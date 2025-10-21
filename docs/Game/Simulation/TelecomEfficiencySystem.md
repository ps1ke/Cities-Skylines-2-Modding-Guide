# Game.Simulation.TelecomEfficiencySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TelecomEfficiencySystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Game.Simulation.TelecomEfficiencySystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_450882671_0;
    private Unity.Entities.EntityQuery __query_450882671_1;
    private static const System.Int32 kUpdatesPerDay;

    public TelecomEfficiencySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  

```csharp
private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Game.Simulation.TelecomEfficiencySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TelecomEfficiencySystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_450882671_0`  

```csharp
private Unity.Entities.EntityQuery __query_450882671_0;
```

- `private Unity.Entities.EntityQuery __query_450882671_1`  

```csharp
private Unity.Entities.EntityQuery __query_450882671_1;
```

- `private static const System.Int32 kUpdatesPerDay`  

```csharp
private static const System.Int32 kUpdatesPerDay;
```


## Constructors

- `public TelecomEfficiencySystem()`  

```csharp
public TelecomEfficiencySystem();
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

- `Game.Simulation.TelecomEfficiencySystem+TelecomEfficiencyJob`  
- `Game.Simulation.TelecomEfficiencySystem+TypeHandle`  

