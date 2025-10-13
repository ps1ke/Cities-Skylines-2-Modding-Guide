# Game.Simulation.StudentSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class StudentSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Simulation.CitizenBehaviorSystem m_CitizenBehaviorSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_GotoSchoolQuery;
    private Unity.Entities.EntityQuery m_StudentQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Unity.Entities.EntityQuery m_PopulationQuery;
    private Game.Simulation.StudentSystem+TypeHandle __TypeHandle;

    public StudentSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single GetStudyOffset(Game.Citizens.Citizen citizen);
    public static Unity.Mathematics.float2 GetTimeToStudy(Game.Citizens.Citizen citizen, Game.Citizens.Student student, Game.Prefabs.EconomyParameterData& economyParameters);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public static System.Boolean IsTimeToStudy(Game.Citizens.Citizen citizen, Game.Citizens.Student student, Game.Prefabs.EconomyParameterData& economyParameters, System.Single timeOfDay, System.UInt32 frame, Game.Common.TimeData timeData, System.Int32 population);
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

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_GotoSchoolQuery`  

```csharp
private Unity.Entities.EntityQuery m_GotoSchoolQuery;
```

- `private Unity.Entities.EntityQuery m_StudentQuery`  

```csharp
private Unity.Entities.EntityQuery m_StudentQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Unity.Entities.EntityQuery m_PopulationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PopulationQuery;
```

- `private Game.Simulation.StudentSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.StudentSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public StudentSystem()`  

```csharp
[Preserve]
	public StudentSystem()
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

- `public static GetStudyOffset(Game.Citizens.Citizen citizen) : System.Single`  

```csharp
public static float GetStudyOffset(Citizen citizen)
	{
		return (float)(-10922 + citizen.GetPseudoRandom(CitizenPseudoRandom.WorkOffset).NextInt(21845)) / 262144f;
	}
```

- `public static GetTimeToStudy(Game.Citizens.Citizen citizen, Game.Citizens.Student student, Game.Prefabs.EconomyParameterData& economyParameters) : Unity.Mathematics.float2`  

```csharp
public static float2 GetTimeToStudy(Citizen citizen, Game.Citizens.Student student, ref EconomyParameterData economyParameters)
	{
		float studyOffset = GetStudyOffset(citizen);
		float num = 60f * student.m_LastCommuteTime;
		if (num < 60f)
		{
			num = 1800f;
		}
		num /= 262144f;
		return new float2(math.frac(economyParameters.m_WorkDayStart + studyOffset - num), math.frac(economyParameters.m_WorkDayEnd + studyOffset));
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 16;
	}
```

- `public static IsTimeToStudy(Game.Citizens.Citizen citizen, Game.Citizens.Student student, Game.Prefabs.EconomyParameterData& economyParameters, System.Single timeOfDay, System.UInt32 frame, Game.Common.TimeData timeData, System.Int32 population) : System.Boolean`  

```csharp
public static bool IsTimeToStudy(Citizen citizen, Game.Citizens.Student student, ref EconomyParameterData economyParameters, float timeOfDay, uint frame, TimeData timeData, int population)
	{
		int num = math.min(40, Mathf.RoundToInt(100f / math.max(1f, math.sqrt(economyParameters.m_TrafficReduction * (float)population))));
		int day = TimeSystem.GetDay(frame, timeData);
		float2 timeToStudy = GetTimeToStudy(citizen, student, ref economyParameters);
		if (Unity.Mathematics.Random.CreateFromIndex((uint)(citizen.m_PseudoRandom + day)).NextInt(100) > num)
		{
			return false;
		}
		if (!(timeToStudy.x < timeToStudy.y))
		{
			if (!(timeOfDay >= timeToStudy.x))
			{
				return timeOfDay <= timeToStudy.y;
			}
			return true;
		}
		if (timeOfDay >= timeToStudy.x)
		{
			return timeOfDay <= timeToStudy.y;
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
		m_StudentQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Citizens.Student>(), ComponentType.ReadOnly<Citizen>(), ComponentType.ReadOnly<TravelPurpose>(), ComponentType.ReadOnly<CurrentBuilding>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_GotoSchoolQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Citizens.Student>(), ComponentType.ReadOnly<Citizen>(), ComponentType.ReadOnly<CurrentBuilding>(), ComponentType.Exclude<ResourceBuyer>(), ComponentType.Exclude<TravelPurpose>(), ComponentType.Exclude<HealthProblem>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_TimeDataQuery = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		m_PopulationQuery = GetEntityQuery(ComponentType.ReadOnly<Population>());
		RequireAnyForUpdate(m_StudentQuery, m_GotoSchoolQuery);
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
		JobHandle deps;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new GoToSchoolJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CitizenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StudentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TripType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_TripNeeded_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_Purposes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TravelPurpose_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Buildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CarKeepers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CarKeeper_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Properties = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OutsideConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Attendings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_AttendingMeeting_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PopulationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_Population_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EconomyParameters = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
			m_TimeOfDay = m_TimeSystem.normalizedTime,
			m_Frame = m_SimulationSystem.frameIndex,
			m_PopulationEntity = m_PopulationQuery.GetSingletonEntity(),
			m_TimeData = m_TimeDataQuery.GetSingleton<TimeData>(),
			m_CarReserverQueue = m_CitizenBehaviorSystem.GetCarReserveQueue(out deps),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_GotoSchoolQuery, JobHandle.CombineDependencies(base.Dependency, deps));
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		m_CitizenBehaviorSystem.AddCarReserveWriter(jobHandle);
		JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(new StudyJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_StudentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PurposeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_TravelPurpose_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CitizenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Attendings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_AttendingMeeting_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentBuildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Targets = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Schools = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_School_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EconomyParameters = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
			m_TimeOfDay = m_TimeSystem.normalizedTime,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		}, m_StudentQuery, JobHandle.CombineDependencies(base.Dependency, jobHandle));
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle2);
		base.Dependency = jobHandle2;
	}
```


## Nested types

- `Game.Simulation.StudentSystem+GoToSchoolJob`  
- `Game.Simulation.StudentSystem+StudyJob`  
- `Game.Simulation.StudentSystem+TypeHandle`  

