# Game.Simulation.GroundHeightSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IJobSerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GroundHeightSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IJobSerializable
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Common.ModificationBarrier2 m_ModificationBarrier;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Areas.GeometrySystem m_AreaGeometrySystem;
    private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_NewUpdates;
    private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_PendingUpdates;
    private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_ReadingUpdates;
    private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_ReadyUpdates;
    private Unity.Jobs.JobHandle m_UpdateDeps;
    private Game.Simulation.GroundHeightSystem+LoadHeightsState m_LoadHeightsState;
    private Game.Simulation.GroundHeightSystem+TypeHandle __TypeHandle;

    public GroundHeightSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AfterReadHeights();
    public System.Void BeforeReadHeights();
    public System.Void BeforeUpdateHeights();
    public Unity.Jobs.JobHandle Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> GetUpdateBuffer();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    public Unity.Jobs.JobHandle Serialize<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Common.ModificationBarrier2 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier2 m_ModificationBarrier;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Areas.GeometrySystem m_AreaGeometrySystem`  

```csharp
private Game.Areas.GeometrySystem m_AreaGeometrySystem;
```

- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_NewUpdates`  

```csharp
private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_NewUpdates;
```

- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_PendingUpdates`  

```csharp
private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_PendingUpdates;
```

- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_ReadingUpdates`  

```csharp
private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_ReadingUpdates;
```

- `private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_ReadyUpdates`  

```csharp
private Unity.Collections.NativeList<Colossal.Mathematics.Bounds2> m_ReadyUpdates;
```

- `private Unity.Jobs.JobHandle m_UpdateDeps`  

```csharp
private Unity.Jobs.JobHandle m_UpdateDeps;
```

- `private Game.Simulation.GroundHeightSystem+LoadHeightsState m_LoadHeightsState`  

```csharp
private Game.Simulation.GroundHeightSystem+LoadHeightsState m_LoadHeightsState;
```

- `private Game.Simulation.GroundHeightSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.GroundHeightSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GroundHeightSystem()`  

```csharp
[Preserve]
	public GroundHeightSystem()
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

- `public AfterReadHeights() : System.Void`  

```csharp
public void AfterReadHeights()
	{
		m_UpdateDeps.Complete();
		if (m_ReadingUpdates.IsCreated && m_ReadingUpdates.Length != 0)
		{
			if (m_ReadyUpdates.IsCreated)
			{
				m_ReadyUpdates.AddRange(m_ReadingUpdates.AsArray());
				m_ReadingUpdates.Clear();
			}
			else
			{
				m_ReadyUpdates = m_ReadingUpdates;
				m_ReadingUpdates = default(NativeList<Bounds2>);
			}
		}
		if (m_LoadHeightsState == LoadHeightsState.Reading)
		{
			m_LoadHeightsState = LoadHeightsState.Ready;
			m_AreaGeometrySystem.TerrainHeightsReadyAfterLoading();
			m_TerrainSystem.TerrainHeightsReadyAfterLoading();
		}
	}
```

- `public BeforeReadHeights() : System.Void`  

```csharp
public void BeforeReadHeights()
	{
		m_UpdateDeps.Complete();
		if (m_PendingUpdates.IsCreated && m_PendingUpdates.Length != 0)
		{
			if (m_ReadingUpdates.IsCreated)
			{
				m_ReadingUpdates.AddRange(m_PendingUpdates.AsArray());
				m_PendingUpdates.Clear();
			}
			else
			{
				m_ReadingUpdates = m_PendingUpdates;
				m_PendingUpdates = default(NativeList<Bounds2>);
			}
		}
		if (m_LoadHeightsState == LoadHeightsState.Pending)
		{
			m_LoadHeightsState = LoadHeightsState.Reading;
		}
	}
```

- `public BeforeUpdateHeights() : System.Void`  

```csharp
public void BeforeUpdateHeights()
	{
		m_UpdateDeps.Complete();
		if (m_NewUpdates.IsCreated && m_NewUpdates.Length != 0)
		{
			if (m_PendingUpdates.IsCreated)
			{
				m_PendingUpdates.AddRange(m_NewUpdates.AsArray());
				m_NewUpdates.Clear();
			}
			else
			{
				m_PendingUpdates = m_NewUpdates;
				m_NewUpdates = default(NativeList<Bounds2>);
			}
		}
		if (m_LoadHeightsState == LoadHeightsState.Loaded)
		{
			m_LoadHeightsState = LoadHeightsState.Pending;
		}
	}
