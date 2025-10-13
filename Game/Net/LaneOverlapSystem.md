# Game.Net.LaneOverlapSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LaneOverlapSystem : Game.GameSystemBase
{
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Unity.Entities.EntityQuery m_UpdatedOwnersQuery;
    private Unity.Entities.EntityQuery m_UpdatedLanesQuery;
    private Unity.Entities.EntityQuery m_AllOwnersQuery;
    private Unity.Entities.EntityQuery m_AllLanesQuery;
    private System.Boolean m_Loaded;
    private Game.Net.LaneOverlapSystem+TypeHandle __TypeHandle;

    public LaneOverlapSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedOwnersQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedOwnersQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedLanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedLanesQuery;
```

- `private Unity.Entities.EntityQuery m_AllOwnersQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllOwnersQuery;
```

- `private Unity.Entities.EntityQuery m_AllLanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllLanesQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Net.LaneOverlapSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.LaneOverlapSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LaneOverlapSystem()`  

```csharp
[Preserve]
	public LaneOverlapSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_UpdatedOwnersQuery = GetEntityQuery(ComponentType.ReadOnly<SubLane>(), ComponentType.ReadOnly<Updated>(), ComponentType.Exclude<Deleted>());
		m_UpdatedLanesQuery = GetEntityQuery(ComponentType.ReadOnly<Lane>(), ComponentType.ReadOnly<Updated>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<SecondaryLane>());
		m_AllOwnersQuery = GetEntityQuery(ComponentType.ReadOnly<SubLane>(), ComponentType.Exclude<Deleted>());
		m_AllLanesQuery = GetEntityQuery(ComponentType.ReadOnly<Lane>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<SecondaryLane>());
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
		bool loaded = GetLoaded();
		EntityQuery entityQuery = (loaded ? m_AllOwnersQuery : m_UpdatedOwnersQuery);
		EntityQuery query = (loaded ? m_AllLanesQuery : m_UpdatedLanesQuery);
		if (!entityQuery.IsEmptyIgnoreFilter)
		{
			int capacity = query.CalculateEntityCount();
			NativeParallelMultiHashMap<PathNode, LaneSourceData> sourceMap = new NativeParallelMultiHashMap<PathNode, LaneSourceData>(capacity, Allocator.TempJob);
			NativeParallelMultiHashMap<PathNode, LaneTargetData> targetMap = new NativeParallelMultiHashMap<PathNode, LaneTargetData>(capacity, Allocator.TempJob);
			JobHandle outJobHandle;
			NativeList<Entity> nativeList = entityQuery.ToEntityListAsync(Allocator.TempJob, out outJobHandle);
			NativeQueue<OverlapData> extraOverlaps = new NativeQueue<OverlapData>(Allocator.TempJob);
			if (!loaded)
			{
				outJobHandle = IJobExtensions.Schedule(new AddNonUpdatedEdgesJob
				{
					m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
					m_Entities = nativeList
				}, JobHandle.CombineDependencies(outJobHandle, base.Dependency));
			}
			UpdateLaneOverlapsJob jobData = new UpdateLaneOverlapsJob
			{
				m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PedestrianLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_PedestrianLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SecondaryLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SecondaryLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ParkingLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabTrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrackLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_NodeLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_NodeLane_RW_ComponentLookup, ref base.CheckedStateRef),
				m_Overlaps = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneOverlap_RW_BufferLookup, ref base.CheckedStateRef),
				m_Entities = nativeList.AsDeferredJobArray(),
				m_LeftHandTraffic = m_CityConfigurationSystem.leftHandTraffic,
				m_UpdateAll = loaded,
				m_ExtraOverlaps = extraOverlaps.AsParallelWriter()
			};
			ApplyExtraOverlapsJob jobData2 = new ApplyExtraOverlapsJob
			{
				m_NodeLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_NodeLane_RW_ComponentLookup, ref base.CheckedStateRef),
				m_Overlaps = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneOverlap_RW_BufferLookup, ref base.CheckedStateRef),
				m_ExtraOverlaps = extraOverlaps
			};
			SortLaneOverlapsJob jobData3 = new SortLaneOverlapsJob
			{
				m_SecondaryLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SecondaryLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_Overlaps = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneOverlap_RW_BufferLookup, ref base.CheckedStateRef),
				m_Entities = nativeList.AsDeferredJobArray()
			};
			CollectLaneDirectionsJob jobData4 = new CollectLaneDirectionsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_LaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Lane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EdgeLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CarLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TrackLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_TrackLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SlaveLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_MasterLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_MasterLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ConnectionLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ConnectionLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SourceMap = sourceMap.AsParallelWriter(),
				m_TargetMap = targetMap.AsParallelWriter()
			};
			UpdateLaneFlagsJob jobData5 = new UpdateLaneFlagsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_LaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Lane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_MasterLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_MasterLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_LaneOverlapType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_LaneOverlap_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OutsideConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_EdgeLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_NodeLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_NodeLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CarLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_CarLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TrackLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_TrackLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SlaveLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_SlaveLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LaneOverlapData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneOverlap_RO_BufferLookup, ref base.CheckedStateRef),
				m_SourceMap = sourceMap,
				m_TargetMap = targetMap
			};
			JobHandle dependsOn = jobData.Schedule(nativeList, 1, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
			JobHandle jobHandle = IJobExtensions.Schedule(jobData2, dependsOn);
			JobHandle jobHandle2 = jobData3.Schedule(nativeList, 1, jobHandle);
			JobHandle jobHandle3 = JobChunkExtensions.ScheduleParallel(dependsOn: JobHandle.CombineDependencies(jobHandle2, JobChunkExtensions.ScheduleParallel(jobData4, query, base.Dependency)), jobData: jobData5, query: query);
			sourceMap.Dispose(jobHandle3);
			targetMap.Dispose(jobHandle3);
			nativeList.Dispose(jobHandle2);
			extraOverlaps.Dispose(jobHandle);
			base.Dependency = jobHandle3;
		}
	}
```


## Nested types

- `Game.Net.LaneOverlapSystem+AddNonUpdatedEdgesJob`  
- `Game.Net.LaneOverlapSystem+UpdateLaneFlagsJob`  
- `Game.Net.LaneOverlapSystem+LaneSourceData`  
- `Game.Net.LaneOverlapSystem+LaneTargetData`  
- `Game.Net.LaneOverlapSystem+CollectLaneDirectionsJob`  
- `Game.Net.LaneOverlapSystem+OverlapData`  
- `Game.Net.LaneOverlapSystem+ApplyExtraOverlapsJob`  
- `Game.Net.LaneOverlapSystem+SortLaneOverlapsJob`  
- `Game.Net.LaneOverlapSystem+UpdateLaneOverlapsJob`  
- `Game.Net.LaneOverlapSystem+TypeHandle`  

