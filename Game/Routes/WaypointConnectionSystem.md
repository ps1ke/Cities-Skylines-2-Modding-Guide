# Game.Routes.WaypointConnectionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaypointConnectionSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Net.AirwaySystem m_AirwaySystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Routes.SearchSystem m_RouteSearchSystem;
    private Unity.Entities.EntityQuery m_WaypointQuery;
    private Unity.Entities.EntityArchetype m_PathTargetEventArchetype;
    private Game.Routes.WaypointConnectionSystem+TypeHandle __TypeHandle;

    public WaypointConnectionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem`  

```csharp
private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Net.AirwaySystem m_AirwaySystem`  

```csharp
private Game.Net.AirwaySystem m_AirwaySystem;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem`  

```csharp
private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Routes.SearchSystem m_RouteSearchSystem`  

```csharp
private Game.Routes.SearchSystem m_RouteSearchSystem;
```

- `private Unity.Entities.EntityQuery m_WaypointQuery`  

```csharp
private Unity.Entities.EntityQuery m_WaypointQuery;
```

- `private Unity.Entities.EntityArchetype m_PathTargetEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_PathTargetEventArchetype;
```

- `private Game.Routes.WaypointConnectionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Routes.WaypointConnectionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaypointConnectionSystem()`  

```csharp
[Preserve]
	public WaypointConnectionSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_NetUpdateCollectSystem = base.World.GetOrCreateSystemManaged<Game.Net.UpdateCollectSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_AirwaySystem = base.World.GetOrCreateSystemManaged<AirwaySystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_AreaUpdateCollectSystem = base.World.GetOrCreateSystemManaged<Game.Areas.UpdateCollectSystem>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_RouteSearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_WaypointQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Updated>() },
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Waypoint>(),
				ComponentType.ReadOnly<AccessLane>(),
				ComponentType.ReadOnly<RouteLane>(),
				ComponentType.ReadOnly<ConnectedRoute>()
			},
			None = new ComponentType[0]
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() },
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Waypoint>(),
				ComponentType.ReadOnly<AccessLane>(),
				ComponentType.ReadOnly<RouteLane>(),
				ComponentType.ReadOnly<ConnectedRoute>()
			},
			None = new ComponentType[0]
		});
		m_PathTargetEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<PathTargetMoved>());
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
		if (!m_WaypointQuery.IsEmptyIgnoreFilter || m_NetUpdateCollectSystem.netsUpdated || m_AreaUpdateCollectSystem.lotsUpdated)
		{
			NativeList<Entity> nativeList = new NativeList<Entity>(Allocator.TempJob);
			JobHandle jobHandle = default(JobHandle);
			if (!m_WaypointQuery.IsEmptyIgnoreFilter)
			{
				jobHandle = JobChunkExtensions.Schedule(new UpdateWaypointReferencesJob
				{
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_ConnectedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_CreatedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_AccessLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_AccessLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_RouteLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_RouteLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_ConnectedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentLookup, ref base.CheckedStateRef),
					m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ConnectedRoutes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_ConnectedRoute_RW_BufferLookup, ref base.CheckedStateRef),
					m_UpdatedList = nativeList
				}, m_WaypointQuery, base.Dependency);
			}
			JobHandle jobHandle2 = jobHandle;
			if (m_NetUpdateCollectSystem.netsUpdated)
			{
				NativeQueue<Entity> updatedQueue = new NativeQueue<Entity>(Allocator.TempJob);
				JobHandle dependencies;
				NativeList<Bounds2> updatedNetBounds = m_NetUpdateCollectSystem.GetUpdatedNetBounds(out dependencies);
				JobHandle dependencies2;
				JobHandle dependencies3;
				FindUpdatedWaypointsJob jobData = new FindUpdatedWaypointsJob
				{
					m_Bounds = updatedNetBounds.AsDeferredJobArray(),
					m_RouteSearchTree = m_RouteSearchSystem.GetSearchTree(readOnly: true, out dependencies2),
					m_ObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies3),
					m_WaypointData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Waypoint_RO_ComponentLookup, ref base.CheckedStateRef),
					m_AccessLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_AccessLane_RO_ComponentLookup, ref base.CheckedStateRef),
					m_RouteLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_RouteLane_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ResultQueue = updatedQueue.AsParallelWriter()
				};
				DequeUpdatedWaypointsJob jobData2 = new DequeUpdatedWaypointsJob
				{
					m_UpdatedQueue = updatedQueue,
					m_UpdatedList = nativeList
				};
				JobHandle job = JobHandle.CombineDependencies(dependencies, dependencies2, dependencies3);
				JobHandle jobHandle3 = jobData.Schedule(updatedNetBounds, 1, JobHandle.CombineDependencies(base.Dependency, job));
				jobHandle2 = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(jobHandle2, jobHandle3));
				updatedQueue.Dispose(jobHandle2);
				m_NetUpdateCollectSystem.AddNetBoundsReader(jobHandle3);
				m_RouteSearchSystem.AddSearchTreeReader(jobHandle3);
				m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle3);
			}
			if (m_AreaUpdateCollectSystem.lotsUpdated)
			{
				NativeQueue<Entity> updatedQueue2 = new NativeQueue<Entity>(Allocator.TempJob);
				JobHandle dependencies4;
				NativeList<Bounds2> updatedLotBounds = m_AreaUpdateCollectSystem.GetUpdatedLotBounds(out dependencies4);
				JobHandle dependencies5;
				JobHandle dependencies6;
				FindUpdatedWaypointsJob jobData3 = new FindUpdatedWaypointsJob
				{
					m_Bounds = updatedLotBounds.AsDeferredJobArray(),
					m_RouteSearchTree = m_RouteSearchSystem.GetSearchTree(readOnly: true, out dependencies5),
					m_ObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies6),
					m_WaypointData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Waypoint_RO_ComponentLookup, ref base.CheckedStateRef),
					m_AccessLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_AccessLane_RO_ComponentLookup, ref base.CheckedStateRef),
					m_RouteLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_RouteLane_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ResultQueue = updatedQueue2.AsParallelWriter()
				};
				DequeUpdatedWaypointsJob jobData4 = new DequeUpdatedWaypointsJob
				{
					m_UpdatedQueue = updatedQueue2,
					m_UpdatedList = nativeList
				};
				JobHandle job2 = JobHandle.CombineDependencies(dependencies4, dependencies5, dependencies6);
				JobHandle jobHandle4 = jobData3.Schedule(updatedLotBounds, 1, JobHandle.CombineDependencies(base.Dependency, job2));
				jobHandle2 = IJobExtensions.Schedule(jobData4, JobHandle.CombineDependencies(jobHandle2, jobHandle4));
				updatedQueue2.Dispose(jobHandle2);
				m_AreaUpdateCollectSystem.AddLotBoundsReader(jobHandle4);
				m_RouteSearchSystem.AddSearchTreeReader(jobHandle4);
				m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle4);
			}
			NativeQueue<PathTargetInfo> pathTargetInfo = new NativeQueue<PathTargetInfo>(Allocator.TempJob);
			RemoveDuplicatedWaypointsJob jobData5 = new RemoveDuplicatedWaypointsJob
			{
				m_UpdatedList = nativeList
			};
			JobHandle dependencies7;
			JobHandle dependencies8;
			FindWaypointConnectionsJob jobData6 = new FindWaypointConnectionsJob
			{
				m_WaypointData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Waypoint_RO_ComponentLookup, ref base.CheckedStateRef),
				m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabSpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnLocationData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabCarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabTrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrackLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PedestrianLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_PedestrianLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TrackLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_TrackLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_MasterLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_MasterLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SlaveLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectionLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ConnectionLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NetOutsideConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NetElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_StartNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EndNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ObjectOutsideConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AttachedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Lot_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SurfaceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Surface_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Segments = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteSegment_RO_BufferLookup, ref base.CheckedStateRef),
				m_Lanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
				m_AreaTriangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
				m_AccessLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_AccessLane_RW_ComponentLookup, ref base.CheckedStateRef),
				m_RouteLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_RouteLane_RW_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Connected_RW_ComponentLookup, ref base.CheckedStateRef),
				m_PositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RW_ComponentLookup, ref base.CheckedStateRef),
				m_UpdatedList = nativeList.AsDeferredJobArray(),
				m_AirwayData = m_AirwaySystem.GetAirwayData(),
				m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies7),
				m_AreaSearchTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies8),
				m_PathTargetEventArchetype = m_PathTargetEventArchetype,
				m_PathTargetInfo = pathTargetInfo.AsParallelWriter(),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			ClearPathTargetsJob jobData7 = new ClearPathTargetsJob
			{
				m_PathTargetInfo = pathTargetInfo,
				m_PathTargetsData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_PathTargets_RW_ComponentLookup, ref base.CheckedStateRef)
			};
			JobHandle jobHandle5 = IJobParallelForDeferExtensions.Schedule(dependsOn: JobHandle.CombineDependencies(IJobExtensions.Schedule(jobData5, jobHandle2), dependencies7, dependencies8), jobData: jobData6, list: nativeList, innerloopBatchCount: 1);
			JobHandle jobHandle6 = IJobExtensions.Schedule(jobData7, jobHandle5);
			nativeList.Dispose(jobHandle5);
			pathTargetInfo.Dispose(jobHandle6);
			m_NetSearchSystem.AddNetSearchTreeReader(jobHandle5);
			m_AreaSearchSystem.AddSearchTreeReader(jobHandle5);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle5);
			base.Dependency = jobHandle6;
		}
	}
```


## Nested types

- `Game.Routes.WaypointConnectionSystem+UpdateWaypointReferencesJob`  
- `Game.Routes.WaypointConnectionSystem+FindUpdatedWaypointsJob`  
- `Game.Routes.WaypointConnectionSystem+DequeUpdatedWaypointsJob`  
- `Game.Routes.WaypointConnectionSystem+RemoveDuplicatedWaypointsJob`  
- `Game.Routes.WaypointConnectionSystem+FindWaypointConnectionsJob`  
- `Game.Routes.WaypointConnectionSystem+PathTargetInfo`  
- `Game.Routes.WaypointConnectionSystem+ClearPathTargetsJob`  
- `Game.Routes.WaypointConnectionSystem+TypeHandle`  

