# Game.UI.Tooltip.PollutionTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PollutionTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultTool;
    private Game.Common.RaycastSystem m_RaycastSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_ActiveInfomodeQuery;
    private Game.UI.Tooltip.IntTooltip m_Garbage;
    private Game.UI.Tooltip.IntTooltip m_AirPollution;
    private Game.UI.Tooltip.IntTooltip m_GroundPollution;
    private Game.UI.Tooltip.IntTooltip m_NoisePollution;
    private Game.UI.Tooltip.IntTooltip m_WaterPollution;
    private Game.Common.RaycastResult m_RaycastResult;

    private Game.Common.RaycastResult raycastResult { private get; private set; }

    public PollutionTooltipSystem();

    protected virtual System.Void OnCreate();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.DefaultToolSystem m_DefaultTool`  

```csharp
private Game.Tools.DefaultToolSystem m_DefaultTool;
```

- `private Game.Common.RaycastSystem m_RaycastSystem`  

```csharp
private Game.Common.RaycastSystem m_RaycastSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_ActiveInfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActiveInfomodeQuery;
```

- `private Game.UI.Tooltip.IntTooltip m_Garbage`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Garbage;
```

- `private Game.UI.Tooltip.IntTooltip m_AirPollution`  

```csharp
private Game.UI.Tooltip.IntTooltip m_AirPollution;
```

- `private Game.UI.Tooltip.IntTooltip m_GroundPollution`  

```csharp
private Game.UI.Tooltip.IntTooltip m_GroundPollution;
```

- `private Game.UI.Tooltip.IntTooltip m_NoisePollution`  

```csharp
private Game.UI.Tooltip.IntTooltip m_NoisePollution;
```

- `private Game.UI.Tooltip.IntTooltip m_WaterPollution`  

```csharp
private Game.UI.Tooltip.IntTooltip m_WaterPollution;
```

- `private Game.Common.RaycastResult m_RaycastResult`  

```csharp
private Game.Common.RaycastResult m_RaycastResult;
```


## Properties

- `private Game.Common.RaycastResult raycastResult { private get; private set }`  

```csharp
private Game.Common.RaycastResult raycastResult { private get; private set; }
```


## Constructors

- `public PollutionTooltipSystem()`  

```csharp
[Preserve]
	public PollutionTooltipSystem()
	{
	}
```


