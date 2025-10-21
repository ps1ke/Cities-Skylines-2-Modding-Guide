# Game.Simulation.IndustrialAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class IndustrialAISystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
    private Unity.Entities.EntityQuery m_CompanyQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Game.Simulation.IndustrialAISystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;
    public static readonly System.Int32 kLowestCompanyWorth;
    public static readonly System.Int32 kMinimumEmployee;
    public static readonly System.Int32 kMaxVirtualResourceStorage;

    public IndustrialAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem`  

```csharp
private Game.Simulation.CountCompanyDataSystem m_CountCompanyDataSystem;
```

- `private Unity.Entities.EntityQuery m_CompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Game.Simulation.IndustrialAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.IndustrialAISystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```

- `public static readonly System.Int32 kLowestCompanyWorth`  

```csharp
public static readonly System.Int32 kLowestCompanyWorth;
```

- `public static readonly System.Int32 kMinimumEmployee`  

```csharp
public static readonly System.Int32 kMinimumEmployee;
```

- `public static readonly System.Int32 kMaxVirtualResourceStorage`  

```csharp
public static readonly System.Int32 kMaxVirtualResourceStorage;
```


## Constructors

- `public IndustrialAISystem()`  

```csharp
public IndustrialAISystem();
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

- `protected virtual OnStopRunning() : System.Void`  

```csharp
protected virtual System.Void OnStopRunning();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Simulation.IndustrialAISystem+CompanyAITickJob`  
- `Game.Simulation.IndustrialAISystem+TypeHandle`  

