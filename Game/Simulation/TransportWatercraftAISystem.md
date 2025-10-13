# Game.Simulation.TransportWatercraftAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TransportWatercraftAISystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Unity.Entities.EntityArchetype m_TransportVehicleRequestArchetype;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Game.Simulation.TransportBoardingHelpers+BoardingLookupData m_BoardingLookupData;
    private Game.Simulation.TransportWatercraftAISystem+TypeHandle __TypeHandle;

    public TransportWatercraftAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem`  

```csharp
private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Unity.Entities.EntityArchetype m_TransportVehicleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_TransportVehicleRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
```

- `private Game.Simulation.TransportBoardingHelpers+BoardingLookupData m_BoardingLookupData`  

```csharp
private Game.Simulation.TransportBoardingHelpers+BoardingLookupData m_BoardingLookupData;
```

- `private Game.Simulation.TransportWatercraftAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TransportWatercraftAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TransportWatercraftAISystem()`  

```csharp
[Preserve]
	public TransportWatercraftAISystem()
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

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 16;
	}
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return 8;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_PathfindSetupSystem = base.World.GetOrCreateSystemManaged<PathfindSetupSystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_AchievementTriggerSystem = base.World.GetOrCreateSystemManaged<AchievementTriggerSystem>();
		m_BoardingLookupData = new TransportBoardingHelpers.BoardingLookupData(this);
		m_VehicleQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[5]
			{
				ComponentType.ReadWrite<WatercraftCurrentLane>(),
				ComponentType.ReadOnly<Owner>(),
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadWrite<PathOwner>(),
				ComponentType.ReadWrite<Target>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadWrite<Game.Vehicles.CargoTransport>(),
				ComponentType.ReadWrite<Game.Vehicles.PublicTransport>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<TripSource>(),
				ComponentType.ReadOnly<OutOfControl>()
			}
		});
		m_TransportVehicleRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<ServiceRequest>(), ComponentType.ReadWrite<TransportVehicleRequest>(), ComponentType.ReadWrite<RequestGroup>());
		m_HandleRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<HandleRequest>(), ComponentType.ReadWrite<Event>());
		RequireForUpdate(m_VehicleQuery);
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
		TransportBoardingHelpers.BoardingData boardingData = new TransportBoardingHelpers.BoardingData(Allocator.TempJob);
		m_BoardingLookupData.Update(this);
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new TransportWatercraftTickJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UnspawnedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Unspawned_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentRouteType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Routes_CurrentRoute_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PassengerType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_Passenger_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CargoTransportType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_CargoTransport_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PublicTransportType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_PublicTransport_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WatercraftType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Watercraft_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentLaneType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_WatercraftCurrentLane_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TargetType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Target_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PathOwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Pathfind_PathOwner_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OdometerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Vehicles_Odometer_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WatercraftNavigationLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_WatercraftNavigationLane_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_ServiceDispatchType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Simulation_ServiceDispatch_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathInformationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransportVehicleRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_TransportVehicleRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabWatercraftData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WatercraftData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PublicTransportVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PublicTransportVehicleData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CargoTransportVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CargoTransportVehicleData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaypointData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Waypoint_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConnectedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Connected_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BoardingVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_BoardingVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RouteLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_RouteLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RouteColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Color_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StorageCompanyData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_StorageCompany_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransportStationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_TransportStation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SlaveLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RouteWaypoints = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Routes_RouteWaypoint_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
			m_PathElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_PathElement_RW_BufferLookup, ref base.CheckedStateRef),
			m_LoadingResources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LoadingResources_RW_BufferLookup, ref base.CheckedStateRef),
			m_SimulationFrameIndex = m_SimulationSystem.frameIndex,
			m_TransportVehicleRequestArchetype = m_TransportVehicleRequestArchetype,
			m_HandleRequestArchetype = m_HandleRequestArchetype,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_PathfindQueue = m_PathfindSetupSystem.GetQueue(this, 64).AsParallelWriter(),
			m_BoardingData = boardingData.ToConcurrent()
		}, m_VehicleQuery, base.Dependency);
		JobHandle jobHandle2 = boardingData.ScheduleBoarding(this, m_CityStatisticsSystem, m_AchievementTriggerSystem, m_BoardingLookupData, m_SimulationSystem.frameIndex, jobHandle);
		boardingData.Dispose(jobHandle2);
		m_PathfindSetupSystem.AddQueueWriter(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		base.Dependency = jobHandle2;
	}
```


## Nested types

- `Game.Simulation.TransportWatercraftAISystem+TransportWatercraftTickJob`  
- `Game.Simulation.TransportWatercraftAISystem+TypeHandle`  

