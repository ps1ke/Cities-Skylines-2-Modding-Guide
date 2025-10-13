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
public BudgetApplySystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.BudgetApplySystem+BudgetApplyJob`  
- `Game.Simulation.BudgetApplySystem+TypeHandle`  

