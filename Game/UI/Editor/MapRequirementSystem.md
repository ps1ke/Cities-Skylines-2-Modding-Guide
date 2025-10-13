# Game.UI.Editor.MapRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class MapRequirementSystem : Game.GameSystemBase
{
    private Game.Areas.MapTileSystem m_MapTileSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_TileQuery;
    private Unity.Entities.EntityQuery m_OutsideRoadNodeQuery;
    private Unity.Entities.EntityQuery m_OutsideTrainNodeQuery;
    private Unity.Entities.EntityQuery m_OutsideAirNodeQuery;
    private Unity.Entities.EntityQuery m_OutsideElectricityConnectionQuery;
    private Unity.Jobs.JobHandle m_ResultDependency;
    private Colossal.Collections.NativeValue<System.Boolean> m_WaterResult;
    private Unity.Collections.NativeArray<System.Boolean> m_StartingAreaResources;
    private Unity.Collections.NativeArray<System.Boolean> m_MapResources;
    private System.Boolean <hasStartingArea>k__BackingField;
    private System.Boolean <roadConnection>k__BackingField;
    private System.Boolean <trainConnection>k__BackingField;
    private System.Boolean <airConnection>k__BackingField;
    private System.Boolean <electricityConnection>k__BackingField;
    private Game.UI.Editor.MapRequirementSystem+TypeHandle __TypeHandle;

    public System.Boolean hasStartingArea { get; private set; }
    public System.Boolean roadConnection { get; private set; }
    public System.Boolean trainConnection { get; private set; }
    public System.Boolean airConnection { get; private set; }
    public System.Boolean electricityConnection { get; private set; }

    public MapRequirementSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Boolean MapHasResource(Game.Areas.MapFeature feature);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Boolean StartingAreaHasResource(Game.Areas.MapFeature feature);
}
```


## Fields

- `private Game.Areas.MapTileSystem m_MapTileSystem`  

```csharp
private Game.Areas.MapTileSystem m_MapTileSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_TileQuery`  

```csharp
private Unity.Entities.EntityQuery m_TileQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideRoadNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideRoadNodeQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideTrainNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideTrainNodeQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideAirNodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideAirNodeQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideElectricityConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideElectricityConnectionQuery;
```

- `private Unity.Jobs.JobHandle m_ResultDependency`  

```csharp
private Unity.Jobs.JobHandle m_ResultDependency;
```

- `private Colossal.Collections.NativeValue<System.Boolean> m_WaterResult`  

```csharp
private Colossal.Collections.NativeValue<System.Boolean> m_WaterResult;
```

- `private Unity.Collections.NativeArray<System.Boolean> m_StartingAreaResources`  

```csharp
private Unity.Collections.NativeArray<System.Boolean> m_StartingAreaResources;
```

- `private Unity.Collections.NativeArray<System.Boolean> m_MapResources`  

```csharp
private Unity.Collections.NativeArray<System.Boolean> m_MapResources;
```

- `private System.Boolean <hasStartingArea>k__BackingField`  

```csharp
private System.Boolean <hasStartingArea>k__BackingField;
```

- `private System.Boolean <roadConnection>k__BackingField`  

```csharp
private System.Boolean <roadConnection>k__BackingField;
```

- `private System.Boolean <trainConnection>k__BackingField`  

```csharp
private System.Boolean <trainConnection>k__BackingField;
```

- `private System.Boolean <airConnection>k__BackingField`  

```csharp
private System.Boolean <airConnection>k__BackingField;
```

- `private System.Boolean <electricityConnection>k__BackingField`  

```csharp
private System.Boolean <electricityConnection>k__BackingField;
```

- `private Game.UI.Editor.MapRequirementSystem+TypeHandle __TypeHandle`  

```csharp
private Game.UI.Editor.MapRequirementSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Boolean hasStartingArea { get; private set }`  

```csharp
public System.Boolean hasStartingArea { get; private set; }
```

- `public System.Boolean roadConnection { get; private set }`  

```csharp
public System.Boolean roadConnection { get; private set; }
```

- `public System.Boolean trainConnection { get; private set }`  

```csharp
public System.Boolean trainConnection { get; private set; }
```

- `public System.Boolean airConnection { get; private set }`  

```csharp
public System.Boolean airConnection { get; private set; }
```

- `public System.Boolean electricityConnection { get; private set }`  

```csharp
public System.Boolean electricityConnection { get; private set; }
```


## Constructors

- `public MapRequirementSystem()`  

```csharp
[Preserve]
	public MapRequirementSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `public MapHasResource(Game.Areas.MapFeature feature) : System.Boolean`  

