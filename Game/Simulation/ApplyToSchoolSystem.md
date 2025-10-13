# Game.Simulation.ApplyToSchoolSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ApplyToSchoolSystem : Game.GameSystemBase
{
    public System.Boolean debugFastApplySchool;
    private Unity.Entities.EntityQuery m_CitizenGroup;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.ApplyToSchoolSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_2069025490_0;
    private Unity.Entities.EntityQuery __query_2069025490_1;
    private Unity.Entities.EntityQuery __query_2069025490_2;
    public static readonly System.Int32 kCoolDown;
    public static const System.UInt32 UPDATE_INTERVAL;

    public ApplyToSchoolSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single GetEnteringProbability(Game.Citizens.CitizenAge age, System.Boolean worker, System.Int32 level, System.Int32 wellbeing, System.Single willingness, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.EducationParameterData& educationParameterData);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `public System.Boolean debugFastApplySchool`  

```csharp
public System.Boolean debugFastApplySchool;
```

- `private Unity.Entities.EntityQuery m_CitizenGroup`  

```csharp
private Unity.Entities.EntityQuery m_CitizenGroup;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.ApplyToSchoolSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ApplyToSchoolSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_2069025490_0`  

```csharp
private Unity.Entities.EntityQuery __query_2069025490_0;
```

- `private Unity.Entities.EntityQuery __query_2069025490_1`  

```csharp
private Unity.Entities.EntityQuery __query_2069025490_1;
```

- `private Unity.Entities.EntityQuery __query_2069025490_2`  

```csharp
private Unity.Entities.EntityQuery __query_2069025490_2;
```

- `public static readonly System.Int32 kCoolDown`  

```csharp
public static readonly System.Int32 kCoolDown;
```

- `public static const System.UInt32 UPDATE_INTERVAL`  

```csharp
public static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public ApplyToSchoolSystem()`  

```csharp
[Preserve]
	public ApplyToSchoolSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<EconomyParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_2069025490_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<EducationParameterData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_2069025490_1 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<TimeData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_2069025490_2 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `public static GetEnteringProbability(Game.Citizens.CitizenAge age, System.Boolean worker, System.Int32 level, System.Int32 wellbeing, System.Single willingness, Unity.Entities.DynamicBuffer<Game.City.CityModifier> cityModifiers, Game.Prefabs.EducationParameterData& educationParameterData) : System.Single`  

```csharp
public static float GetEnteringProbability(CitizenAge age, bool worker, int level, int wellbeing, float willingness, DynamicBuffer<CityModifier> cityModifiers, ref EducationParameterData educationParameterData)
	{
		if (level == 1)
		{
			if (age != CitizenAge.Child)
			{
				return 0f;
			}
			return 1f;
		}
		if (age == CitizenAge.Child || age == CitizenAge.Elderly)
		{
			return 0f;
		}
		if (level == 2)
		{
			if (!(age == CitizenAge.Adult || worker))
			{
				return educationParameterData.m_EnterHighSchoolProbability;
			}
			return educationParameterData.m_AdultEnterHighSchoolProbability;
		}
		float num = (float)wellbeing / 60f * (0.5f + willingness);
		switch (level)
		{
		case 3:
			return 0.5f * (worker ? educationParameterData.m_WorkerContinueEducationProbability : 1f) * math.log(1.6f * num + 1f);
		case 4:
		{
			float value = 0.3f * (worker ? educationParameterData.m_WorkerContinueEducationProbability : 1f) * num;
			CityUtils.ApplyModifier(ref value, cityModifiers, CityModifierType.UniversityInterest);
			return value;
		}
		default:
			return 0f;
		}
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 512;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_CitizenGroup = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadWrite<Citizen>(),
				ComponentType.ReadOnly<UpdateFrame>()
			},
			None = new ComponentType[5]
			{
				ComponentType.ReadOnly<HealthProblem>(),
				ComponentType.ReadOnly<HasJobSeeker>(),
				ComponentType.ReadOnly<HasSchoolSeeker>(),
				ComponentType.ReadOnly<Game.Citizens.Student>(),
				ComponentType.ReadOnly<Deleted>()
			}
		});
		RequireForUpdate(m_CitizenGroup);
		RequireForUpdate<EconomyParameterData>();
		RequireForUpdate<TimeData>();
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
		ApplyToSchoolJob jobData = new ApplyToSchoolJob
		{
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_CitizenType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Citizen_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_WorkerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HouseholdMembers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SchoolDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SchoolData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Resources = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RO_BufferLookup, ref base.CheckedStateRef),
			m_Fees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_ServiceFee_RO_BufferLookup, ref base.CheckedStateRef),
			m_TouristHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TouristHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MovingAways = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Agents_MovingAway_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SchoolSeekerCooldowns = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_SchoolSeekerCooldown_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_EconomyParameters = __query_2069025490_0.GetSingleton<EconomyParameterData>(),
			m_EducationParameters = __query_2069025490_1.GetSingleton<EducationParameterData>(),
			m_TimeData = __query_2069025490_2.GetSingleton<TimeData>(),
			m_City = m_CitySystem.City,
			m_UpdateFrameIndex = updateFrameWithInterval,
			m_DebugFastApplySchool = debugFastApplySchool,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CitizenGroup, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.ApplyToSchoolSystem+ApplyToSchoolJob`  
- `Game.Simulation.ApplyToSchoolSystem+TypeHandle`  

