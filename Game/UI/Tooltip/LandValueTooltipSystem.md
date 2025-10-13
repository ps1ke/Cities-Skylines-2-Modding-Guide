# Game.UI.Tooltip.LandValueTooltipSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.TooltipSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LandValueTooltipSystem : Game.UI.Tooltip.TooltipSystemBase
{
    private Game.Common.RaycastSystem m_RaycastSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.TerrainToolSystem m_TerrainToolSystem;
    private Game.Simulation.LandValueSystem m_LandValueSystem;
    private Game.Debug.LandValueDebugSystem m_LandValueDebugSystem;
    private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Unity.Entities.EntityQuery m_AttractivenessParameterQuery;
    private Unity.Entities.EntityQuery m_LandValueParameterQuery;
    private Game.UI.Tooltip.FloatTooltip m_LandValueTooltip;
    private Game.UI.Tooltip.FloatTooltip m_TerrainAttractiveTooltip;
    private Game.UI.Tooltip.FloatTooltip m_AirPollutionTooltip;
    private Game.UI.Tooltip.FloatTooltip m_GroundPollutionTooltip;
    private Game.UI.Tooltip.FloatTooltip m_NoisePollutionTooltip;
    private Colossal.Collections.NativeValue<System.Single> m_LandValueResult;
    private Colossal.Collections.NativeValue<System.Single> m_TerrainAttractiveResult;
    private Colossal.Collections.NativeValue<System.Single> m_AirPollutionResult;
    private Colossal.Collections.NativeValue<System.Single> m_NoisePollutionResult;
    private Colossal.Collections.NativeValue<System.Single> m_GroundPollutionResult;

    public LandValueTooltipSystem();

    private System.Boolean IsInfomodeActivated();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.RaycastSystem m_RaycastSystem`  

```csharp
private Game.Common.RaycastSystem m_RaycastSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem`  

```csharp
private Game.Tools.ToolRaycastSystem m_ToolRaycastSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.TerrainToolSystem m_TerrainToolSystem`  

```csharp
private Game.Tools.TerrainToolSystem m_TerrainToolSystem;
```

- `private Game.Simulation.LandValueSystem m_LandValueSystem`  

```csharp
private Game.Simulation.LandValueSystem m_LandValueSystem;
```

- `private Game.Debug.LandValueDebugSystem m_LandValueDebugSystem`  

```csharp
private Game.Debug.LandValueDebugSystem m_LandValueDebugSystem;
```

- `private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem`  

```csharp
private Game.Simulation.TerrainAttractivenessSystem m_TerrainAttractivenessSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Unity.Entities.EntityQuery m_AttractivenessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_AttractivenessParameterQuery;
```

- `private Unity.Entities.EntityQuery m_LandValueParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_LandValueParameterQuery;
```

- `private Game.UI.Tooltip.FloatTooltip m_LandValueTooltip`  

```csharp
private Game.UI.Tooltip.FloatTooltip m_LandValueTooltip;
```

- `private Game.UI.Tooltip.FloatTooltip m_TerrainAttractiveTooltip`  

```csharp
private Game.UI.Tooltip.FloatTooltip m_TerrainAttractiveTooltip;
```

- `private Game.UI.Tooltip.FloatTooltip m_AirPollutionTooltip`  

```csharp
private Game.UI.Tooltip.FloatTooltip m_AirPollutionTooltip;
```

- `private Game.UI.Tooltip.FloatTooltip m_GroundPollutionTooltip`  

```csharp
private Game.UI.Tooltip.FloatTooltip m_GroundPollutionTooltip;
```

- `private Game.UI.Tooltip.FloatTooltip m_NoisePollutionTooltip`  

```csharp
private Game.UI.Tooltip.FloatTooltip m_NoisePollutionTooltip;
```

- `private Colossal.Collections.NativeValue<System.Single> m_LandValueResult`  

```csharp
private Colossal.Collections.NativeValue<System.Single> m_LandValueResult;
```

- `private Colossal.Collections.NativeValue<System.Single> m_TerrainAttractiveResult`  

```csharp
private Colossal.Collections.NativeValue<System.Single> m_TerrainAttractiveResult;
```

- `private Colossal.Collections.NativeValue<System.Single> m_AirPollutionResult`  

```csharp
private Colossal.Collections.NativeValue<System.Single> m_AirPollutionResult;
```

- `private Colossal.Collections.NativeValue<System.Single> m_NoisePollutionResult`  

```csharp
private Colossal.Collections.NativeValue<System.Single> m_NoisePollutionResult;
```

- `private Colossal.Collections.NativeValue<System.Single> m_GroundPollutionResult`  

```csharp
private Colossal.Collections.NativeValue<System.Single> m_GroundPollutionResult;
```


## Constructors

- `public LandValueTooltipSystem()`  

```csharp
[Preserve]
	public LandValueTooltipSystem()
	{
	}
```


## Methods

- `private IsInfomodeActivated() : System.Boolean`  

```csharp
private bool IsInfomodeActivated()
	{
		if (m_PrefabSystem.TryGetPrefab<InfoviewPrefab>(m_LandValueParameterQuery.GetSingleton<LandValueParameterData>().m_LandValueInfoViewPrefab, out var prefab))
		{
			return m_ToolSystem.activeInfoview == prefab;
		}
		return false;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_RaycastSystem = base.World.GetOrCreateSystemManaged<RaycastSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_TerrainToolSystem = base.World.GetOrCreateSystemManaged<TerrainToolSystem>();
		m_ToolRaycastSystem = base.World.GetOrCreateSystemManaged<ToolRaycastSystem>();
		m_LandValueSystem = base.World.GetOrCreateSystemManaged<LandValueSystem>();
		m_LandValueDebugSystem = base.World.GetOrCreateSystemManaged<LandValueDebugSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_TerrainAttractivenessSystem = base.World.GetOrCreateSystemManaged<TerrainAttractivenessSystem>();
		m_GroundPollutionSystem = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		m_AirPollutionSystem = base.World.GetOrCreateSystemManaged<AirPollutionSystem>();
		m_NoisePollutionSystem = base.World.GetOrCreateSystemManaged<NoisePollutionSystem>();
		m_AttractivenessParameterQuery = GetEntityQuery(ComponentType.ReadOnly<AttractivenessParameterData>());
		m_LandValueParameterQuery = GetEntityQuery(ComponentType.ReadOnly<LandValueParameterData>());
		RequireForUpdate(m_AttractivenessParameterQuery);
		RequireForUpdate(m_LandValueParameterQuery);
		m_LandValueTooltip = new FloatTooltip
		{
			path = "LandValue",
			icon = "Media/Game/Icons/LandValue.svg",
			label = LocalizedString.Id("Infoviews.INFOVIEW[LandValue]"),
			unit = "money"
		};
		m_TerrainAttractiveTooltip = new FloatTooltip
		{
			path = "TerrainAttractive",
			icon = "Media/Game/Icons/Tourism.svg",
			label = LocalizedString.Id("Properties.CITY_MODIFIER[Attractiveness]"),
			unit = "integer"
		};
		m_AirPollutionTooltip = new FloatTooltip
		{
			path = "AirPollution",
			icon = "Media/Game/Icons/AirPollution.svg",
			label = LocalizedString.Id("Infoviews.INFOVIEW[AirPollution]"),
			unit = "integer"
		};
		m_GroundPollutionTooltip = new FloatTooltip
		{
			path = "GroundPollution",
			icon = "Media/Game/Icons/GroundPollution.svg",
			label = LocalizedString.Id("Infoviews.INFOVIEW[GroundPollution]"),
			unit = "integer"
		};
		m_NoisePollutionTooltip = new FloatTooltip
		{
			path = "NoisePollution",
			icon = "Media/Game/Icons/NoisePollution.svg",
			label = LocalizedString.Id("Infoviews.INFOVIEW[NoisePollution]"),
			unit = "integer"
		};
		m_LandValueResult = new NativeValue<float>(Allocator.Persistent);
		m_TerrainAttractiveResult = new NativeValue<float>(Allocator.Persistent);
		m_NoisePollutionResult = new NativeValue<float>(Allocator.Persistent);
		m_AirPollutionResult = new NativeValue<float>(Allocator.Persistent);
		m_GroundPollutionResult = new NativeValue<float>(Allocator.Persistent);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_LandValueResult.Dispose();
		m_TerrainAttractiveResult.Dispose();
		m_NoisePollutionResult.Dispose();
		m_AirPollutionResult.Dispose();
		m_GroundPollutionResult.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (IsInfomodeActivated() || m_LandValueDebugSystem.Enabled)
		{
			CompleteDependency();
			m_LandValueTooltip.value = m_LandValueResult.value;
			AddMouseTooltip(m_LandValueTooltip);
			if (m_LandValueDebugSystem.Enabled)
			{
				if (m_TerrainAttractiveResult.value > 0f)
				{
					m_TerrainAttractiveTooltip.value = m_TerrainAttractiveResult.value;
					AddMouseTooltip(m_TerrainAttractiveTooltip);
				}
				if (m_AirPollutionResult.value > 0f)
				{
					m_AirPollutionTooltip.value = m_AirPollutionResult.value;
					AddMouseTooltip(m_AirPollutionTooltip);
				}
				if (m_GroundPollutionResult.value > 0f)
				{
					m_GroundPollutionTooltip.value = m_GroundPollutionResult.value;
					AddMouseTooltip(m_GroundPollutionTooltip);
				}
				if (m_NoisePollutionResult.value > 0f)
				{
					m_NoisePollutionTooltip.value = m_NoisePollutionResult.value;
					AddMouseTooltip(m_NoisePollutionTooltip);
				}
			}
			m_LandValueResult.value = 0f;
			m_TerrainAttractiveResult.value = 0f;
			m_AirPollutionResult.value = 0f;
			m_GroundPollutionResult.value = 0f;
			m_NoisePollutionResult.value = 0f;
			if (m_CameraUpdateSystem.TryGetViewer(out var viewer))
			{
				RaycastInput input = new RaycastInput
				{
					m_Line = ToolRaycastSystem.CalculateRaycastLine(viewer.camera),
					m_TypeMask = (TypeMask.Terrain | TypeMask.Water),
					m_CollisionMask = (CollisionMask.OnGround | CollisionMask.Overground)
				};
				m_RaycastSystem.AddInput(this, input);
				NativeArray<RaycastResult> result = m_RaycastSystem.GetResult(this);
				if (result.Length != 0)
				{
					TerrainHeightData data = m_TerrainSystem.GetHeightData();
					JobHandle dependencies;
					JobHandle dependencies2;
					JobHandle dependencies3;
					JobHandle dependencies4;
					JobHandle dependencies5;
					LandValueTooltipJob jobData = new LandValueTooltipJob
					{
						m_LandValueMap = m_LandValueSystem.GetMap(readOnly: true, out dependencies),
						m_AttractiveMap = m_TerrainAttractivenessSystem.GetMap(readOnly: true, out dependencies2),
						m_GroundPollutionMap = m_GroundPollutionSystem.GetMap(readOnly: true, out dependencies3),
						m_AirPollutionMap = m_AirPollutionSystem.GetMap(readOnly: true, out dependencies4),
						m_NoisePollutionMap = m_NoisePollutionSystem.GetMap(readOnly: true, out dependencies5),
						m_TerrainHeight = TerrainUtils.SampleHeight(ref data, result[0].m_Hit.m_HitPosition),
						m_AttractivenessParameterData = m_AttractivenessParameterQuery.GetSingleton<AttractivenessParameterData>(),
						m_LandValueResult = m_LandValueResult,
						m_NoisePollutionResult = m_NoisePollutionResult,
						m_AirPollutionResult = m_AirPollutionResult,
						m_GroundPollutionResult = m_GroundPollutionResult,
						m_TerrainAttractiveResult = m_TerrainAttractiveResult,
						m_RaycastPosition = result[0].m_Hit.m_HitPosition
					};
					base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, JobHandle.CombineDependencies(dependencies2, dependencies, JobHandle.CombineDependencies(dependencies3, dependencies4, dependencies5))));
					m_LandValueSystem.AddReader(base.Dependency);
					m_TerrainAttractivenessSystem.AddReader(base.Dependency);
					m_GroundPollutionSystem.AddReader(base.Dependency);
					m_AirPollutionSystem.AddReader(base.Dependency);
					m_NoisePollutionSystem.AddReader(base.Dependency);
				}
			}
		}
		else
		{
			m_LandValueResult.value = 0f;
			m_TerrainAttractiveResult.value = 0f;
			m_AirPollutionResult.value = 0f;
			m_GroundPollutionResult.value = 0f;
			m_NoisePollutionResult.value = 0f;
		}
	}
```


## Nested types

- `Game.UI.Tooltip.LandValueTooltipSystem+LandValueTooltipJob`  

