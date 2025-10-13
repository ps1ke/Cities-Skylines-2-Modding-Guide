# Game.Pathfind.LaneDataSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LaneDataSystem : Game.GameSystemBase
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Unity.Entities.EntityQuery m_LaneQuery2;
    private Game.Pathfind.LaneDataSystem+TypeHandle __TypeHandle;

    public LaneDataSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Unity.Entities.EntityQuery m_LaneQuery2`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery2;
```

- `private Game.Pathfind.LaneDataSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Pathfind.LaneDataSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LaneDataSystem()`  

```csharp
[Preserve]
	public LaneDataSystem()
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
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_LaneQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Lane>()
			},
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Game.Net.CarLane>(),
				ComponentType.ReadOnly<Game.Net.PedestrianLane>(),
				ComponentType.ReadOnly<Game.Net.TrackLane>(),
				ComponentType.ReadOnly<Game.Net.ConnectionLane>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<GarageLane>(),
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
				ComponentType.ReadOnly<Game.Net.PedestrianLane>(),
				ComponentType.ReadOnly<Game.Net.TrackLane>(),
				ComponentType.ReadOnly<Game.Net.ConnectionLane>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<GarageLane>(),
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_LaneQuery2 = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Lane>()
			},
			Any = new ComponentType[1] { ComponentType.ReadOnly<Game.Net.CarLane>() },
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<PathfindUpdated>(),
				ComponentType.ReadOnly<Lane>()
			},
			Any = new ComponentType[1] { ComponentType.ReadOnly<Game.Net.CarLane>() },
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		RequireForUpdate(m_LaneQuery);
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
		UpdateLaneDataJob jobData = new UpdateLaneDataJob
		{
			m_LaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Lane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MasterLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_MasterLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_SlaveLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LaneObjectType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_LaneObject_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CarLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_CarLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PedestrianLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_PedestrianLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TrackLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_TrackLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ConnectionLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_ConnectionLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Road_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GateData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Gate_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AttachmentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attachment_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_City_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BorderDistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_BorderDistrict_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_District_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MovingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Moving_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Car_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InvolvedInAccidenteData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_InvolvedInAccident_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AccidentSiteData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_AccidentSite_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_LaneObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedNode_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_DistrictModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_DistrictModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_TargetElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Events_TargetElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_City = m_CitySystem.City
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_LaneQuery, base.Dependency);
		if (!m_LaneQuery.IsEmptyIgnoreFilter)
		{
			UpdateLaneData2Job jobData2 = new UpdateLaneData2Job
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RW_ComponentLookup, ref base.CheckedStateRef)
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData2, m_LaneQuery2, base.Dependency);
		}
	}
```


## Nested types

- `Game.Pathfind.LaneDataSystem+UpdateLaneDataJob`  
- `Game.Pathfind.LaneDataSystem+UpdateLaneData2Job`  
- `Game.Pathfind.LaneDataSystem+TypeHandle`  

