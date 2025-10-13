# Game.Simulation.HealthProblemSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HealthProblemSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityArchetype m_HealthcareRequestArchetype;
    private Unity.Entities.EntityArchetype m_JournalDataArchetype;
    private Unity.Entities.EntityArchetype m_ResetTripArchetype;
    private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
    private Unity.Entities.EntityQuery m_HealthProblemQuery;
    private Unity.Entities.EntityQuery m_HealthcareSettingsQuery;
    private Unity.Entities.EntityQuery m_FireSettingsQuery;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Simulation.HealthProblemSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 SYSTEM_UPDATE_INTERVAL;

    public HealthProblemSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityArchetype m_HealthcareRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HealthcareRequestArchetype;
```

- `private Unity.Entities.EntityArchetype m_JournalDataArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_JournalDataArchetype;
```

- `private Unity.Entities.EntityArchetype m_ResetTripArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_ResetTripArchetype;
```

- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HandleRequestArchetype;
```

- `private Unity.Entities.EntityQuery m_HealthProblemQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthProblemQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareSettingsQuery;
```

- `private Unity.Entities.EntityQuery m_FireSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireSettingsQuery;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Simulation.HealthProblemSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.HealthProblemSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 SYSTEM_UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 SYSTEM_UPDATE_INTERVAL;
```


## Constructors

- `public HealthProblemSystem()`  

```csharp
[Preserve]
	public HealthProblemSystem()
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
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_HealthProblemQuery = GetEntityQuery(ComponentType.ReadOnly<Citizen>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.ReadWrite<HealthProblem>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_HealthcareSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<HealthcareParameterData>());
		m_FireSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<FireConfigurationData>());
		m_HealthcareRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<ServiceRequest>(), ComponentType.ReadWrite<HealthcareRequest>(), ComponentType.ReadWrite<RequestGroup>());
		m_JournalDataArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<AddEventJournalData>(), ComponentType.ReadWrite<Game.Common.Event>());
		m_ResetTripArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<ResetTrip>());
		m_HandleRequestArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<HandleRequest>(), ComponentType.ReadWrite<Game.Common.Event>());
		RequireForUpdate(m_HealthProblemQuery);
		RequireForUpdate(m_HealthcareSettingsQuery);
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
		uint updateFrameIndex = (m_SimulationSystem.frameIndex / 16) & 0xF;
		JobHandle deps;
		HealthProblemJob jobData = new HealthProblemJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CurrentBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentTransportType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentTransport_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CitizenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TravelPurposeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_TravelPurpose_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_HealthProblemType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HealthProblem_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TripNeededType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_TripNeeded_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_HouseholdMemberType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HealthcareRequestData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_HealthcareRequest_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HospitalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Hospital_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DeathcareFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_DeathcareFacility_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OnFireData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_OnFire_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DestroyedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DispatchedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_Dispatched_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TargetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StaticData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Static_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OutsideConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AmbulanceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Ambulance_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HearseData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_Hearse_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentVehicleData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_CurrentVehicle_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DivertData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Divert_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_TriggerBuffer = m_TriggerSystem.CreateActionBuffer().AsParallelWriter(),
			m_StatisticsEventQueue = m_CityStatisticsSystem.GetStatisticsEventQueue(out deps).AsParallelWriter(),
			m_UpdateFrameIndex = updateFrameIndex,
			m_RandomSeed = RandomSeed.Next(),
			m_HealthcareRequestArchetype = m_HealthcareRequestArchetype,
			m_JournalDataArchetype = m_JournalDataArchetype,
			m_ResetTripArchetype = m_ResetTripArchetype,
			m_HandleRequestArchetype = m_HandleRequestArchetype,
			m_HealthcareParameterData = m_HealthcareSettingsQuery.GetSingleton<HealthcareParameterData>(),
			m_FireConfigurationData = m_FireSettingsQuery.GetSingleton<FireConfigurationData>(),
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_HealthProblemQuery, JobHandle.CombineDependencies(base.Dependency, deps));
		m_CityStatisticsSystem.AddWriter(base.Dependency);
		m_TriggerSystem.AddActionBufferWriter(base.Dependency);
		m_IconCommandSystem.AddCommandBufferWriter(base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.HealthProblemSystem+HealthProblemJob`  
- `Game.Simulation.HealthProblemSystem+TypeHandle`  