## Methods

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_DefaultTool = base.World.GetOrCreateSystemManaged<DefaultToolSystem>();
		m_RaycastSystem = base.World.GetOrCreateSystemManaged<RaycastSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_GroundPollutionSystem = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		m_NoisePollutionSystem = base.World.GetOrCreateSystemManaged<NoisePollutionSystem>();
		m_AirPollutionSystem = base.World.GetOrCreateSystemManaged<AirPollutionSystem>();
		m_GroundWaterSystem = base.World.GetOrCreateSystemManaged<GroundWaterSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_ActiveInfomodeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<InfomodeData>(),
				ComponentType.ReadOnly<InfomodeActive>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<InfoviewHeatmapData>(),
				ComponentType.ReadOnly<InfoviewBuildingStatusData>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<InfomodeGroup>() }
		});
		m_Garbage = new IntTooltip
		{
			path = "garbage",
			icon = "Media/Game/Icons/Garbage.svg",
			label = LocalizedString.Id("DefaultTool.INFOMODE_TOOLTIP[Garbage]"),
			unit = "integer"
		};
		m_AirPollution = new IntTooltip
		{
			path = "airPollution",
			icon = "Media/Game/Icons/AirPollution.svg",
			label = LocalizedString.Id("DefaultTool.INFOMODE_TOOLTIP[AirPollution]"),
			unit = "integer"
		};
		m_GroundPollution = new IntTooltip
		{
			path = "groundPollution",
			icon = "Media/Game/Icons/GroundPollution.svg",
			label = LocalizedString.Id("DefaultTool.INFOMODE_TOOLTIP[GroundPollution]"),
			unit = "integer"
		};
		m_NoisePollution = new IntTooltip
		{
			path = "noisePollution",
			icon = "Media/Game/Icons/NoisePollution.svg",
			label = LocalizedString.Id("DefaultTool.INFOMODE_TOOLTIP[NoisePollution]"),
			unit = "integer"
		};
		m_WaterPollution = new IntTooltip
		{
			path = "waterPollution",
			icon = "Media/Game/Icons/WaterPollution.svg",
			label = LocalizedString.Id("DefaultTool.INFOMODE_TOOLTIP[WaterPollution]"),
			unit = "integer"
		};
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_ToolSystem.activeTool != m_DefaultTool || m_ToolSystem.activeInfoview == null || m_ActiveInfomodeQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		raycastResult = default(RaycastResult);
		foreach (Entity item in m_ActiveInfomodeQuery.ToEntityArray(Allocator.Temp))
		{
			InfoviewBuildingStatusData component2;
			if (base.EntityManager.TryGetComponent<InfoviewHeatmapData>(item, out var component))
			{
				switch (component.m_Type)
				{
				case HeatmapData.GroundPollution:
				{
					if (raycastResult.m_Owner == Entity.Null)
					{
						return;
					}
					JobHandle dependencies4;
					NativeArray<GroundPollution> map4 = m_GroundPollutionSystem.GetMap(readOnly: true, out dependencies4);
					dependencies4.Complete();
					GroundPollution pollution3 = GroundPollutionSystem.GetPollution(raycastResult.m_Hit.m_HitPosition, map4);
					m_GroundPollution.value = pollution3.m_Pollution;
					AddMouseTooltip(m_GroundPollution);
					break;
				}
				case HeatmapData.AirPollution:
				{
					if (raycastResult.m_Owner == Entity.Null)
					{
						return;
					}
					JobHandle dependencies3;
					NativeArray<AirPollution> map3 = m_AirPollutionSystem.GetMap(readOnly: true, out dependencies3);
					dependencies3.Complete();
					AirPollution pollution2 = AirPollutionSystem.GetPollution(raycastResult.m_Hit.m_HitPosition, map3);
					m_AirPollution.value = pollution2.m_Pollution;
					AddMouseTooltip(m_AirPollution);
					break;
				}
				case HeatmapData.WaterPollution:
				{
					if (raycastResult.m_Owner == Entity.Null)
					{
						return;
					}
					JobHandle deps;
					WaterSurfaceData data = m_WaterSystem.GetSurfaceData(out deps);
					deps.Complete();
					if (WaterUtils.SampleDepth(ref data, raycastResult.m_Hit.m_HitPosition) > 0f)
					{
						float num = WaterUtils.SamplePolluted(ref data, raycastResult.m_Hit.m_HitPosition);
						m_WaterPollution.value = (int)(num * 10000f);
						AddMouseTooltip(m_WaterPollution);
					}
					break;
				}
				case HeatmapData.GroundWaterPollution:
				{
					if (raycastResult.m_Owner == Entity.Null)
					{
						return;
					}
					JobHandle deps2;
					WaterSurfaceData data2 = m_WaterSystem.GetSurfaceData(out deps2);
					deps2.Complete();
					if (WaterUtils.SampleDepth(ref data2, raycastResult.m_Hit.m_HitPosition) == 0f)
					{
						JobHandle dependencies2;
						NativeArray<GroundWater> map2 = m_GroundWaterSystem.GetMap(readOnly: true, out dependencies2);
						dependencies2.Complete();
						GroundWater groundWater = GroundWaterSystem.GetGroundWater(raycastResult.m_Hit.m_HitPosition, map2);
						m_WaterPollution.value = groundWater.m_Polluted;
						AddMouseTooltip(m_WaterPollution);
					}
					break;
				}
				case HeatmapData.Noise:
				{
					if (raycastResult.m_Owner == Entity.Null)
					{
						return;
					}
					JobHandle dependencies;
					NativeArray<NoisePollution> map = m_NoisePollutionSystem.GetMap(readOnly: true, out dependencies);
					dependencies.Complete();
					NoisePollution pollution = NoisePollutionSystem.GetPollution(raycastResult.m_Hit.m_HitPosition, map);
					m_NoisePollution.value = pollution.m_Pollution;
					AddMouseTooltip(m_NoisePollution);
					break;
				}
				}
			}
			else if (base.EntityManager.TryGetComponent<InfoviewBuildingStatusData>(item, out component2) && component2.m_Type == BuildingStatusType.GarbageAccumulation)
			{
				if (raycastResult.m_Owner == Entity.Null)
				{
					break;
				}
				if (base.EntityManager.HasComponent<Building>(raycastResult.m_Owner) && base.EntityManager.TryGetComponent<GarbageProducer>(raycastResult.m_Owner, out var component3))
				{
					m_Garbage.value = component3.m_Garbage;
					AddMouseTooltip(m_Garbage);
				}
			}
		}
	}
```


