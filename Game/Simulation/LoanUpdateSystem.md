# Game.Simulation.LoanUpdateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LoanUpdateSystem : Game.GameSystemBase
{
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_EconomyParametersQuery;
    private Game.Simulation.LoanUpdateSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public LoanUpdateSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Unity.Entities.EntityQuery m_EconomyParametersQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParametersQuery;
```

- `private Game.Simulation.LoanUpdateSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.LoanUpdateSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public LoanUpdateSystem()`  

```csharp
[Preserve]
	public LoanUpdateSystem()
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
		return 262144 / kUpdatesPerDay;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_EconomyParametersQuery = base.EntityManager.CreateEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		RequireForUpdate(m_EconomyParametersQuery);
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
		LoanUpdateJob jobData = new LoanUpdateJob
		{
			m_StatisticsEventQueue = m_CityStatisticsSystem.GetStatisticsEventQueue(out deps),
			m_City = m_CitySystem.City,
			m_Loans = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_Loan_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Creditworthinesses = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Simulation_Creditworthiness_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlayerMoneys = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_PlayerMoney_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityEffects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_TriggerBuffer = m_TriggerSystem.CreateActionBuffer(),
			m_EconomyParameters = m_EconomyParametersQuery.GetSingleton<EconomyParameterData>(),
			m_SimulationFrameIndex = m_SimulationSystem.frameIndex
		};
		base.Dependency = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, deps));
		m_CityStatisticsSystem.AddWriter(base.Dependency);
		m_TriggerSystem.AddActionBufferWriter(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.LoanUpdateSystem+LoanUpdateJob`  
- `Game.Simulation.LoanUpdateSystem+TypeHandle`  

