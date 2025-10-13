# Game.Simulation.WorkerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WorkerSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Simulation.CitizenBehaviorSystem m_CitizenBehaviorSystem;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_GotoWorkQuery;
    private Unity.Entities.EntityQuery m_WorkerQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Unity.Entities.EntityQuery m_PopulationQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.WorkerSystem+TypeHandle __TypeHandle;

    public WorkerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static Unity.Mathematics.float2 GetTimeToWork(Game.Citizens.Citizen citizen, Game.Citizens.Worker worker, Game.Prefabs.EconomyParameterData& economyParameters, System.Boolean includeCommute);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static System.Single GetWorkOffset(Game.Citizens.Citizen citizen);
    public static System.Boolean IsTimeToWork(Game.Citizens.Citizen citizen, Game.Citizens.Worker worker, Game.Prefabs.EconomyParameterData& economyParameters, System.Single timeOfDay);
    public static System.Boolean IsTodayOffDay(Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, System.UInt32 frame, Game.Common.TimeData timeData, System.Int32 population);
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

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Simulation.CitizenBehaviorSystem m_CitizenBehaviorSystem`  

```csharp
private Game.Simulation.CitizenBehaviorSystem m_CitizenBehaviorSystem;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_GotoWorkQuery`  

```csharp
private Unity.Entities.EntityQuery m_GotoWorkQuery;
```

- `private Unity.Entities.EntityQuery m_WorkerQuery`  

```csharp
private Unity.Entities.EntityQuery m_WorkerQuery;
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

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.WorkerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WorkerSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WorkerSystem()`  

```csharp
[Preserve]
	public WorkerSystem()
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

- `public static GetTimeToWork(Game.Citizens.Citizen citizen, Game.Citizens.Worker worker, Game.Prefabs.EconomyParameterData& economyParameters, System.Boolean includeCommute) : Unity.Mathematics.float2`  

```csharp
public static float2 GetTimeToWork(Citizen citizen, Worker worker, ref EconomyParameterData economyParameters, bool includeCommute)
	{
		float num = GetWorkOffset(citizen);
		if (worker.m_Shift == Workshift.Evening)
		{
			num += 0.33f;
		}
		else if (worker.m_Shift == Workshift.Night)
		{
			num += 0.67f;
		}
		float num2 = math.frac((float)Mathf.RoundToInt(24f * (economyParameters.m_WorkDayStart + num)) / 24f);
		float y = math.frac((float)Mathf.RoundToInt(24f * (economyParameters.m_WorkDayEnd + num)) / 24f);
		float num3 = 0f;
		if (includeCommute)
		{
			num3 = 60f * worker.m_LastCommuteTime;
			if (num3 < 60f)
			{
				num3 = 40000f;
			}
			num3 /= 262144f;
		}
		return new float2(math.frac(num2 - num3), y);
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 16;
	}
```

- `public static GetWorkOffset(Game.Citizens.Citizen citizen) : System.Single`  

```csharp
public static float GetWorkOffset(Citizen citizen)
	{
		return (float)(-10922 + citizen.GetPseudoRandom(CitizenPseudoRandom.WorkOffset).NextInt(21845)) / 262144f;
	}
```

- `public static IsTimeToWork(Game.Citizens.Citizen citizen, Game.Citizens.Worker worker, Game.Prefabs.EconomyParameterData& economyParameters, System.Single timeOfDay) : System.Boolean`  

```csharp
public static bool IsTimeToWork(Citizen citizen, Worker worker, ref EconomyParameterData economyParameters, float timeOfDay)
	{
		float2 timeToWork = GetTimeToWork(citizen, worker, ref economyParameters, includeCommute: true);
		if (!(timeToWork.x < timeToWork.y))
		{
			if (!(timeOfDay >= timeToWork.x))
			{
				return timeOfDay <= timeToWork.y;
			}
			return true;
		}
		if (timeOfDay >= timeToWork.x)
		{
			return timeOfDay <= timeToWork.y;
		}
		return false;
	}
```

- `public static IsTodayOffDay(Game.Citizens.Citizen citizen, Game.Prefabs.EconomyParameterData& economyParameters, System.UInt32 frame, Game.Common.TimeData timeData, System.Int32 population) : System.Boolean`  

