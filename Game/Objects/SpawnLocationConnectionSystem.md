# Game.Objects.SpawnLocationConnectionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SpawnLocationConnectionSystem : Game.GameSystemBase
{
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
    private Game.Net.AirwaySystem m_AirwaySystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Game.Objects.SpawnLocationConnectionSystem+TypeHandle __TypeHandle;

    public SpawnLocationConnectionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem`  

```csharp
private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
```

- `private Game.Net.AirwaySystem m_AirwaySystem`  

```csharp
private Game.Net.AirwaySystem m_AirwaySystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem`  

```csharp
private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Game.Objects.SpawnLocationConnectionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.SpawnLocationConnectionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SpawnLocationConnectionSystem()`  

```csharp
[Preserve]
	public SpawnLocationConnectionSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_NetUpdateCollectSystem = base.World.GetOrCreateSystemManaged<Game.Net.UpdateCollectSystem>();
		m_AirwaySystem = base.World.GetOrCreateSystemManaged<AirwaySystem>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_AreaUpdateCollectSystem = base.World.GetOrCreateSystemManaged<Game.Areas.UpdateCollectSystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_UpdatedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<SpawnLocation>(),
				ComponentType.ReadOnly<Updated>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<RoadConnectionUpdated>(),
				ComponentType.ReadOnly<Event>()
			}
		});
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool flag = !m_UpdatedQuery.IsEmptyIgnoreFilter;
		if (flag || m_NetUpdateCollectSystem.netsUpdated || m_AreaUpdateCollectSystem.lotsUpdated || m_AreaUpdateCollectSystem.spacesUpdated)
		{
			NativeQueue<Entity> updatedQueue = new NativeQueue<Entity>(Allocator.TempJob);
			NativeQueue<Entity> updatedQueue2 = new NativeQueue<Entity>(Allocator.TempJob);
			NativeQueue<Entity> updatedQueue3 = new NativeQueue<Entity>(Allocator.TempJob);
			NativeQueue<Entity> updatedQueue4 = new NativeQueue<Entity>(Allocator.TempJob);
			NativeList<Entity> nativeList = new NativeList<Entity>(Allocator.TempJob);
			JobHandle jobHandle = default(JobHandle);
			if (m_NetUpdateCollectSystem.netsUpdated)
			{
				JobHandle dependencies;
				NativeList<Bounds2> updatedNetBounds = m_NetUpdateCollectSystem.GetUpdatedNetBounds(out dependencies);
				JobHandle dependencies2;
				JobHandle jobHandle2 = new FindUpdatedSpawnLocationsJob
				{
					m_Bounds = updatedNetBounds.AsDeferredJobArray(),
					m_ObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies2),
					m_SpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_SpawnLocation_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ResultQueue = updatedQueue.AsParallelWriter()
				}.Schedule(updatedNetBounds, 1, JobHandle.CombineDependencies(base.Dependency, dependencies, dependencies2));
				m_NetUpdateCollectSystem.AddNetBoundsReader(jobHandle2);
				m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle2);
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
			}
			if (m_AreaUpdateCollectSystem.lotsUpdated)
			{
				JobHandle dependencies3;
				NativeList<Bounds2> updatedLotBounds = m_AreaUpdateCollectSystem.GetUpdatedLotBounds(out dependencies3);
				JobHandle dependencies4;
				JobHandle jobHandle3 = new FindUpdatedSpawnLocationsJob
				{
					m_Bounds = updatedLotBounds.AsDeferredJobArray(),
					m_ObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies4),
					m_SpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_SpawnLocation_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ResultQueue = updatedQueue2.AsParallelWriter()
				}.Schedule(updatedLotBounds, 1, JobHandle.CombineDependencies(base.Dependency, dependencies3, dependencies4));
				m_AreaUpdateCollectSystem.AddLotBoundsReader(jobHandle3);
				m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle3);
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle3);
			}
			if (m_AreaUpdateCollectSystem.spacesUpdated)
			{
				JobHandle dependencies5;
				NativeList<Bounds2> updatedSpaceBounds = m_AreaUpdateCollectSystem.GetUpdatedSpaceBounds(out dependencies5);
				JobHandle dependencies6;
				JobHandle jobHandle4 = new FindUpdatedSpawnLocationsJob
				{
					m_Bounds = updatedSpaceBounds.AsDeferredJobArray(),
					m_ObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies6),
					m_SpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_SpawnLocation_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ResultQueue = updatedQueue3.AsParallelWriter()
				}.Schedule(updatedSpaceBounds, 1, JobHandle.CombineDependencies(base.Dependency, dependencies5, dependencies6));
				m_AreaUpdateCollectSystem.AddSpaceBoundsReader(jobHandle4);
				m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle4);
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle4);
			}
			if (flag)
			{
				JobHandle job = JobChunkExtensions.ScheduleParallel(new CheckUpdatedSpawnLocationsJob
				{
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_RoadConnectionUpdatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_RoadConnectionUpdated_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_SpawnLocations = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_SpawnLocationElement_RO_BufferLookup, ref base.CheckedStateRef),
					m_ResultQueue = updatedQueue4.AsParallelWriter()
				}, m_UpdatedQuery, base.Dependency);
				jobHandle = JobHandle.CombineDependencies(jobHandle, job);
			}
			ListUpdatedSpawnLocationsJob jobData = new ListUpdatedSpawnLocationsJob
			{
				m_UpdatedQueue1 = updatedQueue,
				m_UpdatedQueue2 = updatedQueue2,
				m_UpdatedQueue3 = updatedQueue3,
				m_UpdatedQueue4 = updatedQueue4,
				m_UpdatedList = nativeList
			};
			JobHandle dependencies7;
			JobHandle dependencies8;
			FindSpawnLocationConnectionJob jobData2 = new FindSpawnLocationConnectionJob
			{
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AttachedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_MovedLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_MovedLocation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SlaveLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectionLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ConnectionLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Lot_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabCarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabTrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrackLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabSpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnLocationData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRouteConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_SpawnLocation_RW_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnLocations = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_SpawnLocationElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_Lanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
				m_AreaTriangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
				m_Entities = nativeList.AsDeferredJobArray(),
				m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies7),
				m_AreaSearchTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies8),
				m_AirwayData = m_AirwaySystem.GetAirwayData(),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			JobHandle jobHandle5 = IJobExtensions.Schedule(jobData, jobHandle);
			JobHandle jobHandle6 = jobData2.Schedule(nativeList, 1, JobHandle.CombineDependencies(jobHandle5, dependencies7, dependencies8));
			updatedQueue.Dispose(jobHandle5);
			updatedQueue2.Dispose(jobHandle5);
			updatedQueue3.Dispose(jobHandle5);
			updatedQueue4.Dispose(jobHandle5);
			nativeList.Dispose(jobHandle6);
			m_NetSearchSystem.AddNetSearchTreeReader(jobHandle6);
			m_AreaSearchSystem.AddSearchTreeReader(jobHandle6);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle6);
			base.Dependency = jobHandle6;
		}
	}
```


## Nested types

- `Game.Objects.SpawnLocationConnectionSystem+FindUpdatedSpawnLocationsJob`  
- `Game.Objects.SpawnLocationConnectionSystem+CheckUpdatedSpawnLocationsJob`  
- `Game.Objects.SpawnLocationConnectionSystem+ListUpdatedSpawnLocationsJob`  
- `Game.Objects.SpawnLocationConnectionSystem+FindSpawnLocationConnectionJob`  
- `Game.Objects.SpawnLocationConnectionSystem+TypeHandle`  

