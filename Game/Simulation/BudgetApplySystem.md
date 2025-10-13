# Game.Simulation.BudgetApplySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BudgetApplySystem : Game.GameSystemBase
{
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.CityServiceBudgetSystem m_CityServiceBudgetSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Simulation.BudgetApplySystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public BudgetApplySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.CityServiceBudgetSystem m_CityServiceBudgetSystem`  

```csharp
private Game.Simulation.CityServiceBudgetSystem m_CityServiceBudgetSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Simulation.BudgetApplySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.BudgetApplySystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public BudgetApplySystem()`  

```csharp
[Preserve]
	public BudgetApplySystem()
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
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_CityServiceBudgetSystem = base.World.GetOrCreateSystemManaged<CityServiceBudgetSystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
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
		JobHandle deps2;
		JobHandle deps3;
		BudgetApplyJob jobData = new BudgetApplyJob
		{
			m_PlayerMoneys = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_PlayerMoney_RW_ComponentLookup, ref base.CheckedStateRef),
			m_City = m_CitySystem.City,
			m_Expenses = m_CityServiceBudgetSystem.GetExpenseArray(out deps),
			m_Income = m_CityServiceBudgetSystem.GetIncomeArray(out deps2),
			m_StatisticsEventQueue = m_CityStatisticsSystem.GetStatisticsEventQueue(out deps3).AsParallelWriter()
		};
		base.Dependency = IJobExtensions.Schedule(jobData, JobUtils.CombineDependencies(deps, deps2, deps3, base.Dependency));
		m_CityServiceBudgetSystem.AddArrayReader(base.Dependency);
		m_CityStatisticsSystem.AddWriter(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.BudgetApplySystem+BudgetApplyJob`  
- `Game.Simulation.BudgetApplySystem+TypeHandle`  

