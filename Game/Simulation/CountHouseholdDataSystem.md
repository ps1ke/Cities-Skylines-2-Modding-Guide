# Game.Simulation.CountHouseholdDataSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CountHouseholdDataSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Entities.EntityQuery m_RequirementQuery;
    private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
    private Unity.Jobs.JobHandle m_HouseholdDataWriteDependencies;
    private Unity.Jobs.JobHandle m_HouseholdDataReadDependencies;
    private Colossal.Collections.NativeAccumulator<Game.Simulation.CountHouseholdDataSystem+HouseholdData> m_HouseholdCountData;
    private Colossal.Collections.NativeAccumulator<Game.Simulation.CountHouseholdDataSystem+HouseholdNeedData> m_HouseholdNeedCountData;
    private Game.Simulation.CountHouseholdDataSystem+HouseholdData m_LastHouseholdCountData;
    private Unity.Collections.NativeArray<System.Int32> m_ResourceNeed;
    private System.Boolean m_NeedForceCountData;
    private Unity.Collections.NativeArray<System.Int32> m_EmployableByEducation;
    private Game.Simulation.CountHouseholdDataSystem+TypeHandle __TypeHandle;

    public System.Int32 MovingInHouseholdCount { get; }
    public System.Int32 MovingInCitizenCount { get; }
    public System.Int32 MovingAwayHouseholdCount { get; }
    public System.Int32 CommuterHouseholdCount { get; }
    public System.Int32 TouristCitizenCount { get; }
    public System.Int32 HomelessHouseholdCount { get; }
    public System.Int32 HomelessCitizenCount { get; }
    public System.Int32 MovedInHouseholdCount { get; }
    public System.Int32 MovedInCitizenCount { get; }
    public System.Int32 ChildrenCount { get; }
    public System.Int32 AdultCount { get; }
    public System.Int32 TeenCount { get; }
    public System.Int32 SeniorCount { get; }
    public System.Int32 StudentCount { get; }
    public System.Int32 UneducatedCount { get; }
    public System.Int32 PoorlyEducatedCount { get; }
    public System.Int32 EducatedCount { get; }
    public System.Int32 WellEducatedCount { get; }
    public System.Int32 HighlyEducatedCount { get; }
    public System.Int32 WorkableCitizenCount { get; }
    public System.Int32 CityWorkerCount { get; }
    public System.Int32 DeadCitizenCount { get; }
    public System.Int32 AverageCitizenHappiness { get; }
    public System.Int32 AverageCitizenHealth { get; }
    public System.Single UnemploymentRate { get; }
    public System.Single HomelessnessRate { get; }

    public CountHouseholdDataSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddHouseholdDataReader(Unity.Jobs.JobHandle reader);
    public System.Void Deserialize<TReader>(TReader reader);
    public Unity.Collections.NativeArray<System.Int32> GetEmployables();
    public Game.Simulation.CountHouseholdDataSystem+HouseholdData GetHouseholdCountData();
    public Unity.Collections.NativeArray<System.Int32> GetResourceNeeds(Unity.Jobs.JobHandle& deps);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public System.Boolean IsCountDataNotReady();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Entities.EntityQuery m_RequirementQuery`  

```csharp
private Unity.Entities.EntityQuery m_RequirementQuery;
```

- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_UnlockEventArchetype;
```

- `private Unity.Jobs.JobHandle m_HouseholdDataWriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_HouseholdDataWriteDependencies;
```

- `private Unity.Jobs.JobHandle m_HouseholdDataReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_HouseholdDataReadDependencies;
```

- `private Colossal.Collections.NativeAccumulator<Game.Simulation.CountHouseholdDataSystem+HouseholdData> m_HouseholdCountData`  

```csharp
private Colossal.Collections.NativeAccumulator<Game.Simulation.CountHouseholdDataSystem+HouseholdData> m_HouseholdCountData;
```

- `private Colossal.Collections.NativeAccumulator<Game.Simulation.CountHouseholdDataSystem+HouseholdNeedData> m_HouseholdNeedCountData`  

```csharp
private Colossal.Collections.NativeAccumulator<Game.Simulation.CountHouseholdDataSystem+HouseholdNeedData> m_HouseholdNeedCountData;
```

- `private Game.Simulation.CountHouseholdDataSystem+HouseholdData m_LastHouseholdCountData`  

```csharp
private Game.Simulation.CountHouseholdDataSystem+HouseholdData m_LastHouseholdCountData;
```

