# Game.Simulation.TripNeededSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TripNeededSystem : Game.GameSystemBase
{
    private System.Boolean <debugDisableSpawning>k__BackingField;
    private Unity.Entities.EntityQuery m_CitizenGroup;
    private Unity.Entities.EntityQuery m_ResidentPrefabGroup;
    private Unity.Entities.EntityQuery m_CompanyGroup;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Unity.Entities.EntityArchetype m_ResetTripArchetype;
    private Unity.Entities.ComponentTypeSet m_HumanSpawnTypes;
    private Unity.Entities.ComponentTypeSet m_PathfindTypes;
    private Unity.Entities.ComponentTypeSet m_CurrentLaneTypesRelative;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
    private Game.Debug.DebugWatchDistribution m_DebugPathCostsCar;
    private Game.Debug.DebugWatchDistribution m_DebugPathCostsPublic;
    private Game.Debug.DebugWatchDistribution m_DebugPathCostsPedestrian;
    private Game.Debug.DebugWatchDistribution m_DebugPathCostsCarShort;
    private Game.Debug.DebugWatchDistribution m_DebugPathCostsPublicShort;
    private Game.Debug.DebugWatchDistribution m_DebugPathCostsPedestrianShort;
    private Game.Debug.DebugWatchDistribution m_DebugPublicTransportDuration;
    private Game.Debug.DebugWatchDistribution m_DebugTaxiDuration;
    private Game.Debug.DebugWatchDistribution m_DebugPedestrianDuration;
    private Game.Debug.DebugWatchDistribution m_DebugCarDuration;
    private Game.Debug.DebugWatchDistribution m_DebugPedestrianDurationShort;
    private Game.Simulation.TripNeededSystem+TypeHandle __TypeHandle;
    private static const System.Int32 UPDATE_INTERVAL;

    public System.Boolean debugDisableSpawning { get; set; }

    public TripNeededSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private System.Boolean <debugDisableSpawning>k__BackingField`  

```csharp
private System.Boolean <debugDisableSpawning>k__BackingField;
```

- `private Unity.Entities.EntityQuery m_CitizenGroup`  

```csharp
private Unity.Entities.EntityQuery m_CitizenGroup;
```

- `private Unity.Entities.EntityQuery m_ResidentPrefabGroup`  

```csharp
private Unity.Entities.EntityQuery m_ResidentPrefabGroup;
```

- `private Unity.Entities.EntityQuery m_CompanyGroup`  

```csharp
private Unity.Entities.EntityQuery m_CompanyGroup;
```

- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_ResetTripArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ResetTripArchetype;
```

- `private Unity.Entities.ComponentTypeSet m_HumanSpawnTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_HumanSpawnTypes;
```

- `private Unity.Entities.ComponentTypeSet m_PathfindTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_PathfindTypes;
```

- `private Unity.Entities.ComponentTypeSet m_CurrentLaneTypesRelative`  

```csharp
private Unity.Entities.ComponentTypeSet m_CurrentLaneTypesRelative;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  

```csharp
private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsCar`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPathCostsCar;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsPublic`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPathCostsPublic;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsPedestrian`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPathCostsPedestrian;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsCarShort`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPathCostsCarShort;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsPublicShort`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPathCostsPublicShort;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsPedestrianShort`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPathCostsPedestrianShort;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPublicTransportDuration`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPublicTransportDuration;
```

- `private Game.Debug.DebugWatchDistribution m_DebugTaxiDuration`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugTaxiDuration;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPedestrianDuration`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPedestrianDuration;
```

- `private Game.Debug.DebugWatchDistribution m_DebugCarDuration`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugCarDuration;
```

- `private Game.Debug.DebugWatchDistribution m_DebugPedestrianDurationShort`  

```csharp
private Game.Debug.DebugWatchDistribution m_DebugPedestrianDurationShort;
```

- `private Game.Simulation.TripNeededSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TripNeededSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 UPDATE_INTERVAL`  

```csharp
private static const System.Int32 UPDATE_INTERVAL;
```


## Properties

- `public System.Boolean debugDisableSpawning { get; set }`  

```csharp
public System.Boolean debugDisableSpawning { get; set; }
```


## Constructors

- `public TripNeededSystem()`  

```csharp
[Preserve]
	public TripNeededSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_DebugPathCostsCar = new DebugWatchDistribution(persistent: true);
		m_DebugPathCostsPublic = new DebugWatchDistribution(persistent: true);
		m_DebugPathCostsPedestrian = new DebugWatchDistribution(persistent: true);
		m_DebugPathCostsCarShort = new DebugWatchDistribution(persistent: true);
		m_DebugPathCostsPublicShort = new DebugWatchDistribution(persistent: true);
		m_DebugPathCostsPedestrianShort = new DebugWatchDistribution(persistent: true);
		m_DebugPublicTransportDuration = new DebugWatchDistribution(persistent: true);
		m_DebugTaxiDuration = new DebugWatchDistribution(persistent: true);
		m_DebugPedestrianDuration = new DebugWatchDistribution(persistent: true);
		m_DebugCarDuration = new DebugWatchDistribution(persistent: true);
		m_DebugPedestrianDurationShort = new DebugWatchDistribution(persistent: true);
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_VehicleCapacitySystem = base.World.GetOrCreateSystemManaged<VehicleCapacitySystem>();
		m_CitizenGroup = GetEntityQuery(ComponentType.ReadOnly<Citizen>(), ComponentType.ReadOnly<HouseholdMember>(), ComponentType.ReadWrite<TripNeeded>(), ComponentType.Exclude<TravelPurpose>(), ComponentType.ReadOnly<CurrentBuilding>(), ComponentType.Exclude<ResourceBuyer>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_ResidentPrefabGroup = GetEntityQuery(ComponentType.ReadOnly<ObjectData>(), ComponentType.ReadOnly<HumanData>(), ComponentType.ReadOnly<ResidentData>(), ComponentType.ReadOnly<PrefabData>());
		m_CompanyGroup = GetEntityQuery(ComponentType.ReadWrite<TripNeeded>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadWrite<Game.Economy.Resources>(), ComponentType.ReadOnly<OwnedVehicle>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_HandleRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<HandleRequest>(), ComponentType.ReadWrite<Game.Events.Event>());
		m_ResetTripArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<ResetTrip>());
		m_HumanSpawnTypes = new ComponentTypeSet(ComponentType.ReadWrite<HumanCurrentLane>(), ComponentType.ReadWrite<TripSource>(), ComponentType.ReadWrite<Unspawned>());
		m_PathfindTypes = new ComponentTypeSet(ComponentType.ReadWrite<PathInformation>(), ComponentType.ReadWrite<PathElement>());
		m_CurrentLaneTypesRelative = new ComponentTypeSet(new ComponentType[5]
		{
			ComponentType.ReadWrite<Moving>(),
			ComponentType.ReadWrite<TransformFrame>(),
			ComponentType.ReadWrite<HumanNavigation>(),
			ComponentType.ReadWrite<HumanCurrentLane>(),
			ComponentType.ReadWrite<Blocker>()
		});
		m_PathfindSetupSystem = base.World.GetOrCreateSystemManaged<PathfindSetupSystem>();
		RequireAnyForUpdate(m_CitizenGroup, m_CompanyGroup);
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_DebugPathCostsCar.Dispose();
		m_DebugPathCostsPublic.Dispose();
		m_DebugPathCostsPedestrian.Dispose();
		m_DebugPathCostsCarShort.Dispose();
		m_DebugPathCostsPublicShort.Dispose();
		m_DebugPathCostsPedestrianShort.Dispose();
		m_DebugPublicTransportDuration.Dispose();
		m_DebugTaxiDuration.Dispose();
		m_DebugCarDuration.Dispose();
		m_DebugPedestrianDuration.Dispose();
		m_DebugPedestrianDurationShort.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> humanChunks = m_ResidentPrefabGroup.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		JobHandle jobHandle = JobHandle.CombineDependencies(base.Dependency, outJobHandle);
		JobHandle jobHandle2 = default(JobHandle);
		if (!m_CitizenGroup.IsEmptyIgnoreFilter)
		{
			NativeQueue<AnimalTargetInfo> animalQueue = new NativeQueue<AnimalTargetInfo>(Allocator.TempJob);
			NativeQueue<Entity> leaveQueue = new NativeQueue<Entity>(Allocator.TempJob);
			NativeQueue<int> debugPathQueueCar = default(NativeQueue<int>);
			NativeQueue<int> debugPathQueuePublic = default(NativeQueue<int>);
			NativeQueue<int> debugPathQueuePedestrian = default(NativeQueue<int>);
			NativeQueue<int> debugPathQueueCarShort = default(NativeQueue<int>);
			NativeQueue<int> debugPathQueuePublicShort = default(NativeQueue<int>);
			NativeQueue<int> debugPathQueuePedestrianShort = default(NativeQueue<int>);
			NativeQueue<int> debugPublicTransportDuration = default(NativeQueue<int>);
			NativeQueue<int> debugTaxiDuration = default(NativeQueue<int>);
			NativeQueue<int> debugCarDuration = default(NativeQueue<int>);
			NativeQueue<int> debugPedestrianDuration = default(NativeQueue<int>);
			NativeQueue<int> debugPedestrianDurationShort = default(NativeQueue<int>);
			JobHandle deps = default(JobHandle);
			if (m_DebugPathCostsCar.IsEnabled)
			{
				debugPathQueueCar = m_DebugPathCostsCar.GetQueue(clear: false, out deps);
				deps.Complete();
			}
			if (m_DebugPathCostsPublic.IsEnabled)
			{
				debugPathQueuePublic = m_DebugPathCostsPublic.GetQueue(clear: false, out deps);
				deps.Complete();
			}
			if (m_DebugPathCostsPedestrian.IsEnabled)
			{
				debugPathQueuePedestrian = m_DebugPathCostsPedestrian.GetQueue(clear: false, out deps);
				deps.Complete();
			}
			if (m_DebugPathCostsCarShort.IsEnabled)
			{
				debugPathQueueCarShort = m_DebugPathCostsCarShort.GetQueue(clear: false, out deps);
				deps.Complete();
			}
			if (m_DebugPathCostsPublicShort.IsEnabled)
			{
				debugPathQueuePublicShort = m_DebugPathCostsPublicShort.GetQueue(clear: false, out deps);
				deps.Complete();
			}
			if (m_DebugPathCostsPedestrianShort.IsEnabled)
			{
				debugPathQueuePedestrianShort = m_DebugPathCostsPedestrianShort.GetQueue(clear: false, out deps);
				deps.Complete();
			}
			if (m_DebugPublicTransportDuration.IsEnabled)
			{
				debugPublicTransportDuration = m_DebugPublicTransportDuration.GetQueue(clear: false, out deps);
				deps.Complete();
			}
			if (m_DebugTaxiDuration.IsEnabled)
			{
				debugTaxiDuration = m_DebugTaxiDuration.GetQueue(clear: false, out deps);
				deps.Complete();
			}
			if (m_DebugCarDuration.IsEnabled)
			{
				debugCarDuration = m_DebugCarDuration.GetQueue(clear: false, out deps);
				deps.Complete();
			}
			if (m_DebugPedestrianDuration.IsEnabled)
			{
				debugPedestrianDuration = m_DebugPedestrianDuration.GetQueue(clear: false, out deps);
				deps.Complete();
			}
			if (m_DebugPedestrianDurationShort.IsEnabled)
			{
				debugPedestrianDurationShort = m_DebugPedestrianDurationShort.GetQueue(clear: false, out deps);
				deps.Complete();
			}
			CitizenJob jobData = new CitizenJob
			{
				m_DebugPathQueueCar = debugPathQueueCar,
				m_DebugPathQueuePublic = debugPathQueuePublic,
				m_DebugPathQueuePedestrian = debugPathQueuePedestrian,
				m_DebugPathQueueCarShort = debugPathQueueCarShort,
				m_DebugPathQueuePublicShort = debugPathQueuePublicShort,
				m_DebugPathQueuePedestrianShort = debugPathQueuePedestrianShort,
				m_DebugPublicTransportDuration = debugPublicTransportDuration,
				m_DebugTaxiDuration = debugTaxiDuration,
				m_DebugCarDuration = debugCarDuration,
				m_DebugPedestrianDuration = debugPedestrianDuration,
				m_DebugPedestrianDurationShort = debugPedestrianDurationShort,
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_CitizenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_HealthProblemType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_HouseholdMemberType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_MailSenderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_MailSender_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurrentTransportType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentTransport_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurrentBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TripNeededType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_TripNeeded_RW_BufferTypeHandle, ref base.CheckedStateRef),
				m_AttendingMeetingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_AttendingMeeting_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CreatureDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CreatureData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ResidentDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ResidentData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ParkedCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_ParkedCar_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PersonalCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PersonalCar_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AmbulanceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Ambulance_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurrentDistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PathInfos = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Properties = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Transforms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Targets = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Deleteds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PathElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_CarKeepers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CarKeeper_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Workers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Worker_RW_ComponentLookup, ref base.CheckedStateRef),
				m_Students = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Student_RW_ComponentLookup, ref base.CheckedStateRef),
				m_ObjectDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabCarData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabHumanData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_HumanData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OutsideConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_UnderConstructionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_UnderConstruction_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Meetings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CoordinatedMeeting_RW_ComponentLookup, ref base.CheckedStateRef),
				m_Attendees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_CoordinatedMeetingAttendee_RO_BufferLookup, ref base.CheckedStateRef),
				m_HouseholdAnimals = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdAnimal_RO_BufferLookup, ref base.CheckedStateRef),
				m_TravelPurposes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TravelPurpose_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HaveCoordinatedMeetingDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_HaveCoordinatedMeetingData_RO_BufferLookup, ref base.CheckedStateRef),
				m_Households = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
				m_OwnedVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferLookup, ref base.CheckedStateRef),
				m_HumanChunks = humanChunks,
				m_RandomSeed = RandomSeed.Next(),
				m_TimeOfDay = m_TimeSystem.normalizedTime,
				m_ResetTripArchetype = m_ResetTripArchetype,
				m_HumanSpawnTypes = m_HumanSpawnTypes,
				m_PathfindTypes = m_PathfindTypes,
				m_PathQueue = m_PathfindSetupSystem.GetQueue(this, 80, 16).AsParallelWriter(),
				m_AnimalQueue = animalQueue.AsParallelWriter(),
				m_LeaveQueue = leaveQueue.AsParallelWriter(),
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
				m_DebugDisableSpawning = debugDisableSpawning
			};
			PetTargetJob jobData2 = new PetTargetJob
			{
				m_CurrentBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AnimalQueue = animalQueue,
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer()
			};
			CitizeLeaveJob jobData3 = new CitizeLeaveJob
			{
				m_CurrentBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CitizenPresenceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_CitizenPresence_RW_ComponentLookup, ref base.CheckedStateRef),
				m_LeaveQueue = leaveQueue
			};
			jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_CitizenGroup, jobHandle);
			JobHandle jobHandle3 = IJobExtensions.Schedule(jobData2, jobHandle);
			JobHandle jobHandle4 = IJobExtensions.Schedule(jobData3, jobHandle);
			jobHandle2 = JobHandle.CombineDependencies(jobHandle3, jobHandle4);
			animalQueue.Dispose(jobHandle3);
			leaveQueue.Dispose(jobHandle4);
			m_PathfindSetupSystem.AddQueueWriter(jobHandle);
			m_EndFrameBarrier.AddJobHandleForProducer(jobHandle2);
		}
		if (!m_CompanyGroup.IsEmptyIgnoreFilter)
		{
			jobHandle = JobChunkExtensions.ScheduleParallel(new CompanyJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PropertyRenterType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CreatureDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CreatureData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ResidentDataType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ResidentData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TripNeededType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_TripNeeded_RW_BufferTypeHandle, ref base.CheckedStateRef),
				m_VehicleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_ResourceType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RW_BufferTypeHandle, ref base.CheckedStateRef),
				m_PrefabDeliveryTruckData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_DeliveryTruckData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Transforms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransportCompanyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_TransportCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ServiceRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_ServiceRequest_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PathInformationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_UnderConstructionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_UnderConstruction_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PropertyRenterData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PathElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_PathElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_ActivityLocationElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_ActivityLocationElement_RO_BufferLookup, ref base.CheckedStateRef),
				m_HumanChunks = humanChunks,
				m_LeftHandTraffic = m_CityConfigurationSystem.leftHandTraffic,
				m_RandomSeed = RandomSeed.Next(),
				m_HandleRequestArchetype = m_HandleRequestArchetype,
				m_DeliveryTruckSelectData = m_VehicleCapacitySystem.GetDeliveryTruckSelectData(),
				m_CurrentLaneTypesRelative = m_CurrentLaneTypesRelative,
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
				m_DebugDisableSpawning = debugDisableSpawning
			}, m_CompanyGroup, jobHandle);
			m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
			jobHandle2 = JobHandle.CombineDependencies(jobHandle2, jobHandle);
		}
		humanChunks.Dispose(jobHandle);
		base.Dependency = jobHandle2;
	}
```


## Nested types

- `Game.Simulation.TripNeededSystem+CompanyJob`  
- `Game.Simulation.TripNeededSystem+AnimalTargetInfo`  
- `Game.Simulation.TripNeededSystem+PetTargetJob`  
- `Game.Simulation.TripNeededSystem+CitizeLeaveJob`  
- `Game.Simulation.TripNeededSystem+CitizenJob`  
- `Game.Simulation.TripNeededSystem+TypeHandle`  

