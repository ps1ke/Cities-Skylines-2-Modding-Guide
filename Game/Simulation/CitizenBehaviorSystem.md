# Game.Simulation.CitizenBehaviorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CitizenBehaviorSystem : Game.GameSystemBase
{
    private Unity.Jobs.JobHandle m_CarReserveWriters;
    private Unity.Entities.EntityQuery m_CitizenQuery;
    private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_LeisureParameterQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Unity.Entities.EntityQuery m_PopulationQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityArchetype m_HouseholdArchetype;
    private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_CarReserveQueue;
    private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_ParallelCarReserveQueue;
    private Game.Simulation.CitizenBehaviorSystem+TypeHandle __TypeHandle;
    public static readonly System.Single kMaxPathfindCost;
    public static readonly System.Single kMaxMovingAwayCost;
    public static readonly System.Int32 kMinLeisurePossibility;

    public CitizenBehaviorSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddCarReserveWriter(Unity.Jobs.JobHandle writer);
    public Unity.Collections.NativeQueue<Unity.Entities.Entity> GetCarReserveQueue(Unity.Jobs.JobHandle& deps);
    public static Unity.Mathematics.float2 GetSleepTime(Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
    public static System.Boolean IsSleepTime(Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, System.Single normalizedTime, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Jobs.JobHandle m_CarReserveWriters`  

```csharp
private Unity.Jobs.JobHandle m_CarReserveWriters;
```

- `private Unity.Entities.EntityQuery m_CitizenQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_LeisureParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_LeisureParameterQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Unity.Entities.EntityQuery m_PopulationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PopulationQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityArchetype m_HouseholdArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_HouseholdArchetype;
```

- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_CarReserveQueue`  

```csharp
private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_CarReserveQueue;
```

- `private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_ParallelCarReserveQueue`  

```csharp
private Unity.Collections.NativeQueue<Unity.Entities.Entity> m_ParallelCarReserveQueue;
```

- `private Game.Simulation.CitizenBehaviorSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CitizenBehaviorSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Single kMaxPathfindCost`  

```csharp
public static readonly System.Single kMaxPathfindCost;
```

- `public static readonly System.Single kMaxMovingAwayCost`  

```csharp
public static readonly System.Single kMaxMovingAwayCost;
```

- `public static readonly System.Int32 kMinLeisurePossibility`  

```csharp
public static readonly System.Int32 kMinLeisurePossibility;
```


## Constructors

- `public CitizenBehaviorSystem()`  

```csharp
[Preserve]
	public CitizenBehaviorSystem()
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

- `public AddCarReserveWriter(Unity.Jobs.JobHandle writer) : System.Void`  

```csharp
public void AddCarReserveWriter(JobHandle writer)
	{
		m_CarReserveWriters = JobHandle.CombineDependencies(m_CarReserveWriters, writer);
	}
```

- `public GetCarReserveQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Unity.Entities.Entity>`  

```csharp
public NativeQueue<Entity>.ParallelWriter GetCarReserveQueue(out JobHandle deps)
	{
		deps = m_CarReserveWriters;
		return m_ParallelCarReserveQueue;
	}
```

- `public static GetSleepTime(Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students) : Unity.Mathematics.float2`  

```csharp
public static float2 GetSleepTime(Entity entity, Citizen citizen, ref EconomyParameterData economyParameters, ref ComponentLookup<Worker> workers, ref ComponentLookup<Game.Citizens.Student> students)
	{
		CitizenAge age = citizen.GetAge();
		float2 x = new float2(0.875f, 0.175f);
		float num = x.y - x.x;
		x += citizen.GetPseudoRandom(CitizenPseudoRandom.SleepOffset).NextFloat(0f, 0.2f);
		if (age == CitizenAge.Elderly)
		{
			x -= 0.05f;
		}
		if (age == CitizenAge.Child)
		{
			x -= 0.1f;
		}
		if (age == CitizenAge.Teen)
		{
			x += 0.05f;
		}
		x = math.frac(x);
		float2 @float;
		if (workers.HasComponent(entity))
		{
			@float = WorkerSystem.GetTimeToWork(citizen, workers[entity], ref economyParameters, includeCommute: true);
		}
		else
		{
			if (!students.HasComponent(entity))
			{
				return x;
			}
			@float = StudentSystem.GetTimeToStudy(citizen, students[entity], ref economyParameters);
		}
		if (@float.x < @float.y)
		{
			if (x.x > x.y && @float.y > x.x)
			{
				x += @float.y - x.x;
			}
			else if (x.y > @float.x)
			{
				x += 1f - (x.y - @float.x);
			}
		}
		else
		{
			x = new float2(@float.y, @float.y + num);
		}
		return math.frac(x);
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
		return 11;
	}
```

- `public static IsSleepTime(Unity.Entities.Entity entity, Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, System.Single normalizedTime, Unity.Entities.ComponentLookup`1[[Game.Citizens.Worker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& workers, Unity.Entities.ComponentLookup`1[[Game.Citizens.Student, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& students) : System.Boolean`  

```csharp
public static bool IsSleepTime(Entity entity, Citizen citizen, ref EconomyParameterData economyParameters, float normalizedTime, ref ComponentLookup<Worker> workers, ref ComponentLookup<Game.Citizens.Student> students)
	{
		float2 sleepTime = GetSleepTime(entity, citizen, ref economyParameters, ref workers, ref students);
		if (sleepTime.y < sleepTime.x)
		{
			if (!(normalizedTime > sleepTime.x))
			{
				return normalizedTime < sleepTime.y;
			}
			return true;
		}
		if (normalizedTime > sleepTime.x)
		{
			return normalizedTime < sleepTime.y;
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
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_CarReserveQueue = new NativeQueue<Entity>(Allocator.Persistent);
		m_ParallelCarReserveQueue = m_CarReserveQueue.AsParallelWriter();
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_LeisureParameterQuery = GetEntityQuery(ComponentType.ReadOnly<LeisureParametersData>());
		m_PopulationQuery = GetEntityQuery(ComponentType.ReadOnly<Population>());
		m_CitizenQuery = GetEntityQuery(ComponentType.ReadWrite<Citizen>(), ComponentType.Exclude<TravelPurpose>(), ComponentType.Exclude<ResourceBuyer>(), ComponentType.ReadOnly<CurrentBuilding>(), ComponentType.ReadOnly<HouseholdMember>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_OutsideConnectionQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Game.Objects.ElectricityOutsideConnection>(), ComponentType.Exclude<Game.Objects.WaterPipeOutsideConnection>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_TimeDataQuery = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		m_HouseholdArchetype = base.World.EntityManager.CreateArchetype(ComponentType.ReadWrite<Household>(), ComponentType.ReadWrite<HouseholdNeed>(), ComponentType.ReadWrite<HouseholdCitizen>(), ComponentType.ReadWrite<TaxPayer>(), ComponentType.ReadWrite<Game.Economy.Resources>(), ComponentType.ReadWrite<UpdateFrame>(), ComponentType.ReadWrite<Created>());
		RequireForUpdate(m_CitizenQuery);
		RequireForUpdate(m_EconomyParameterQuery);
		RequireForUpdate(m_LeisureParameterQuery);
		RequireForUpdate(m_TimeDataQuery);
		RequireForUpdate(m_PopulationQuery);
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
		m_CarReserveQueue.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		uint updateFrameWithInterval = SimulationUtils.GetUpdateFrameWithInterval(m_SimulationSystem.frameIndex, (uint)GetUpdateInterval(SystemUpdatePhase.GameSimulation), 16);
		NativeQueue<Entity> mailSenderQueue = new NativeQueue<Entity>(Allocator.TempJob);
		NativeQueue<Entity> sleepQueue = new NativeQueue<Entity>(Allocator.TempJob);
		JobHandle outJobHandle;
		CitizenAITickJob jobData = new CitizenAITickJob
		{
			m_CitizenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_HouseholdMemberType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_HealthProblemType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TripType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_TripNeeded_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_LeisureType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Leisure_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HouseholdNeeds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdNeed_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Households = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Transforms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarKeepers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CarKeeper_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PersonalCars = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PersonalCar_RW_ComponentLookup, ref base.CheckedStateRef),
			m_MovingAway = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Agents_MovingAway_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Workers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Students = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TouristHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TouristHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HomelessHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HomelessHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OutsideConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InDangerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Events_InDanger_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Attendees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_CoordinatedMeetingAttendee_RO_BufferLookup, ref base.CheckedStateRef),
			m_Meetings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CoordinatedMeeting_RW_ComponentLookup, ref base.CheckedStateRef),
			m_AttendingMeetings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_AttendingMeeting_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MeetingDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_HaveCoordinatedMeetingData_RO_BufferLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingStudents = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Student_RO_BufferLookup, ref base.CheckedStateRef),
			m_PopulationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_Population_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OutsideConnectionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_OutsideConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnedVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferLookup, ref base.CheckedStateRef),
			m_CommuterHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CommuterHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EmployeeBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RO_BufferLookup, ref base.CheckedStateRef),
			m_HouseholdArchetype = m_HouseholdArchetype,
			m_OutsideConnectionEntities = m_OutsideConnectionQuery.ToEntityListAsync(Allocator.TempJob, out outJobHandle),
			m_EconomyParameters = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
			m_LeisureParameters = m_LeisureParameterQuery.GetSingleton<LeisureParametersData>(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_UpdateFrameIndex = updateFrameWithInterval,
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_NormalizedTime = m_TimeSystem.normalizedTime,
			m_TimeData = m_TimeDataQuery.GetSingleton<TimeData>(),
			m_PopulationEntity = m_PopulationQuery.GetSingletonEntity(),
			m_CarReserverQueue = m_ParallelCarReserveQueue,
			m_MailSenderQueue = mailSenderQueue.AsParallelWriter(),
			m_SleepQueue = sleepQueue.AsParallelWriter(),
			m_RandomSeed = RandomSeed.Next()
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_CitizenQuery, JobHandle.CombineDependencies(m_CarReserveWriters, JobHandle.CombineDependencies(base.Dependency, outJobHandle)));
		jobData.m_OutsideConnectionEntities.Dispose(jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		AddCarReserveWriter(jobHandle);
		JobHandle jobHandle2 = IJobExtensions.Schedule(new CitizenReserveHouseholdCarJob
		{
			m_CarKeepers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CarKeeper_RW_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdMembers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnedVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferLookup, ref base.CheckedStateRef),
			m_PersonalCars = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_PersonalCar_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ReserverQueue = m_CarReserveQueue
		}, JobHandle.CombineDependencies(jobHandle, m_CarReserveWriters));
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle2);
		AddCarReserveWriter(jobHandle2);
		JobHandle jobHandle3 = IJobExtensions.Schedule(new CitizenTryCollectMailJob
		{
			m_CurrentBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnableBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MailAccumulationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_MailAccumulationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ServiceObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MailSenderData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_MailSender_RW_ComponentLookup, ref base.CheckedStateRef),
			m_MailProducerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_MailProducer_RW_ComponentLookup, ref base.CheckedStateRef),
			m_MailSenderQueue = mailSenderQueue
		}, jobHandle);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle3);
		mailSenderQueue.Dispose(jobHandle3);
		JobHandle jobHandle4 = IJobExtensions.Schedule(new CitizeSleepJob
		{
			m_CurrentBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CitizenPresenceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_CitizenPresence_RW_ComponentLookup, ref base.CheckedStateRef),
			m_SleepQueue = sleepQueue
		}, jobHandle);
		sleepQueue.Dispose(jobHandle4);
		base.Dependency = JobHandle.CombineDependencies(jobHandle2, jobHandle3, jobHandle4);
	}
```


## Nested types

- `Game.Simulation.CitizenBehaviorSystem+CitizenReserveHouseholdCarJob`  
- `Game.Simulation.CitizenBehaviorSystem+CitizenTryCollectMailJob`  
- `Game.Simulation.CitizenBehaviorSystem+CitizeSleepJob`  
- `Game.Simulation.CitizenBehaviorSystem+CitizenAITickJob`  
- `Game.Simulation.CitizenBehaviorSystem+TypeHandle`  

