# Game.Net.LaneReferencesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LaneReferencesSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier4B m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_LanesQuery;
    private Unity.Entities.EntityQuery m_UpdatedOwnersQuery;
    private Unity.Entities.EntityQuery m_AllOwnersQuery;
    private Unity.Collections.NativeQueue<Game.Net.Lane> m_SkipLaneQueue;
    private Unity.Jobs.JobHandle m_SkipLaneDeps;
    private System.Boolean m_Loaded;
    private Game.Net.LaneReferencesSystem+TypeHandle __TypeHandle;

    public LaneReferencesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddSkipLaneWriter(Unity.Jobs.JobHandle dependency);
    private System.Boolean GetLoaded();
    public Unity.Collections.NativeQueue<Game.Net.Lane> GetSkipLaneQueue();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4B m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_LanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_LanesQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedOwnersQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedOwnersQuery;
```

- `private Unity.Entities.EntityQuery m_AllOwnersQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllOwnersQuery;
```

- `private Unity.Collections.NativeQueue<Game.Net.Lane> m_SkipLaneQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Net.Lane> m_SkipLaneQueue;
```

- `private Unity.Jobs.JobHandle m_SkipLaneDeps`  

```csharp
private Unity.Jobs.JobHandle m_SkipLaneDeps;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Net.LaneReferencesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.LaneReferencesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LaneReferencesSystem()`  

```csharp
[Preserve]
	public LaneReferencesSystem()
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

- `public AddSkipLaneWriter(Unity.Jobs.JobHandle dependency) : System.Void`  

```csharp
public void AddSkipLaneWriter(JobHandle dependency)
	{
		m_SkipLaneDeps = dependency;
	}
```

- `private GetLoaded() : System.Boolean`  

```csharp
private bool GetLoaded()
	{
		if (m_Loaded)
		{
			m_Loaded = false;
			return true;
		}
		return false;
	}
```

- `public GetSkipLaneQueue() : Unity.Collections.NativeQueue<Game.Net.Lane>`  

```csharp
public NativeQueue<Lane> GetSkipLaneQueue()
	{
		m_SkipLaneQueue = new NativeQueue<Lane>(Allocator.TempJob);
		return m_SkipLaneQueue;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier4B>();
		m_LanesQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Lane>(),
				ComponentType.ReadOnly<Owner>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<SecondaryLane>() }
		});
		m_UpdatedOwnersQuery = GetEntityQuery(ComponentType.ReadWrite<SubLane>(), ComponentType.ReadOnly<Updated>());
		m_AllOwnersQuery = GetEntityQuery(ComponentType.ReadWrite<SubLane>());
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_Loaded = true;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		EntityQuery query = (GetLoaded() ? m_AllOwnersQuery : m_UpdatedOwnersQuery);
		if (!m_LanesQuery.IsEmptyIgnoreFilter)
		{
			UpdateLaneReferencesJob jobData = new UpdateLaneReferencesJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PedestrianLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_PedestrianLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CarLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TrackLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_TrackLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ParkingLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ConnectionLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ConnectionLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_Lanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RW_BufferLookup, ref base.CheckedStateRef)
			};
			base.Dependency = JobChunkExtensions.Schedule(jobData, m_LanesQuery, base.Dependency);
		}
		if (m_SkipLaneQueue.IsCreated)
		{
			NativeHashMap<PathNode, PathNode> pathNodeMap = new NativeHashMap<PathNode, PathNode>(100, Allocator.TempJob);
			FillNodeMapJob jobData2 = new FillNodeMapJob
			{
				m_SkipLaneQueue = m_SkipLaneQueue,
				m_PathNodeMap = pathNodeMap
			};
			FixSkippedLanesJob jobData3 = new FixSkippedLanesJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ConnectedEdgeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_SubLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RW_ComponentLookup, ref base.CheckedStateRef),
				m_PathNodeMap = pathNodeMap,
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			JobHandle jobHandle = IJobExtensions.Schedule(jobData2, m_SkipLaneDeps);
			JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(jobData3, m_UpdatedOwnersQuery, JobHandle.CombineDependencies(jobHandle, base.Dependency));
			m_SkipLaneQueue.Dispose(jobHandle);
			pathNodeMap.Dispose(jobHandle2);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
			base.Dependency = jobHandle2;
		}
		if (!query.IsEmptyIgnoreFilter)
		{
			UpdateLaneIndicesJob jobData4 = new UpdateLaneIndicesJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_NodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Node_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_RoadType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Road_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TramTrackType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_TramTrack_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TrainTrackType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_TrainTrack_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SubLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubLane_RW_BufferTypeHandle, ref base.CheckedStateRef),
				m_SecondaryLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SecondaryLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabTrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrackLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_MasterLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_MasterLane_RW_ComponentLookup, ref base.CheckedStateRef),
				m_SlaveLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SlaveLane_RW_ComponentLookup, ref base.CheckedStateRef),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData4, query, base.Dependency);
			m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
		}
	}
```


## Nested types

- `Game.Net.LaneReferencesSystem+UpdateLaneReferencesJob`  
- `Game.Net.LaneReferencesSystem+FillNodeMapJob`  
- `Game.Net.LaneReferencesSystem+FixSkippedLanesJob`  
- `Game.Net.LaneReferencesSystem+UpdateLaneIndicesJob`  
- `Game.Net.LaneReferencesSystem+SubLaneOrder`  
- `Game.Net.LaneReferencesSystem+TypeHandle`  