- `private Unity.Collections.NativeArray<System.Int32> m_ResourceNeed`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_ResourceNeed;
```

- `private System.Boolean m_NeedForceCountData`  

```csharp
private System.Boolean m_NeedForceCountData;
```

- `private Unity.Collections.NativeArray<System.Int32> m_EmployableByEducation`  

```csharp
private Unity.Collections.NativeArray<System.Int32> m_EmployableByEducation;
```

- `private Game.Simulation.CountHouseholdDataSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CountHouseholdDataSystem+TypeHandle __TypeHandle;
```


## Properties

- `public System.Int32 MovingInHouseholdCount { get }`  

```csharp
public System.Int32 MovingInHouseholdCount { get; }
```

- `public System.Int32 MovingInCitizenCount { get }`  

```csharp
public System.Int32 MovingInCitizenCount { get; }
```

- `public System.Int32 MovingAwayHouseholdCount { get }`  

```csharp
public System.Int32 MovingAwayHouseholdCount { get; }
```

- `public System.Int32 CommuterHouseholdCount { get }`  

```csharp
public System.Int32 CommuterHouseholdCount { get; }
```

- `public System.Int32 TouristCitizenCount { get }`  

```csharp
public System.Int32 TouristCitizenCount { get; }
```

- `public System.Int32 HomelessHouseholdCount { get }`  

```csharp
public System.Int32 HomelessHouseholdCount { get; }
```

- `public System.Int32 HomelessCitizenCount { get }`  

```csharp
public System.Int32 HomelessCitizenCount { get; }
```

- `public System.Int32 MovedInHouseholdCount { get }`  

```csharp
public System.Int32 MovedInHouseholdCount { get; }
```

- `public System.Int32 MovedInCitizenCount { get }`  

```csharp
public System.Int32 MovedInCitizenCount { get; }
```

- `public System.Int32 ChildrenCount { get }`  

```csharp
public System.Int32 ChildrenCount { get; }
```

- `public System.Int32 AdultCount { get }`  

```csharp
public System.Int32 AdultCount { get; }
```

- `public System.Int32 TeenCount { get }`  

```csharp
public System.Int32 TeenCount { get; }
```

- `public System.Int32 SeniorCount { get }`  

```csharp
public System.Int32 SeniorCount { get; }
```

- `public System.Int32 StudentCount { get }`  

```csharp
public System.Int32 StudentCount { get; }
```

- `public System.Int32 UneducatedCount { get }`  

```csharp
public System.Int32 UneducatedCount { get; }
```

- `public System.Int32 PoorlyEducatedCount { get }`  

```csharp
public System.Int32 PoorlyEducatedCount { get; }
```

- `public System.Int32 EducatedCount { get }`  

```csharp
public System.Int32 EducatedCount { get; }
```

- `public System.Int32 WellEducatedCount { get }`  

```csharp
public System.Int32 WellEducatedCount { get; }
```

- `public System.Int32 HighlyEducatedCount { get }`  

```csharp
public System.Int32 HighlyEducatedCount { get; }
```

- `public System.Int32 WorkableCitizenCount { get }`  

```csharp
public System.Int32 WorkableCitizenCount { get; }
```

- `public System.Int32 CityWorkerCount { get }`  

```csharp
public System.Int32 CityWorkerCount { get; }
```

- `public System.Int32 DeadCitizenCount { get }`  

```csharp
public System.Int32 DeadCitizenCount { get; }
```

- `public System.Int32 AverageCitizenHappiness { get }`  

```csharp
public System.Int32 AverageCitizenHappiness { get; }
```

- `public System.Int32 AverageCitizenHealth { get }`  

```csharp
public System.Int32 AverageCitizenHealth { get; }
```

- `public System.Single UnemploymentRate { get }`  

```csharp
public System.Single UnemploymentRate { get; }
```

- `public System.Single HomelessnessRate { get }`  

```csharp
public System.Single HomelessnessRate { get; }
```


## Constructors

- `public CountHouseholdDataSystem()`  

```csharp
[Preserve]
	public CountHouseholdDataSystem()
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

- `public AddHouseholdDataReader(Unity.Jobs.JobHandle reader) : System.Void`  

```csharp
public void AddHouseholdDataReader(JobHandle reader)
	{
		m_HouseholdDataReadDependencies = JobHandle.CombineDependencies(m_HouseholdDataReadDependencies, reader);
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public GetEmployables() : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetEmployables()
	{
		return m_EmployableByEducation;
	}
```

