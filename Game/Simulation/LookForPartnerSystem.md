# Game.Simulation.LookForPartnerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LookForPartnerSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_CitizenQuery;
    private Unity.Entities.EntityQuery m_LookingQuery;
    private Unity.Entities.EntityQuery m_CitizenParametersQuery;
    private Unity.Collections.NativeQueue<Game.Citizens.LookingForPartner> m_Queue;
    private Colossal.Collections.NativeValue<System.Int32> m_DebugLookingForPartner;
    private Game.Simulation.LookForPartnerSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public LookForPartnerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_CitizenQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenQuery;
```

- `private Unity.Entities.EntityQuery m_LookingQuery`  

```csharp
private Unity.Entities.EntityQuery m_LookingQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenParametersQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenParametersQuery;
```

- `private Unity.Collections.NativeQueue<Game.Citizens.LookingForPartner> m_Queue`  

```csharp
private Unity.Collections.NativeQueue<Game.Citizens.LookingForPartner> m_Queue;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_DebugLookingForPartner`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_DebugLookingForPartner;
```

- `private Game.Simulation.LookForPartnerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.LookForPartnerSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public LookForPartnerSystem()`  

```csharp
[Preserve]
	public LookForPartnerSystem()
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
		m_DebugLookingForPartner = new NativeValue<int>(Allocator.Persistent);
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_CitizenQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Citizen>() },
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_LookingQuery = GetEntityQuery(ComponentType.ReadOnly<LookingForPartner>());
		m_CitizenParametersQuery = GetEntityQuery(ComponentType.ReadOnly<CitizenParametersData>());
		m_Queue = new NativeQueue<LookingForPartner>(Allocator.Persistent);
		RequireForUpdate(m_CitizenQuery);
		RequireForUpdate(m_CitizenParametersQuery);
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
		base.OnDestroy();
		m_Queue.Dispose();
		m_DebugLookingForPartner.Dispose();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		NativeQueue<int> debugLookForPartnerQueue = default(NativeQueue<int>);
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16);
		LookForPartnerJob jobData = new LookForPartnerJob
		{
			m_DebugLookForPartnerQueue = debugLookForPartnerQueue,
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_HouseholdMemberType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdMember_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RW_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_HealthProblems = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Commuters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CommuterHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Tourists = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_TouristHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Households = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RandomSeed = RandomSeed.Next(),
			m_UpdateFrameIndex = updateFrame,
			m_CitizenParametersData = m_CitizenParametersQuery.GetSingleton<CitizenParametersData>(),
			m_Queue = m_Queue.AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CitizenQuery, base.Dependency);
		AddPartnerSeekerJob jobData2 = new AddPartnerSeekerJob
		{
			m_DebugLookingForPartner = m_DebugLookingForPartner,
			m_LookingForPartners = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_LookingForPartner_RW_BufferLookup, ref base.CheckedStateRef),
			m_LookingForPartnerEntity = m_LookingQuery.GetSingletonEntity(),
			m_Queue = m_Queue
		};
		base.Dependency = IJobExtensions.Schedule(jobData2, base.Dependency);
	}
```


## Nested types

- `Game.Simulation.LookForPartnerSystem+AddPartnerSeekerJob`  
- `Game.Simulation.LookForPartnerSystem+LookForPartnerJob`  
- `Game.Simulation.LookForPartnerSystem+TypeHandle`  

