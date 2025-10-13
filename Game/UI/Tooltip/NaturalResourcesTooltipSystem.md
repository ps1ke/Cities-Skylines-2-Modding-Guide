# Game.UI.Tooltip.NaturalResourcesTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

## Code

```csharp
public class NaturalResourcesTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.DefaultToolSystem m_DefaultTool;
    private Game.Common.RaycastSystem m_RaycastSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_ActiveInfomodeQuery;
    private Game.UI.Tooltip.IntTooltip m_Fertility;
    private Game.UI.Tooltip.IntTooltip m_Wood;
    private Game.UI.Tooltip.IntTooltip m_Oil;
    private Game.UI.Tooltip.IntTooltip m_Ore;
    private Game.UI.Tooltip.IntTooltip m_Fish;
    private Game.Common.RaycastResult m_RaycastResult;

    private Game.Common.RaycastResult raycastResult { private get; private set; }

    public NaturalResourcesTooltipSystem();

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

- `private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem`  

```csharp
private Game.Simulation.NaturalResourceSystem m_NaturalResourceSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_ActiveInfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_ActiveInfomodeQuery;
```

- `private Game.UI.Tooltip.IntTooltip m_Fertility`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Fertility;
```

- `private Game.UI.Tooltip.IntTooltip m_Wood`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Wood;
```

- `private Game.UI.Tooltip.IntTooltip m_Oil`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Oil;
```

- `private Game.UI.Tooltip.IntTooltip m_Ore`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Ore;
```

- `private Game.UI.Tooltip.IntTooltip m_Fish`  

```csharp
private Game.UI.Tooltip.IntTooltip m_Fish;
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

- `public NaturalResourcesTooltipSystem()`  

```csharp
[Preserve]
	public NaturalResourcesTooltipSystem()
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
		m_NaturalResourceSystem = base.World.GetOrCreateSystemManaged<NaturalResourceSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_ActiveInfomodeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[4]
			{
				ComponentType.ReadOnly<PrefabData>(),
				ComponentType.ReadOnly<InfomodeData>(),
				ComponentType.ReadOnly<InfomodeActive>(),
				ComponentType.ReadOnly<InfoviewHeatmapData>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<InfomodeGroup>() }
		});
		m_Fertility = new IntTooltip
		{
			path = "fertility",
			icon = "Media/Game/Icons/Fertility.svg",
			label = LocalizedString.Id("DefaultTool.INFOMODE_TOOLTIP[Fertility]"),
			unit = "integer"
		};
		m_Wood = new IntTooltip
		{
			path = "wood",
			icon = "Media/Game/Resources/Wood.svg",
			label = LocalizedString.Id("DefaultTool.INFOMODE_TOOLTIP[Wood]"),
			unit = "integer"
		};
		m_Oil = new IntTooltip
		{
			path = "oil",
			icon = "Media/Game/Resources/Oil.svg",
			label = LocalizedString.Id("DefaultTool.INFOMODE_TOOLTIP[Oil]"),
			unit = "integer"
		};
		m_Ore = new IntTooltip
		{
			path = "ore",
			icon = "Media/Game/Resources/Ore.svg",
			label = LocalizedString.Id("DefaultTool.INFOMODE_TOOLTIP[Ore]"),
			unit = "integer"
		};
		m_Fish = new IntTooltip
		{
			path = "fish",
			icon = "Media/Game/Resources/Fish.svg",
			label = LocalizedString.Id("DefaultTool.INFOMODE_TOOLTIP[Fish]"),
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
		NativeArray<Entity> nativeArray = m_ActiveInfomodeQuery.ToEntityArray(Allocator.Temp);
		foreach (Entity item in nativeArray)
		{
			switch (base.EntityManager.GetComponentData<InfoviewHeatmapData>(item).m_Type)
			{
			case HeatmapData.Fertility:
			{
				if (raycastResult.m_Owner == Entity.Null)
				{
					return;
				}
				JobHandle deps2;
				WaterSurfaceData data2 = m_WaterSystem.GetSurfaceData(out deps2);
				deps2.Complete();
				if (!(WaterUtils.SampleDepth(ref data2, raycastResult.m_Hit.m_HitPosition) > 0f))
				{
					JobHandle dependencies4;
					NativeArray<NaturalResourceCell> map4 = m_NaturalResourceSystem.GetMap(readOnly: true, out dependencies4);
					dependencies4.Complete();
					NaturalResourceAmount fertilityAmount = NaturalResourceSystem.GetFertilityAmount(raycastResult.m_Hit.m_HitPosition, map4);
					if (fertilityAmount.m_Base > fertilityAmount.m_Used)
					{
						m_Fertility.value = fertilityAmount.m_Base - fertilityAmount.m_Used;
						AddMouseTooltip(m_Fertility);
					}
				}
				break;
			}
			case HeatmapData.Oil:
			{
				if (raycastResult.m_Owner == Entity.Null)
				{
					return;
				}
				JobHandle dependencies3;
				NativeArray<NaturalResourceCell> map3 = m_NaturalResourceSystem.GetMap(readOnly: true, out dependencies3);
				dependencies3.Complete();
				NaturalResourceAmount oilAmount = NaturalResourceSystem.GetOilAmount(raycastResult.m_Hit.m_HitPosition, map3);
				if (oilAmount.m_Base > oilAmount.m_Used)
				{
					m_Oil.value = oilAmount.m_Base - oilAmount.m_Used;
					AddMouseTooltip(m_Oil);
				}
				break;
			}
			case HeatmapData.Ore:
			{
				if (raycastResult.m_Owner == Entity.Null)
				{
					return;
				}
				JobHandle dependencies2;
				NativeArray<NaturalResourceCell> map2 = m_NaturalResourceSystem.GetMap(readOnly: true, out dependencies2);
				dependencies2.Complete();
				NaturalResourceAmount oreAmount = NaturalResourceSystem.GetOreAmount(raycastResult.m_Hit.m_HitPosition, map2);
				if (oreAmount.m_Base > oreAmount.m_Used)
				{
					m_Ore.value = oreAmount.m_Base - oreAmount.m_Used;
					AddMouseTooltip(m_Ore);
				}
				break;
			}
			case HeatmapData.Fish:
			{
				if (raycastResult.m_Owner == Entity.Null)
				{
					return;
				}
				JobHandle deps;
				WaterSurfaceData data = m_WaterSystem.GetSurfaceData(out deps);
				deps.Complete();
				if (!(WaterUtils.SampleDepth(ref data, raycastResult.m_Hit.m_HitPosition) <= 0f))
				{
					JobHandle dependencies;
					NativeArray<NaturalResourceCell> map = m_NaturalResourceSystem.GetMap(readOnly: true, out dependencies);
					dependencies.Complete();
					NaturalResourceAmount fishAmount = NaturalResourceSystem.GetFishAmount(raycastResult.m_Hit.m_HitPosition, map);
					if (fishAmount.m_Base > fishAmount.m_Used)
					{
						m_Fish.value = fishAmount.m_Base - fishAmount.m_Used;
						AddMouseTooltip(m_Fish);
					}
				}
				break;
			}
			}
		}
		nativeArray.Dispose();
	}
```


