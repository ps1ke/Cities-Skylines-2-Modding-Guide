# Game.Simulation.DeathCheckSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DeathCheckSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_DeathCheckQuery;
    private Unity.Entities.EntityQuery m_HealthcareSettingsQuery;
    private Unity.Entities.EntityQuery m_TimeSettingsQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
    private Game.Simulation.DeathCheckSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;
    public static readonly System.Int32 kMaxAgeInGameYear;

    public DeathCheckSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
    public static System.Void PerformAfterDeathActions(Unity.Entities.Entity citizen, Unity.Entities.Entity household, Unity.Collections.NativeQueue<Game.Triggers.TriggerAction> triggerBuffer, Unity.Collections.NativeQueue<Game.City.StatisticsEvent> statisticsEventQueue, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_DeathCheckQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeathCheckQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareSettingsQuery;
```

- `private Unity.Entities.EntityQuery m_TimeSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeSettingsQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem`  

```csharp
private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem;
```

- `private Game.Simulation.DeathCheckSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.DeathCheckSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static readonly System.Int32 kMaxAgeInGameYear`  

```csharp
public static readonly System.Int32 kMaxAgeInGameYear;
```


## Constructors

- `public DeathCheckSystem()`  

```csharp
[Preserve]
	public DeathCheckSystem()
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
		return 262144 / (kUpdatesPerDay * 16);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_AchievementTriggerSystem = base.World.GetOrCreateSystemManaged<AchievementTriggerSystem>();
		m_DeathCheckQuery = GetEntityQuery(ComponentType.ReadOnly<Citizen>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_HealthcareSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<HealthcareParameterData>());
		m_TimeSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<TimeSettingsData>());
		m_TimeDataQuery = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		RequireForUpdate(m_DeathCheckQuery);
		RequireForUpdate(m_HealthcareSettingsQuery);
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
		if (!base.EntityManager.HasEnabledComponent<Locked>(m_HealthcareSettingsQuery.GetSingleton<HealthcareParameterData>().m_HealthcareServicePrefab))
		{
			uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16);
			JobHandle deps;
			DeathCheckJob jobData = new DeathCheckJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_CitizenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_WorkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_HouseholdMemberType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_HealthProblemType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HealthProblem_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
				m_LeisureType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Leisure_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ResourceBuyerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Companies_ResourceBuyer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_StudentType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_CurrentBuildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
				m_HospitalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Hospital_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurrentTransport = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentTransport_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResidentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Creatures_Resident_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
				m_Students = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Student_RO_BufferLookup, ref base.CheckedStateRef),
				m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
				m_UpdateFrameIndex = updateFrame,
				m_RandomSeed = RandomSeed.Next(),
				m_HealthcareParameterData = m_HealthcareSettingsQuery.GetSingleton<HealthcareParameterData>(),
				m_City = m_CitySystem.City,
				m_TriggerBuffer = m_TriggerSystem.CreateActionBuffer().AsParallelWriter(),
				m_StatisticsEventQueue = m_CityStatisticsSystem.GetStatisticsEventQueue(out deps).AsParallelWriter(),
				m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer(),
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
				m_PatientsRecoveredCounter = m_AchievementTriggerSystem.m_PatientsTreatedCounter.ToConcurrent(),
				m_SimulationFrame = m_SimulationSystem.frameIndex,
				m_TimeSettings = m_TimeSettingsQuery.GetSingleton<TimeSettingsData>(),
				m_TimeData = m_TimeDataQuery.GetSingleton<TimeData>()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_DeathCheckQuery, JobHandle.CombineDependencies(base.Dependency, deps));
			m_IconCommandSystem.AddCommandBufferWriter(base.Dependency);
			m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
			m_CityStatisticsSystem.AddWriter(base.Dependency);
			m_TriggerSystem.AddActionBufferWriter(base.Dependency);
		}
	}
```

- `public static PerformAfterDeathActions(Unity.Entities.Entity citizen, Unity.Entities.Entity household, Unity.Collections.NativeQueue<Game.Triggers.TriggerAction> triggerBuffer, Unity.Collections.NativeQueue<Game.City.StatisticsEvent> statisticsEventQueue, Unity.Entities.BufferLookup`1[[Game.Citizens.HouseholdCitizen, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& householdCitizens) : System.Void`  

```csharp
public static void PerformAfterDeathActions(Entity citizen, Entity household, NativeQueue<TriggerAction>.ParallelWriter triggerBuffer, NativeQueue<StatisticsEvent>.ParallelWriter statisticsEventQueue, ref BufferLookup<HouseholdCitizen> householdCitizens)
	{
		triggerBuffer.Enqueue(new TriggerAction(TriggerType.CitizenDied, Entity.Null, citizen, Entity.Null));
		if (household != Entity.Null && householdCitizens.TryGetBuffer(household, out var bufferData))
		{
			for (int i = 0; i < bufferData.Length; i++)
			{
				if (bufferData[i].m_Citizen != citizen)
				{
					triggerBuffer.Enqueue(new TriggerAction(TriggerType.CitizensFamilyMemberDied, Entity.Null, bufferData[i].m_Citizen, citizen));
				}
			}
		}
		statisticsEventQueue.Enqueue(new StatisticsEvent
		{
			m_Statistic = StatisticType.DeathRate,
			m_Change = 1f
		});
	}
```


## Nested types

- `Game.Simulation.DeathCheckSystem+DeathCheckJob`  
- `Game.Simulation.DeathCheckSystem+TypeHandle`  

