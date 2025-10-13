# Game.Simulation.GarbageFacilityAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GarbageFacilityAISystem : Game.GameSystemBase
{
    private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.GarbageTruckSelectData m_GarbageTruckSelectData;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Unity.Entities.EntityQuery m_GarbageTruckPrefabQuery;
    private Unity.Entities.EntityQuery m_GarbageSettingsQuery;
    private Unity.Entities.EntityArchetype m_GarbageTransferRequestArchetype;
    private Unity.Entities.EntityArchetype m_GarbageCollectionRequestArchetype;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes;
    private Game.Simulation.GarbageFacilityAISystem+TypeHandle __TypeHandle;
    private static const System.Int32 kUpdatesPerDay;

    public GarbageFacilityAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private static System.Single CalculateGarbageAmountFactor(System.Int32 garbageAmount, System.Int32 garbageCapacity);
    private static System.Single CalculateProcessingRate(System.Single maxProcessingRate, System.Single efficiency, System.Int32 garbageAmount, System.Int32 garbageCapacity);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  

```csharp
private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.GarbageTruckSelectData m_GarbageTruckSelectData`  

```csharp
private Game.Prefabs.GarbageTruckSelectData m_GarbageTruckSelectData;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageTruckPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageTruckPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageSettingsQuery;
```

- `private Unity.Entities.EntityArchetype m_GarbageTransferRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_GarbageTransferRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_GarbageCollectionRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_GarbageCollectionRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes;
```

- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes;
```

- `private Game.Simulation.GarbageFacilityAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.GarbageFacilityAISystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 kUpdatesPerDay`  

```csharp
private static const System.Int32 kUpdatesPerDay;
```


## Constructors

- `public GarbageFacilityAISystem()`  

```csharp
[Preserve]
	public GarbageFacilityAISystem()
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

- `private static CalculateGarbageAmountFactor(System.Int32 garbageAmount, System.Int32 garbageCapacity) : System.Single`  

```csharp
private static float CalculateGarbageAmountFactor(int garbageAmount, int garbageCapacity)
	{
		return math.saturate(0.1f + (float)garbageAmount * 1.8f / math.max(1f, garbageCapacity));
	}
```

- `private static CalculateProcessingRate(System.Single maxProcessingRate, System.Single efficiency, System.Int32 garbageAmount, System.Int32 garbageCapacity) : System.Single`  

```csharp
private static float CalculateProcessingRate(float maxProcessingRate, float efficiency, int garbageAmount, int garbageCapacity)
	{
		float num = CalculateGarbageAmountFactor(garbageAmount, garbageCapacity);
		return efficiency * num * maxProcessingRate;
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
		return 80;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_VehicleCapacitySystem = base.World.GetOrCreateSystemManaged<VehicleCapacitySystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_GarbageTruckSelectData = new GarbageTruckSelectData(this);
		m_BuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Buildings.GarbageFacility>(), ComponentType.ReadOnly<ServiceDispatch>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_GarbageSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<GarbageParameterData>());
		m_GarbageTruckPrefabQuery = GetEntityQuery(GarbageTruckSelectData.GetEntityQueryDesc());
		m_GarbageTransferRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<ServiceRequest>(), ComponentType.ReadWrite<GarbageTransferRequest>(), ComponentType.ReadWrite<RequestGroup>());
		m_GarbageCollectionRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<ServiceRequest>(), ComponentType.ReadWrite<GarbageCollectionRequest>(), ComponentType.ReadWrite<RequestGroup>());
		m_HandleRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<HandleRequest>(), ComponentType.ReadWrite<Game.Common.Event>());
		m_ParkedToMovingRemoveTypes = new ComponentTypeSet(ComponentType.ReadWrite<ParkedCar>(), ComponentType.ReadWrite<Stopped>());
		m_ParkedToMovingCarAddTypes = new ComponentTypeSet(new ComponentType[14]
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
		RequireForUpdate(m_BuildingQuery);
		RequireForUpdate(m_GarbageSettingsQuery);
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
		m_GarbageTruckSelectData.PreUpdate(this, m_CityConfigurationSystem, m_GarbageTruckPrefabQuery, Allocator.TempJob, out var jobHandle);
		NativeQueue<GarbageFacilityAction> actionQueue = new NativeQueue<GarbageFacilityAction>(Allocator.TempJob);
		GarbageFacilityTickJob jobData = new GarbageFacilityTickJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EfficiencyType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_OutsideConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_InstalledUpgradeType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_SubAreaType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_GarbageFacilityType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_GarbageFacility_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ServiceDispatchType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Simulation_ServiceDispatch_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_ResourcesType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_OwnedVehicleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_GuestVehicleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_GuestVehicle_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_EntityLookup = InternalCompilerInterface.GetEntityStorageInfoLookup(ref __TypeHandle.__EntityStorageInfoLookup, ref base.CheckedStateRef),
			m_GarbageCollectionRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_GarbageCollectionRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GarbageTransferRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_GarbageTransferRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ServiceRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathInformationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TargetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnLocationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_SpawnLocation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_QuantityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Quantity_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GarbageTruckData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_GarbageTruck_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DeliveryTruckData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_DeliveryTruck_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ReturnLoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ReturnLoad_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkedCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AreaGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Geometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGarbageFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_GarbageFacilityData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGarbageTruckData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_GarbageTruckData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabStorageAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StorageAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabDeliveryTruckData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_DeliveryTruckData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_ResourceProductionDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ResourceProductionData_RO_BufferLookup, ref base.CheckedStateRef),
			m_AreaStorageData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Storage_RW_ComponentLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_SimulationFrameIndex = m_SimulationSystem.frameIndex,
			m_GarbageParameters = m_GarbageSettingsQuery.GetSingleton<GarbageParameterData>(),
			m_GarbageTruckSelectData = m_GarbageTruckSelectData,
			m_DeliveryTruckSelectData = m_VehicleCapacitySystem.GetDeliveryTruckSelectData(),
			m_GarbageTransferRequestArchetype = m_GarbageTransferRequestArchetype,
			m_GarbageCollectionRequestArchetype = m_GarbageCollectionRequestArchetype,
			m_HandleRequestArchetype = m_HandleRequestArchetype,
			m_ParkedToMovingRemoveTypes = m_ParkedToMovingRemoveTypes,
			m_ParkedToMovingCarAddTypes = m_ParkedToMovingCarAddTypes,
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_ActionQueue = actionQueue.AsParallelWriter()
		};
		GarbageFacilityActionJob jobData2 = new GarbageFacilityActionJob
		{
			m_GarbageTruckData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_GarbageTruck_RW_ComponentLookup, ref base.CheckedStateRef),
			m_ActionQueue = actionQueue
		};
		JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(jobData, m_BuildingQuery, JobHandle.CombineDependencies(base.Dependency, jobHandle));
		JobHandle jobHandle3 = IJobExtensions.Schedule(jobData2, jobHandle2);
		actionQueue.Dispose(jobHandle3);
		m_GarbageTruckSelectData.PostUpdate(jobHandle2);
		m_IconCommandSystem.AddCommandBufferWriter(jobHandle2);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle2);
		base.Dependency = jobHandle3;
	}
```


## Nested types

- `Game.Simulation.GarbageFacilityAISystem+GarbageFacilityAction`  
- `Game.Simulation.GarbageFacilityAISystem+GarbageFacilityTickJob`  
- `Game.Simulation.GarbageFacilityAISystem+GarbageFacilityActionJob`  
- `Game.Simulation.GarbageFacilityAISystem+TypeHandle`  

