# Game.Net.AirwaySystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AirwaySystem : Game.GameSystemBase, Colossal.Serialization.Entities.IJobSerializable
{
    private Game.Serialization.LoadGameSystem m_LoadGameSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Entities.EntityQuery m_AirplaneConnectionQuery;
    private Unity.Entities.EntityQuery m_OldConnectionQuery;
    private Game.Net.AirwayHelpers+AirwayData m_AirwayData;
    private Game.Net.AirwaySystem+TypeHandle __TypeHandle;
    private static const System.Single TERRAIN_SIZE;
    private static const System.Int32 HELICOPTER_GRID_WIDTH;
    private static const System.Int32 HELICOPTER_GRID_LENGTH;
    private static const System.Single HELICOPTER_CELL_SIZE;
    private static const System.Single HELICOPTER_PATH_HEIGHT;
    private static const System.Int32 AIRPLANE_GRID_WIDTH;
    private static const System.Int32 AIRPLANE_GRID_LENGTH;
    private static const System.Single AIRPLANE_CELL_SIZE;
    private static const System.Single AIRPLANE_PATH_HEIGHT;

    public AirwaySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public Unity.Jobs.JobHandle Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
    public Game.Net.AirwayHelpers+AirwayData GetAirwayData();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public Unity.Jobs.JobHandle Serialize<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Serialization.LoadGameSystem m_LoadGameSystem`  

```csharp
private Game.Serialization.LoadGameSystem m_LoadGameSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Entities.EntityQuery m_AirplaneConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_AirplaneConnectionQuery;
```

- `private Unity.Entities.EntityQuery m_OldConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_OldConnectionQuery;
```

- `private Game.Net.AirwayHelpers+AirwayData m_AirwayData`  

```csharp
private Game.Net.AirwayHelpers+AirwayData m_AirwayData;
```

- `private Game.Net.AirwaySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.AirwaySystem+TypeHandle __TypeHandle;
```

- `private static const System.Single TERRAIN_SIZE`  

```csharp
private static const System.Single TERRAIN_SIZE;
```

- `private static const System.Int32 HELICOPTER_GRID_WIDTH`  

```csharp
private static const System.Int32 HELICOPTER_GRID_WIDTH;
```

- `private static const System.Int32 HELICOPTER_GRID_LENGTH`  

```csharp
private static const System.Int32 HELICOPTER_GRID_LENGTH;
```

- `private static const System.Single HELICOPTER_CELL_SIZE`  

```csharp
private static const System.Single HELICOPTER_CELL_SIZE;
```

- `private static const System.Single HELICOPTER_PATH_HEIGHT`  

```csharp
private static const System.Single HELICOPTER_PATH_HEIGHT;
```

- `private static const System.Int32 AIRPLANE_GRID_WIDTH`  

```csharp
private static const System.Int32 AIRPLANE_GRID_WIDTH;
```

- `private static const System.Int32 AIRPLANE_GRID_LENGTH`  

```csharp
private static const System.Int32 AIRPLANE_GRID_LENGTH;
```

- `private static const System.Single AIRPLANE_CELL_SIZE`  

```csharp
private static const System.Single AIRPLANE_CELL_SIZE;
```

- `private static const System.Single AIRPLANE_PATH_HEIGHT`  

```csharp
private static const System.Single AIRPLANE_PATH_HEIGHT;
```


## Constructors

- `public AirwaySystem()`  

```csharp
[Preserve]
	public AirwaySystem()
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

- `public Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
```

- `public GetAirwayData() : Game.Net.AirwayHelpers+AirwayData`  

```csharp
public AirwayHelpers.AirwayData GetAirwayData()
	{
		return m_AirwayData;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_LoadGameSystem = base.World.GetOrCreateSystemManaged<LoadGameSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_PrefabQuery = GetEntityQuery(ComponentType.ReadOnly<ConnectionLaneData>(), ComponentType.ReadOnly<PrefabData>());
		m_AirplaneConnectionQuery = GetEntityQuery(ComponentType.ReadOnly<AirplaneStop>(), ComponentType.ReadOnly<Game.Routes.TakeoffLocation>(), ComponentType.ReadOnly<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_OldConnectionQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[1] { ComponentType.ReadOnly<ConnectionLane>() },
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<OutsideConnection>(),
				ComponentType.ReadOnly<Owner>()
			}
		});
		RequireForUpdate(m_PrefabQuery);
		AirwayHelpers.AirwayMap helicopterMap = new AirwayHelpers.AirwayMap(new int2(28, 28), 494.34482f, 200f, Allocator.Persistent);
		AirwayHelpers.AirwayMap airplaneMap = new AirwayHelpers.AirwayMap(new int2(14, 14), 988.68964f, 1000f, Allocator.Persistent);
		m_AirwayData = new AirwayHelpers.AirwayData(helicopterMap, airplaneMap);
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
		m_AirwayData.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_LoadGameSystem.context.purpose == Purpose.NewGame && m_OldConnectionQuery.IsEmptyIgnoreFilter)
		{
			NativeArray<Entity> nativeArray = m_PrefabQuery.ToEntityArray(Allocator.TempJob);
			NetLaneArchetypeData componentData = base.EntityManager.GetComponentData<NetLaneArchetypeData>(nativeArray[0]);
			if (!m_AirplaneConnectionQuery.IsEmptyIgnoreFilter)
			{
				base.EntityManager.AddComponent<Updated>(m_AirplaneConnectionQuery);
			}
			base.EntityManager.CreateEntity(componentData.m_LaneArchetype, m_AirwayData.helicopterMap.entities);
			base.EntityManager.CreateEntity(componentData.m_LaneArchetype, m_AirwayData.airplaneMap.entities);
			TerrainHeightData heightData = m_TerrainSystem.GetHeightData(waitForPending: true);
			JobHandle deps;
			WaterSurfaceData surfaceData = m_WaterSystem.GetSurfaceData(out deps);
			GenerateAirwayLanesJob jobData = new GenerateAirwayLanesJob
			{
				m_AirwayMap = m_AirwayData.helicopterMap,
				m_Prefab = nativeArray[0],
				m_RoadType = RoadTypes.Helicopter,
				m_TerrainHeightData = heightData,
				m_WaterSurfaceData = surfaceData,
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RW_ComponentLookup, ref base.CheckedStateRef),
				m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RW_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RW_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectionLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ConnectionLane_RW_ComponentLookup, ref base.CheckedStateRef)
			};
			JobHandle jobHandle = new GenerateAirwayLanesJob
			{
				m_AirwayMap = m_AirwayData.airplaneMap,
				m_Prefab = nativeArray[0],
				m_RoadType = RoadTypes.Airplane,
				m_TerrainHeightData = heightData,
				m_WaterSurfaceData = surfaceData,
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RW_ComponentLookup, ref base.CheckedStateRef),
				m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RW_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RW_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectionLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ConnectionLane_RW_ComponentLookup, ref base.CheckedStateRef)
			}.Schedule(dependsOn: IJobParallelForExtensions.Schedule(jobData, m_AirwayData.helicopterMap.entities.Length, 4, JobHandle.CombineDependencies(base.Dependency, deps)), arrayLength: m_AirwayData.airplaneMap.entities.Length, innerloopBatchCount: 4);
			nativeArray.Dispose();
			m_TerrainSystem.AddCPUHeightReader(jobHandle);
			m_WaterSystem.AddSurfaceReader(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```

- `public Serialize<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle Serialize<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetDefaults(Context context)
	{
		return IJobExtensions.Schedule(new SetDefaultsJob
		{
			m_Context = context,
			m_HelicopterMap = m_AirwayData.helicopterMap,
			m_AirplaneMap = m_AirwayData.airplaneMap
		});
	}
```


## Nested types

- `Game.Net.AirwaySystem+SerializeJob<TWriter>`  
- `Game.Net.AirwaySystem+DeserializeJob<TReader>`  
- `Game.Net.AirwaySystem+SetDefaultsJob`  
- `Game.Net.AirwaySystem+GenerateAirwayLanesJob`  
- `Game.Net.AirwaySystem+TypeHandle`  