```csharp
public bool MapHasResource(MapFeature feature)
	{
		m_ResultDependency.Complete();
		if (feature > MapFeature.None && feature < MapFeature.Count)
		{
			return m_MapResources[(int)feature];
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
		m_MapTileSystem = base.World.GetOrCreateSystemManaged<MapTileSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_TileQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<MapTile>(),
				ComponentType.ReadOnly<Geometry>(),
				ComponentType.ReadOnly<MapFeatureElement>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_OutsideRoadNodeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Net.Node>(),
				ComponentType.ReadOnly<Road>(),
				ComponentType.ReadOnly<Game.Net.OutsideConnection>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_OutsideTrainNodeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Net.Node>(),
				ComponentType.ReadOnly<TrainTrack>(),
				ComponentType.ReadOnly<Game.Net.OutsideConnection>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_OutsideAirNodeQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<AirplaneStop>(),
				ComponentType.ReadOnly<Game.Objects.OutsideConnection>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_OutsideElectricityConnectionQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<ElectricityOutsideConnection>() },
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		m_WaterResult = new NativeValue<bool>(Allocator.Persistent);
		m_StartingAreaResources = new NativeArray<bool>(9, Allocator.Persistent);
		m_MapResources = new NativeArray<bool>(9, Allocator.Persistent);
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		base.OnDestroy();
		m_WaterResult.Dispose();
		m_StartingAreaResources.Dispose();
		m_MapResources.Dispose();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_ResultDependency.Complete();
		NativeArray<Entity> startingTiles = m_MapTileSystem.GetStartTiles().ToArray(Allocator.TempJob);
		hasStartingArea = startingTiles.Length != 0;
		roadConnection = !m_OutsideRoadNodeQuery.IsEmptyIgnoreFilter;
		trainConnection = !m_OutsideTrainNodeQuery.IsEmptyIgnoreFilter;
		airConnection = !m_OutsideAirNodeQuery.IsEmptyIgnoreFilter;
		electricityConnection = !m_OutsideElectricityConnectionQuery.IsEmptyIgnoreFilter;
		JobHandle deps;
		CheckWaterJob jobData = new CheckWaterJob
		{
			m_Result = m_WaterResult,
			m_SurfaceData = m_WaterSystem.GetSurfaceData(out deps),
			m_StartingTiles = startingTiles,
			m_GeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Geometry_RO_ComponentLookup, ref base.CheckedStateRef)
		};
		base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, deps));
		m_WaterSystem.AddSurfaceReader(base.Dependency);
		CollectStartingResourcesJob jobData2 = new CollectStartingResourcesJob
		{
			m_StartingTiles = startingTiles,
			m_MapFeatureElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_MapFeatureElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_Results = m_StartingAreaResources
		};
		base.Dependency = IJobExtensions.Schedule(jobData2, base.Dependency);
		startingTiles.Dispose(base.Dependency);
		CollectResourcesJob jobData3 = new CollectResourcesJob
		{
			m_AreaChunks = m_TileQuery.ToArchetypeChunkArray(Allocator.TempJob),
			m_MapFeatureElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_MapFeatureElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_Results = m_MapResources
		};
		base.Dependency = IJobExtensions.Schedule(jobData3, base.Dependency);
		m_ResultDependency = base.Dependency;
	}
```

- `public StartingAreaHasResource(Game.Areas.MapFeature feature) : System.Boolean`  

```csharp
public bool StartingAreaHasResource(MapFeature feature)
	{
		m_ResultDependency.Complete();
		switch (feature)
		{
		case MapFeature.SurfaceWater:
			if (!m_StartingAreaResources[(int)feature])
			{
				return m_WaterResult.value;
			}
			return true;
		case MapFeature.Area:
		case MapFeature.BuildableLand:
		case MapFeature.FertileLand:
		case MapFeature.Forest:
		case MapFeature.Oil:
		case MapFeature.Ore:
		case MapFeature.GroundWater:
		case MapFeature.Fish:
			return m_StartingAreaResources[(int)feature];
		default:
			return false;
		}
	}
```


## Nested types

- `Game.UI.Editor.MapRequirementSystem+CollectResourcesJob`  
- `Game.UI.Editor.MapRequirementSystem+CollectStartingResourcesJob`  
- `Game.UI.Editor.MapRequirementSystem+CheckWaterJob`  
- `Game.UI.Editor.MapRequirementSystem+TypeHandle`  

