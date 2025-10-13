# Game.Simulation.PayWageSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PayWageSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Unity.Entities.EntityQuery m_EconomyParameterGroup;
    private Unity.Entities.EntityQuery m_HouseholdGroup;
    private Unity.Collections.NativeQueue<Game.Simulation.PayWageSystem+Payment> m_PaymentQueue;
    private Game.Simulation.PayWageSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public PayWageSystem();

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

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterGroup`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterGroup;
```

- `private Unity.Entities.EntityQuery m_HouseholdGroup`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdGroup;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.PayWageSystem+Payment> m_PaymentQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.PayWageSystem+Payment> m_PaymentQueue;
```

- `private Game.Simulation.PayWageSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PayWageSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public PayWageSystem()`  

```csharp
public PayWageSystem();
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.PayWageSystem+Payment`  
- `Game.Simulation.PayWageSystem+PayJob`  
- `Game.Simulation.PayWageSystem+PayWageJob`  
- `Game.Simulation.PayWageSystem+TypeHandle`  

