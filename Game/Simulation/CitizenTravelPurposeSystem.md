# Game.Simulation.CitizenTravelPurposeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CitizenTravelPurposeSystem : Game.GameSystemBase
{
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_ArrivedGroup;
    private Unity.Entities.EntityQuery m_StuckGroup;
    private Unity.Entities.EntityQuery m_EconomyParameterGroup;
    private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
    private Unity.Entities.EntityQuery m_ServiceBuildingQuery;
    private Game.Simulation.CitizenTravelPurposeSystem+TypeHandle __TypeHandle;

    public CitizenTravelPurposeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_ArrivedGroup`  

```csharp
private Unity.Entities.EntityQuery m_ArrivedGroup;
```

- `private Unity.Entities.EntityQuery m_StuckGroup`  

```csharp
private Unity.Entities.EntityQuery m_StuckGroup;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterGroup;
```

- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceBuildingQuery;
```

- `private Game.Simulation.CitizenTravelPurposeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CitizenTravelPurposeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CitizenTravelPurposeSystem()`  

```csharp
[Preserve]
	public CitizenTravelPurposeSystem()
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
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_ArrivedGroup = GetEntityQuery(ComponentType.ReadOnly<Citizen>(), ComponentType.ReadWrite<TravelPurpose>(), ComponentType.ReadWrite<TripNeeded>(), ComponentType.ReadOnly<CurrentBuilding>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_StuckGroup = GetEntityQuery(ComponentType.ReadOnly<Citizen>(), ComponentType.ReadWrite<TravelPurpose>(), ComponentType.ReadWrite<TripNeeded>(), ComponentType.Exclude<CurrentTransport>(), ComponentType.Exclude<CurrentBuilding>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_OutsideConnectionQuery = GetEntityQuery(ComponentType.ReadWrite<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Game.Objects.ElectricityOutsideConnection>(), ComponentType.Exclude<Game.Objects.WaterPipeOutsideConnection>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_ServiceBuildingQuery = GetEntityQuery(ComponentType.ReadWrite<CityServiceUpkeep>(), ComponentType.ReadWrite<Building>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Temp>());
		m_EconomyParameterGroup = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		RequireAnyForUpdate(m_ArrivedGroup, m_StuckGroup);
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
		NativeQueue<Arrive> arriveQueue = new NativeQueue<Arrive>(Allocator.TempJob);
		CitizenArriveJob jobData = new CitizenArriveJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CurrentBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TravelPurposeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_TravelPurpose_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HealthProblemType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ArrivedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Arrived_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Schools = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_School_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WorkProviders = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_WorkProvider_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Students = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Workers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PoliceStationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PoliceStation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrisonData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Prison_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HospitalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Hospital_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DeathcareFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_DeathcareFacility_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EmergencyShelterData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_EmergencyShelter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HealthProblems = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EconomyParameters = m_EconomyParameterGroup.GetSingleton<EconomyParameterData>(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_ArriveQueue = arriveQueue.AsParallelWriter(),
			m_NormalizedTime = m_TimeSystem.normalizedTime,
			m_RandomSeed = RandomSeed.Next()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_ArrivedGroup, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		JobHandle deps;
		JobHandle jobHandle = IJobExtensions.Schedule(new ArriveJob
		{
			m_CitizenPresenceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_CitizenPresence_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Patients = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Patient_RW_BufferLookup, ref base.CheckedStateRef),
			m_Occupants = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Occupant_RW_BufferLookup, ref base.CheckedStateRef),
			m_Households = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RW_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdMembers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_StatisticsQueue = m_CityStatisticsSystem.GetStatisticsEventQueue(out deps),
			m_ArriveQueue = arriveQueue
		}, JobHandle.CombineDependencies(base.Dependency, deps));
		arriveQueue.Dispose(jobHandle);
		m_CityStatisticsSystem.AddWriter(jobHandle);
		JobHandle outJobHandle;
		JobHandle outJobHandle2;
		JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(new CitizenStuckJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_HouseholdMemberType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HealthProblemType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CitizenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Households = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MovingAways = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Agents_MovingAway_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Buildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_ServiceBuildings = m_ServiceBuildingQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_OutsideConnections = m_OutsideConnectionQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle2),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_StuckGroup, JobUtils.CombineDependencies(outJobHandle2, outJobHandle, jobHandle, base.Dependency));
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle2);
		base.Dependency = JobHandle.CombineDependencies(jobHandle, jobHandle2);
	}
```


## Nested types

- `Game.Simulation.CitizenTravelPurposeSystem+CitizenArriveJob`  
- `Game.Simulation.CitizenTravelPurposeSystem+Arrive`  
- `Game.Simulation.CitizenTravelPurposeSystem+ArriveType`  
- `Game.Simulation.CitizenTravelPurposeSystem+ArriveJob`  
- `Game.Simulation.CitizenTravelPurposeSystem+CitizenStuckJob`  
- `Game.Simulation.CitizenTravelPurposeSystem+TypeHandle`  

