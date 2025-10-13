# Game.Simulation.CompanyDividendSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CompanyDividendSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_CompanyQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Collections.NativeQueue<Game.Simulation.CompanyDividendSystem+Dividend> m_DividendQueue;
    private Game.Simulation.CompanyDividendSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public CompanyDividendSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_CompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.CompanyDividendSystem+Dividend> m_DividendQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.CompanyDividendSystem+Dividend> m_DividendQueue;
```

- `private Game.Simulation.CompanyDividendSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CompanyDividendSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public CompanyDividendSystem()`  

```csharp
public CompanyDividendSystem();
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

- `Game.Simulation.CompanyDividendSystem+Dividend`  
- `Game.Simulation.CompanyDividendSystem+ProcessDividendsJob`  
- `Game.Simulation.CompanyDividendSystem+DividendJob`  
- `Game.Simulation.CompanyDividendSystem+TypeHandle`  