- `public GetHouseholdCountData() : Game.Simulation.CountHouseholdDataSystem+HouseholdData`  

```csharp
public HouseholdData GetHouseholdCountData()
	{
		return m_LastHouseholdCountData;
	}
```

- `public GetResourceNeeds(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeArray<System.Int32>`  

```csharp
public NativeArray<int> GetResourceNeeds(out JobHandle deps)
	{
		deps = m_HouseholdDataWriteDependencies;
		return m_ResourceNeed;
	}
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 16;
	}
```

- `public IsCountDataNotReady() : System.Boolean`  

```csharp
public bool IsCountDataNotReady()
	{
		return m_NeedForceCountData;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_HouseholdQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Household>() },
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_RequirementQuery = GetEntityQuery(ComponentType.ReadOnly<CitizenRequirementData>(), ComponentType.ReadWrite<UnlockRequirementData>(), ComponentType.ReadOnly<Locked>());
		m_UnlockEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Event>(), ComponentType.ReadWrite<Unlock>());
		m_HouseholdCountData = new NativeAccumulator<HouseholdData>(Allocator.Persistent);
		m_HouseholdNeedCountData = new NativeAccumulator<HouseholdNeedData>(EconomyUtils.ResourceCount, Allocator.Persistent);
		m_ResourceNeed = new NativeArray<int>(EconomyUtils.ResourceCount, Allocator.Persistent);
		m_EmployableByEducation = new NativeArray<int>(5, Allocator.Persistent);
		RequireForUpdate(m_HouseholdQuery);
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
		m_HouseholdCountData.Dispose();
		m_HouseholdNeedCountData.Dispose();
		m_ResourceNeed.Dispose();
		m_EmployableByEducation.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_LastHouseholdCountData = m_HouseholdCountData.GetResult();
		m_HouseholdCountData.Clear();
		m_HouseholdNeedCountData.Clear();
		CountHouseholdJob jobData = new CountHouseholdJob
		{
			m_HouseholdType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Household_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HomelessHouseholdType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HomelessHousehold_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HouseholdNeedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdNeed_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PropertyRenterType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_PropertyRenter_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResourcesType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_HouseholdCitizenType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_HealthProblems = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Parks = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Park_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Abandoneds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Students = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Student_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Workers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Worker_RW_ComponentLookup, ref base.CheckedStateRef),
			m_OutsideConnections = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RW_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdCountData = m_HouseholdCountData.AsParallelWriter(),
			m_HouseholdNeedCountData = m_HouseholdNeedCountData.AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_HouseholdQuery, base.Dependency);
		ResultJob jobData2 = new ResultJob
		{
			m_HouseholdData = m_HouseholdCountData,
			m_HouseholdNeedData = m_HouseholdNeedCountData,
			m_Populations = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_Population_RW_ComponentLookup, ref base.CheckedStateRef),
			m_City = m_CitySystem.City,
			m_ResourceNeed = m_ResourceNeed,
			m_EmployableByEducation = m_EmployableByEducation
		};
		base.Dependency = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(base.Dependency, m_HouseholdDataReadDependencies));
		m_HouseholdDataWriteDependencies = base.Dependency;
		if (m_NeedForceCountData)
		{
			base.Dependency.Complete();
			m_NeedForceCountData = false;
		}
		CitizenRequirementJob jobData3 = new CitizenRequirementJob
		{
			m_UnlockEventArchetype = m_UnlockEventArchetype,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CitizenRequirementType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_CitizenRequirementData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UnlockRequirementType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_UnlockRequirementData_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Populations = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_Population_RO_ComponentLookup, ref base.CheckedStateRef),
			m_City = m_CitySystem.City
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData3, m_RequirementQuery, base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_LastHouseholdCountData = default(HouseholdData);
		m_HouseholdCountData.Clear();
		m_HouseholdNeedCountData.Clear();
		m_ResourceNeed.Fill(0);
		m_EmployableByEducation.Fill(0);
	}
```


## Nested types

- `Game.Simulation.CountHouseholdDataSystem+HouseholdNeedData`  
- `Game.Simulation.CountHouseholdDataSystem+HouseholdData`  
- `Game.Simulation.CountHouseholdDataSystem+CountHouseholdJob`  
- `Game.Simulation.CountHouseholdDataSystem+ResultJob`  
- `Game.Simulation.CountHouseholdDataSystem+CitizenRequirementJob`  
- `Game.Simulation.CountHouseholdDataSystem+TypeHandle`  

