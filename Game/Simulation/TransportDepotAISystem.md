# Game.Simulation.TransportDepotAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TransportDepotAISystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
    private Unity.Entities.EntityQuery m_EventPrefabQuery;
    private Unity.Entities.EntityArchetype m_TransportVehicleRequestArchetype;
    private Unity.Entities.EntityArchetype m_TaxiRequestArchetype;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingTaxiAddTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingBusAddTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrainAddTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrainControllerAddTypes;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData;
    private Game.Simulation.TransportDepotAISystem+TypeHandle __TypeHandle;

    public TransportDepotAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.EntityQuery m_VehiclePrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehiclePrefabQuery;
```

- `private Unity.Entities.EntityQuery m_EventPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventPrefabQuery;
```

- `private Unity.Entities.EntityArchetype m_TransportVehicleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_TransportVehicleRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_TaxiRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_TaxiRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingTaxiAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingTaxiAddTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingBusAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingBusAddTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrainAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrainAddTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrainControllerAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrainControllerAddTypes;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData`  

```csharp
private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData;
```

- `private Game.Simulation.TransportDepotAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TransportDepotAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TransportDepotAISystem()`  

```csharp
[Preserve]
	public TransportDepotAISystem()
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
		return 256;
	}
```

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateOffset(SystemUpdatePhase phase)
	{
		return 32;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_TransportVehicleSelectData = new TransportVehicleSelectData(this);
		m_BuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.TransportDepot>(), ComponentType.ReadOnly<ServiceDispatch>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_VehiclePrefabQuery = GetEntityQuery(TransportVehicleSelectData.GetEntityQueryDesc());
		m_EventPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<VehicleLaunchData>(), ComponentType.ReadOnly<PrefabData>(), ComponentType.Exclude<Locked>());
		m_TransportVehicleRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<ServiceRequest>(), ComponentType.ReadWrite<TransportVehicleRequest>(), ComponentType.ReadWrite<RequestGroup>());
		m_TaxiRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<ServiceRequest>(), ComponentType.ReadWrite<TaxiRequest>(), ComponentType.ReadWrite<RequestGroup>());
		m_HandleRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<HandleRequest>(), ComponentType.ReadWrite<Game.Common.Event>());
		m_ParkedToMovingRemoveTypes = new ComponentTypeSet(ComponentType.ReadWrite<ParkedCar>(), ComponentType.ReadWrite<ParkedTrain>(), ComponentType.ReadWrite<Stopped>());
		m_ParkedToMovingTaxiAddTypes = new ComponentTypeSet(new ComponentType[13]
		{
			ComponentType.ReadWrite<Moving>(),
			ComponentType.ReadWrite<TransformFrame>(),
			ComponentType.ReadWrite<InterpolatedTransform>(),
			ComponentType.ReadWrite<CarNavigation>(),
			ComponentType.ReadWrite<CarNavigationLane>(),
			ComponentType.ReadWrite<CarCurrentLane>(),
			ComponentType.ReadWrite<PathOwner>(),
			ComponentType.ReadWrite<Target>(),
			ComponentType.ReadWrite<Blocker>(),
			ComponentType.ReadWrite<PathElement>(),
			ComponentType.ReadWrite<ServiceDispatch>(),
			ComponentType.ReadWrite<Swaying>(),
			ComponentType.ReadWrite<Updated>()
		});
		m_ParkedToMovingBusAddTypes = new ComponentTypeSet(new ComponentType[14]
		{
			ComponentType.ReadWrite<Moving>(),
			ComponentType.ReadWrite<TransformFrame>(),
			ComponentType.ReadWrite<InterpolatedTransform>(),
			ComponentType.ReadWrite<CarNavigation>(),
			ComponentType.ReadWrite<CarNavigationLane>(),
			ComponentType.ReadWrite<CarCurrentLane>(),
			ComponentType.ReadWrite<PathOwner>(),
			ComponentType.ReadWrite<Target>(),
			ComponentType.ReadWrite<Blocker>(),
			ComponentType.ReadWrite<PathElement>(),
			ComponentType.ReadWrite<PathInformation>(),
			ComponentType.ReadWrite<ServiceDispatch>(),
			ComponentType.ReadWrite<Swaying>(),
			ComponentType.ReadWrite<Updated>()
		});
		m_ParkedToMovingTrainAddTypes = new ComponentTypeSet(new ComponentType[7]
		{
			ComponentType.ReadWrite<Moving>(),
			ComponentType.ReadWrite<TransformFrame>(),
			ComponentType.ReadWrite<InterpolatedTransform>(),
			ComponentType.ReadWrite<TrainNavigation>(),
			ComponentType.ReadWrite<TrainCurrentLane>(),
			ComponentType.ReadWrite<TrainBogieFrame>(),
			ComponentType.ReadWrite<Updated>()
		});
		m_ParkedToMovingTrainControllerAddTypes = new ComponentTypeSet(new ComponentType[14]
		{
			ComponentType.ReadWrite<Moving>(),
			ComponentType.ReadWrite<TransformFrame>(),
			ComponentType.ReadWrite<InterpolatedTransform>(),
			ComponentType.ReadWrite<TrainNavigation>(),
			ComponentType.ReadWrite<TrainNavigationLane>(),
			ComponentType.ReadWrite<TrainCurrentLane>(),
			ComponentType.ReadWrite<TrainBogieFrame>(),
			ComponentType.ReadWrite<PathOwner>(),
			ComponentType.ReadWrite<Target>(),
			ComponentType.ReadWrite<Blocker>(),
			ComponentType.ReadWrite<PathElement>(),
			ComponentType.ReadWrite<PathInformation>(),
			ComponentType.ReadWrite<ServiceDispatch>(),
			ComponentType.ReadWrite<Updated>()
		});
		RequireForUpdate(m_BuildingQuery);
		Assert.IsTrue(condition: true);
		Assert.IsTrue(condition: true);
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
		m_TransportVehicleSelectData.PreUpdate(this, m_CityConfigurationSystem, m_VehiclePrefabQuery, Allocator.TempJob, out var jobHandle);
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> eventPrefabChunks = m_EventPrefabQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		NativeQueue<DepotAction> actionQueue = new NativeQueue<DepotAction>(Allocator.TempJob);
		TransportDepotTickJob jobData = new TransportDepotTickJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OutsideConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_SpectatorSiteType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_SpectatorSite_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EventType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_EventData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_VehicleLaunchType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_VehicleLaunchData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LockedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_OwnedVehicleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_TransportDepotType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_TransportDepot_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ServiceRequestType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Simulation_ServiceDispatch_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_EntityLookup = InternalCompilerInterface.GetEntityStorageInfoLookup(ref __TypeHandle.__EntityStorageInfoLookup, ref base.CheckedStateRef),
			m_TransportVehicleRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_TransportVehicleRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TaxiRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_TaxiRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ServiceRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_VehicleModelData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_VehicleModel_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_SpawnLocation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RouteColorData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Routes_Color_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ProducedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Produced_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedTrainData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedTrain_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PublicTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PublicTransport_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CargoTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CargoTransport_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TaxiData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Taxi_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OdometerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Odometer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTransportDepotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportDepotData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTransportLineData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportLineData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTaxiData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TaxiData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPublicTransportVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PublicTransportVehicleData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCargoTransportVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CargoTransportVehicleData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathInformationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_ActivityLocationElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ActivityLocationElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_TransportVehicleRequestArchetype = m_TransportVehicleRequestArchetype,
			m_TaxiRequestArchetype = m_TaxiRequestArchetype,
			m_HandleRequestArchetype = m_HandleRequestArchetype,
			m_ParkedToMovingRemoveTypes = m_ParkedToMovingRemoveTypes,
			m_ParkedToMovingTaxiAddTypes = m_ParkedToMovingTaxiAddTypes,
			m_ParkedToMovingBusAddTypes = m_ParkedToMovingBusAddTypes,
			m_ParkedToMovingTrainAddTypes = m_ParkedToMovingTrainAddTypes,
			m_ParkedToMovingTrainControllerAddTypes = m_ParkedToMovingTrainControllerAddTypes,
			m_TransportVehicleSelectData = m_TransportVehicleSelectData,
			m_EventPrefabChunks = eventPrefabChunks,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_ActionQueue = actionQueue.AsParallelWriter()
		};
		TransportDepotActionJob jobData2 = new TransportDepotActionJob
		{
			m_PublicTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PublicTransport_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CargoTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_CargoTransport_RW_ComponentLookup, ref base.CheckedStateRef),
			m_TaxiData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Taxi_RW_ComponentLookup, ref base.CheckedStateRef),
			m_OdometerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Odometer_RW_ComponentLookup, ref base.CheckedStateRef),
			m_ActionQueue = actionQueue
		};
		JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(jobData, m_BuildingQuery, JobHandle.CombineDependencies(base.Dependency, jobHandle, outJobHandle));
		JobHandle jobHandle3 = IJobExtensions.Schedule(jobData2, jobHandle2);
		eventPrefabChunks.Dispose(jobHandle2);
		actionQueue.Dispose(jobHandle3);
		m_TransportVehicleSelectData.PostUpdate(jobHandle2);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle2);
		base.Dependency = jobHandle3;
	}
```


## Nested types

- `Game.Simulation.TransportDepotAISystem+DepotActionType`  
- `Game.Simulation.TransportDepotAISystem+DepotAction`  
- `Game.Simulation.TransportDepotAISystem+TransportDepotTickJob`  
- `Game.Simulation.TransportDepotAISystem+TransportDepotActionJob`  
- `Game.Simulation.TransportDepotAISystem+TypeHandle`  

