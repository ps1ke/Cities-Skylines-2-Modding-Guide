# Game.Pathfind.LanesModifiedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LanesModifiedSystem : Game.GameSystemBase
{
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Unity.Entities.EntityQuery m_CreatedLanesQuery;
    private Unity.Entities.EntityQuery m_UpdatedLanesQuery;
    private Unity.Entities.EntityQuery m_DeletedLanesQuery;
    private Unity.Entities.EntityQuery m_AllLanesQuery;
    private System.Boolean m_Loaded;
    private Game.Pathfind.LanesModifiedSystem+TypeHandle __TypeHandle;

    public LanesModifiedSystem();

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

- `private Unity.Entities.EntityQuery m_CreatedLanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedLanesQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedLanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedLanesQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedLanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedLanesQuery;
```

- `private Unity.Entities.EntityQuery m_AllLanesQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllLanesQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Pathfind.LanesModifiedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Pathfind.LanesModifiedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LanesModifiedSystem()`  

```csharp
[Preserve]
	public LanesModifiedSystem()
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
		m_CreatedLanesQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Lane>()
			},
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Game.Net.CarLane>(),
				ComponentType.ReadOnly<Game.Net.ParkingLane>(),
				ComponentType.ReadOnly<Game.Net.PedestrianLane>(),
				ComponentType.ReadOnly<Game.Net.ConnectionLane>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<SlaveLane>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Lane>()
			},
			Any = new ComponentType[1] { ComponentType.ReadOnly<Game.Net.TrackLane>() },
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_UpdatedLanesQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Lane>()
			},
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Game.Net.CarLane>(),
				ComponentType.ReadOnly<Game.Net.ParkingLane>(),
				ComponentType.ReadOnly<Game.Net.PedestrianLane>(),
				ComponentType.ReadOnly<Game.Net.ConnectionLane>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<SlaveLane>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Lane>()
			},
			Any = new ComponentType[1] { ComponentType.ReadOnly<Game.Net.TrackLane>() },
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<PathfindUpdated>(),
				ComponentType.ReadOnly<Lane>()
			},
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Game.Net.CarLane>(),
				ComponentType.ReadOnly<Game.Net.ParkingLane>(),
				ComponentType.ReadOnly<Game.Net.PedestrianLane>(),
				ComponentType.ReadOnly<Game.Net.ConnectionLane>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<SlaveLane>()
			}
		});
		m_DeletedLanesQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Lane>()
			},
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Game.Net.CarLane>(),
				ComponentType.ReadOnly<Game.Net.ParkingLane>(),
				ComponentType.ReadOnly<Game.Net.PedestrianLane>(),
				ComponentType.ReadOnly<Game.Net.ConnectionLane>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<SlaveLane>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Lane>()
			},
			Any = new ComponentType[1] { ComponentType.ReadOnly<Game.Net.TrackLane>() },
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_AllLanesQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Lane>() },
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Game.Net.CarLane>(),
				ComponentType.ReadOnly<Game.Net.ParkingLane>(),
				ComponentType.ReadOnly<Game.Net.PedestrianLane>(),
				ComponentType.ReadOnly<Game.Net.ConnectionLane>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<SlaveLane>(),
				ComponentType.ReadOnly<Deleted>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Lane>() },
			Any = new ComponentType[1] { ComponentType.ReadOnly<Game.Net.TrackLane>() },
			None = new ComponentType[2]
			{
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
			entityQuery = m_AllLanesQuery;
			num = 0;
		}
		else
		{
			entityQuery = m_CreatedLanesQuery;
			num = m_UpdatedLanesQuery.CalculateEntityCount();
		}
		int num2 = entityQuery.CalculateEntityCount();
		int num3 = m_DeletedLanesQuery.CalculateEntityCount();
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
					m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
					m_DensityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Density_RO_ComponentLookup, ref base.CheckedStateRef),
					m_NetLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ParkingLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PedestrianPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindPedestrianData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_CarPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindCarData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_TrackPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindTrackData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_TransportPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindTransportData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ConnectionPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_LaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Lane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_SlaveLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_CarLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_EdgeLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_TrackLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_TrackLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_ParkingLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_PedestrianLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_PedestrianLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_ConnectionLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ConnectionLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_GarageLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_GarageLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_LaneConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_LaneConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_OutsideConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_OutsideConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
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
				NativeList<ArchetypeChunk> chunks2 = m_UpdatedLanesQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle2);
				JobHandle jobHandle3 = IJobExtensions.Schedule(new UpdatePathEdgeJob
				{
					m_Chunks = chunks2,
					m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
					m_DensityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Density_RO_ComponentLookup, ref base.CheckedStateRef),
					m_NetLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ParkingLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PedestrianPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindPedestrianData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_CarPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindCarData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_TrackPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindTrackData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_TransportPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindTransportData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ConnectionPathfindData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PathfindConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_LaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Lane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_SlaveLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_CarLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_EdgeLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_TrackLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_TrackLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_ParkingLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_PedestrianLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_PedestrianLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_ConnectionLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ConnectionLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_GarageLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_GarageLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_LaneConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_LaneConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_OutsideConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_OutsideConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
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
				NativeList<ArchetypeChunk> chunks3 = m_DeletedLanesQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle3);
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

- `Game.Pathfind.LanesModifiedSystem+AddPathEdgeJob`  
- `Game.Pathfind.LanesModifiedSystem+UpdatePathEdgeJob`  
- `Game.Pathfind.LanesModifiedSystem+RemovePathEdgeJob`  
- `Game.Pathfind.LanesModifiedSystem+TypeHandle`  