```csharp
public static bool IsTodayOffDay(Citizen citizen, ref EconomyParameterData economyParameters, uint frame, TimeData timeData, int population)
	{
		int num = math.min(40, Mathf.RoundToInt(100f / math.max(1f, math.sqrt(economyParameters.m_TrafficReduction * (float)population))));
		int day = TimeSystem.GetDay(frame, timeData);
		if (Unity.Mathematics.Random.CreateFromIndex((uint)(citizen.m_PseudoRandom + day)).NextInt(100) > num)
		{
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
		m_CitizenBehaviorSystem = base.World.GetOrCreateSystemManaged<CitizenBehaviorSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_WorkerQuery = GetEntityQuery(ComponentType.ReadOnly<Worker>(), ComponentType.ReadOnly<Citizen>(), ComponentType.ReadOnly<TravelPurpose>(), ComponentType.ReadOnly<CurrentBuilding>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_GotoWorkQuery = GetEntityQuery(ComponentType.ReadOnly<Worker>(), ComponentType.ReadOnly<Citizen>(), ComponentType.ReadOnly<CurrentBuilding>(), ComponentType.Exclude<TravelPurpose>(), ComponentType.Exclude<HealthProblem>(), ComponentType.Exclude<ResourceBuyer>(), ComponentType.ReadWrite<TripNeeded>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_TimeDataQuery = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		m_PopulationQuery = GetEntityQuery(ComponentType.ReadOnly<Population>());
		RequireAnyForUpdate(m_GotoWorkQuery, m_WorkerQuery);
		RequireForUpdate(m_EconomyParameterQuery);
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
		uint updateFrameWithInterval = SimulationUtils.GetUpdateFrameWithInterval(m_SimulationSystem.frameIndex, (uint)GetUpdateInterval(SystemUpdatePhase.GameSimulation), 16);
		JobHandle deps;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new GoToWorkJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CitizenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WorkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TripType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_TripNeeded_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_Buildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarKeepers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CarKeeper_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Properties = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OutsideConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Purposes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TravelPurpose_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Attendings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_AttendingMeeting_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PopulationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_Population_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TriggerBuffer = m_TriggerSystem.CreateActionBuffer().AsParallelWriter(),
			m_EconomyParameters = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
			m_TimeOfDay = m_TimeSystem.normalizedTime,
			m_UpdateFrameIndex = updateFrameWithInterval,
			m_Frame = m_SimulationSystem.frameIndex,
			m_TimeData = m_TimeDataQuery.GetSingleton<TimeData>(),
			m_PopulationEntity = m_PopulationQuery.GetSingletonEntity(),
			m_CarReserverQueue = m_CitizenBehaviorSystem.GetCarReserveQueue(out deps),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_GotoWorkQuery, JobHandle.CombineDependencies(base.Dependency, deps));
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		m_CitizenBehaviorSystem.AddCarReserveWriter(jobHandle);
		m_TriggerSystem.AddActionBufferWriter(jobHandle);
		JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(new WorkJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_WorkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PurposeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_TravelPurpose_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_CitizenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Attendings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_AttendingMeeting_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Workplaces = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_WorkProvider_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TriggerBuffer = m_TriggerSystem.CreateActionBuffer().AsParallelWriter(),
			m_EconomyParameters = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
			m_UpdateFrameIndex = updateFrameWithInterval,
			m_TimeOfDay = m_TimeSystem.normalizedTime,
			m_Frame = m_SimulationSystem.frameIndex,
			m_TimeData = m_TimeDataQuery.GetSingleton<TimeData>(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_WorkerQuery, JobHandle.CombineDependencies(base.Dependency, jobHandle));
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle2);
		m_TriggerSystem.AddActionBufferWriter(jobHandle2);
		base.Dependency = jobHandle2;
	}
```


## Nested types

- `Game.Simulation.WorkerSystem+GoToWorkJob`  
- `Game.Simulation.WorkerSystem+WorkJob`  
- `Game.Simulation.WorkerSystem+TypeHandle`  