```

- `public Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
```

- `public GetUpdateBuffer() : Unity.Collections.NativeList<Colossal.Mathematics.Bounds2>`  

```csharp
public NativeList<Bounds2> GetUpdateBuffer()
	{
		m_UpdateDeps.Complete();
		if (!m_NewUpdates.IsCreated)
		{
			if (m_ReadyUpdates.IsCreated && m_ReadyUpdates.Length == 0)
			{
				m_NewUpdates = m_ReadyUpdates;
				m_ReadyUpdates = default(NativeList<Bounds2>);
			}
			else
			{
				m_NewUpdates = new NativeList<Bounds2>(Allocator.Persistent);
			}
		}
		return m_NewUpdates;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier2>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_AreaGeometrySystem = base.World.GetOrCreateSystemManaged<Game.Areas.GeometrySystem>();
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
		m_UpdateDeps.Complete();
		if (m_NewUpdates.IsCreated)
		{
			m_NewUpdates.Dispose();
		}
		if (m_PendingUpdates.IsCreated)
		{
			m_PendingUpdates.Dispose();
		}
		if (m_ReadingUpdates.IsCreated)
		{
			m_ReadingUpdates.Dispose();
		}
		if (m_ReadyUpdates.IsCreated)
		{
			m_ReadyUpdates.Dispose();
		}
		base.OnDestroy();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_LoadHeightsState = LoadHeightsState.Loaded;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_UpdateDeps.Complete();
		if (m_ReadyUpdates.IsCreated && m_ReadyUpdates.Length != 0)
		{
			NativeQueue<Entity> queue = new NativeQueue<Entity>(Allocator.TempJob);
			NativeList<Entity> list = new NativeList<Entity>(Allocator.TempJob);
			JobHandle dependencies;
			JobHandle dependencies2;
			JobHandle dependencies3;
			JobHandle dependencies4;
			BoundsFindJob jobData = new BoundsFindJob
			{
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ObjectElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingLotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Lot_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NetElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
				m_Triangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
				m_ReadyUpdates = m_ReadyUpdates,
				m_StaticObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies),
				m_LaneSearchTree = m_NetSearchSystem.GetLaneSearchTree(readOnly: true, out dependencies2),
				m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies3),
				m_AreaSearchTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies4),
				m_Queue = queue.AsParallelWriter()
			};
			DequeueJob jobData2 = new DequeueJob
			{
				m_Queue = queue,
				m_List = list,
				m_ReadyUpdates = m_ReadyUpdates
			};
			JobHandle deps;
			UpdateHeightsJob jobData3 = new UpdateHeightsJob
			{
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NetElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ObjectElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_SpawnLocation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_MovedLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_MovedLocation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingLotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Lot_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabPlaceableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabBuildingExtensionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingExtensionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabBuildingTerraformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingTerraformData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabAreaGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
				m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RW_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RW_ComponentLookup, ref base.CheckedStateRef),
				m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RW_ComponentLookup, ref base.CheckedStateRef),
				m_CullingInfoData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_CullingInfo_RW_ComponentLookup, ref base.CheckedStateRef),
				m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RW_BufferLookup, ref base.CheckedStateRef),
				m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
				m_List = list,
				m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
				m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			JobHandle jobHandle = IJobParallelForExtensions.Schedule(jobData, m_ReadyUpdates.Length, 1, JobHandle.CombineDependencies(base.Dependency, dependencies4, JobHandle.CombineDependencies(dependencies, dependencies2, dependencies3)));
			JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, jobHandle);
			JobHandle jobHandle3 = jobData3.Schedule(list, 4, JobHandle.CombineDependencies(jobHandle2, deps));
			queue.Dispose(jobHandle2);
			list.Dispose(jobHandle3);
			m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle);
			m_NetSearchSystem.AddLaneSearchTreeReader(jobHandle);
			m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
			m_AreaSearchSystem.AddSearchTreeReader(jobHandle);
			m_TerrainSystem.AddCPUHeightReader(jobHandle3);
			m_WaterSystem.AddSurfaceReader(jobHandle3);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle3);
			base.Dependency = jobHandle3;
			m_UpdateDeps = jobHandle2;
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
		SetDefaultsJob jobData = new SetDefaultsJob
		{
			m_NewUpdates = m_NewUpdates,
			m_PendingUpdates = m_PendingUpdates,
			m_ReadingUpdates = m_ReadingUpdates,
			m_ReadyUpdates = m_ReadyUpdates
		};
		m_UpdateDeps = IJobExtensions.Schedule(jobData, m_UpdateDeps);
		return m_UpdateDeps;
	}
```


## Nested types

- `Game.Simulation.GroundHeightSystem+LoadHeightsState`  
- `Game.Simulation.GroundHeightSystem+SerializeJob<TWriter>`  
- `Game.Simulation.GroundHeightSystem+DeserializeJob<TReader>`  
- `Game.Simulation.GroundHeightSystem+SetDefaultsJob`  
- `Game.Simulation.GroundHeightSystem+BoundsFindJob`  
- `Game.Simulation.GroundHeightSystem+DequeueJob`  
- `Game.Simulation.GroundHeightSystem+UpdateHeightsJob`  
- `Game.Simulation.GroundHeightSystem+TypeHandle`  

