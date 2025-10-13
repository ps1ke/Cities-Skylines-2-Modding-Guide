# Game.Pathfind.RoutesModifiedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RoutesModifiedSystem : Game.GameSystemBase
{
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Unity.Entities.EntityQuery m_CreatedSubElementQuery;
    private Unity.Entities.EntityQuery m_UpdatedSubElementQuery;
    private Unity.Entities.EntityQuery m_DeletedSubElementQuery;
    private Unity.Entities.EntityQuery m_AllSubElementQuery;
    private System.Boolean m_Loaded;
    private Game.Pathfind.RoutesModifiedSystem+TypeHandle __TypeHandle;

    public RoutesModifiedSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Unity.Entities.EntityQuery m_CreatedSubElementQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedSubElementQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedSubElementQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedSubElementQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedSubElementQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedSubElementQuery;
```

- `private Unity.Entities.EntityQuery m_AllSubElementQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllSubElementQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Pathfind.RoutesModifiedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Pathfind.RoutesModifiedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RoutesModifiedSystem()`  

```csharp
[Preserve]
	public RoutesModifiedSystem()
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
		m_PathfindQueueSystem = base.World.GetOrCreateSystemManaged<PathfindQueueSystem>();
		m_CreatedSubElementQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Created>() },
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<AccessLane>(),
				ComponentType.ReadOnly<RouteLane>(),
				ComponentType.ReadOnly<Game.Routes.Segment>(),
				ComponentType.ReadOnly<Game.Objects.SpawnLocation>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Routes.MailBox>(),
				ComponentType.ReadOnly<LivePath>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_UpdatedSubElementQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Updated>() },
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<AccessLane>(),
				ComponentType.ReadOnly<RouteLane>(),
				ComponentType.ReadOnly<Game.Routes.Segment>(),
				ComponentType.ReadOnly<Game.Objects.SpawnLocation>()
			},
			None = new ComponentType[5]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Game.Routes.MailBox>(),
				ComponentType.ReadOnly<LivePath>(),
				ComponentType.ReadOnly<Temp>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<PathfindUpdated>() },
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<AccessLane>(),
				ComponentType.ReadOnly<RouteLane>(),
				ComponentType.ReadOnly<Game.Routes.Segment>(),
				ComponentType.ReadOnly<Game.Objects.SpawnLocation>()
			},
			None = new ComponentType[5]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Game.Routes.MailBox>(),
				ComponentType.ReadOnly<LivePath>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_DeletedSubElementQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() },
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<AccessLane>(),
				ComponentType.ReadOnly<RouteLane>(),
				ComponentType.ReadOnly<Game.Routes.Segment>(),
				ComponentType.ReadOnly<Game.Objects.SpawnLocation>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Routes.MailBox>(),
				ComponentType.ReadOnly<LivePath>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_AllSubElementQuery = GetEntityQuery(new EntityQueryDesc
		{
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<AccessLane>(),
				ComponentType.ReadOnly<RouteLane>(),
				ComponentType.ReadOnly<Game.Routes.Segment>(),
				ComponentType.ReadOnly<Game.Objects.SpawnLocation>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Game.Routes.MailBox>(),
				ComponentType.ReadOnly<LivePath>(),
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Deleted>()
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
		EntityQuery entityQuery;
		int num;
		if (GetLoaded())
		{
			entityQuery = m_AllSubElementQuery;
			num = 0;
		}
		else
		{
			entityQuery = m_CreatedSubElementQuery;
			num = m_UpdatedSubElementQuery.CalculateEntityCount();
		}
		int num2 = entityQuery.CalculateEntityCount();
		int num3 = m_DeletedSubElementQuery.CalculateEntityCount();
		if (num2 != 0 || num != 0 || num3 != 0)
		{
			JobHandle jobHandle = base.Dependency;
			if (num2 != 0)
			{
				CreateAction action = new CreateAction(num2, Allocator.Persistent);
				JobHandle outJobHandle;
				NativeList<ArchetypeChunk> chunks = entityQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
				JobHandle jobHandle2 = IJobExtensions.Schedule(new AddPathEdgeJob
				{
					m_Chunks = chunks,
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_WaypointType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Waypoint_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_PositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Position_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_AccessLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_AccessLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_RouteLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_RouteLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_SegmentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Segment_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_TaxiStandType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_TaxiStand_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_TakeoffLocationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_TakeoffLocation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_ConnectedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_RouteInfoType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_RouteInfo_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_SpawnLocationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_SpawnLocation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_WaitingPassengersType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_WaitingPassengers_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_PositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef),
					m_TransportStopData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_TransportStop_RO_ComponentLookup, ref base.CheckedStateRef),
					m_TransportLineData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_TransportLine_RO_ComponentLookup, ref base.CheckedStateRef),
					m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
					m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
					m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
					m_MasterLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_MasterLane_RO_ComponentLookup, ref base.CheckedStateRef),
					m_Waypoints = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
					m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
					m_NetLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabTransportLineData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportLineData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabRouteConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabSpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnLocationData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_TransportPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindTransportData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PedestrianPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindPedestrianData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_CarPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindCarData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_TrackPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindTrackData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ConnectionPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_Actions = action.m_CreateData
				}, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
				chunks.Dispose(jobHandle2);
				m_PathfindQueueSystem.Enqueue(action, jobHandle2);
			}
			if (num != 0)
			{
				UpdateAction action2 = new UpdateAction(num, Allocator.Persistent);
				JobHandle outJobHandle2;
				NativeList<ArchetypeChunk> chunks2 = m_UpdatedSubElementQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle2);
				JobHandle jobHandle3 = IJobExtensions.Schedule(new UpdatePathEdgeJob
				{
					m_Chunks = chunks2,
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_WaypointType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Waypoint_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_PositionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Position_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_AccessLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_AccessLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_RouteLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_RouteLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_SegmentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Segment_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_TaxiStandType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_TaxiStand_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_TakeoffLocationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_TakeoffLocation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_ConnectedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_RouteInfoType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_RouteInfo_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_SpawnLocationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_SpawnLocation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_WaitingPassengersType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_WaitingPassengers_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_PositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Position_RO_ComponentLookup, ref base.CheckedStateRef),
					m_TransportStopData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_TransportStop_RO_ComponentLookup, ref base.CheckedStateRef),
					m_TransportLineData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_TransportLine_RO_ComponentLookup, ref base.CheckedStateRef),
					m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
					m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
					m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
					m_MasterLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_MasterLane_RO_ComponentLookup, ref base.CheckedStateRef),
					m_Waypoints = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
					m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
					m_NetLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabTransportLineData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportLineData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabRouteConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RouteConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PrefabSpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnLocationData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_TransportPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindTransportData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PedestrianPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindPedestrianData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_CarPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindCarData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_TrackPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindTrackData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ConnectionPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_Actions = action2.m_UpdateData
				}, JobHandle.CombineDependencies(base.Dependency, outJobHandle2));
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle3);
				chunks2.Dispose(jobHandle3);
				m_PathfindQueueSystem.Enqueue(action2, jobHandle3);
			}
			if (num3 != 0)
			{
				DeleteAction action3 = new DeleteAction(num3, Allocator.Persistent);
				JobHandle outJobHandle3;
				NativeList<ArchetypeChunk> chunks3 = m_DeletedSubElementQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle3);
				JobHandle jobHandle4 = IJobExtensions.Schedule(new RemovePathEdgeJob
				{
					m_Chunks = chunks3,
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_Actions = action3.m_DeleteData
				}, JobHandle.CombineDependencies(base.Dependency, outJobHandle3));
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle4);
				chunks3.Dispose(jobHandle4);
				m_PathfindQueueSystem.Enqueue(action3, jobHandle4);
			}
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Pathfind.RoutesModifiedSystem+AddPathEdgeJob`  
- `Game.Pathfind.RoutesModifiedSystem+UpdatePathEdgeJob`  
- `Game.Pathfind.RoutesModifiedSystem+RemovePathEdgeJob`  
- `Game.Pathfind.RoutesModifiedSystem+TypeHandle`  

