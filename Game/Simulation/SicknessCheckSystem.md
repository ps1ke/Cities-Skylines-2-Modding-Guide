# Game.Simulation.SicknessCheckSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class SicknessCheckSystem : Game.GameSystemBase
{
    public readonly System.Int32 kUpdatesPerDay;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Unity.Entities.EntityArchetype m_AddProblemArchetype;
    private Unity.Entities.EntityQuery m_CitizenQuery;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Game.Simulation.SicknessCheckSystem+TypeHandle __TypeHandle;

    public SicknessCheckSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `public readonly System.Int32 kUpdatesPerDay`  

```csharp
public readonly System.Int32 kUpdatesPerDay;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Unity.Entities.EntityArchetype m_AddProblemArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_AddProblemArchetype;
```

- `private Unity.Entities.EntityQuery m_CitizenQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenQuery;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Game.Simulation.SicknessCheckSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.SicknessCheckSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public SicknessCheckSystem()`  

```csharp
public SicknessCheckSystem();
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

- `Game.Simulation.SicknessCheckSystem+SicknessCheckJob`  
- `Game.Simulation.SicknessCheckSystem+TypeHandle`  

