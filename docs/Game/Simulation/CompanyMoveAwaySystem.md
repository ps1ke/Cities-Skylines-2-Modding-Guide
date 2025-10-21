# Game.Simulation.CompanyMoveAwaySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CompanyMoveAwaySystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CompanyQuery;
    private Unity.Entities.EntityQuery m_MovingAwayQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityArchetype m_RentEventArchetype;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Simulation.CompanyMoveAwaySystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_731167828_0;
    public static readonly System.Int32 kUpdatesPerDay;

    public CompanyMoveAwaySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CompanyQuery`  

```csharp
private Unity.Entities.EntityQuery m_CompanyQuery;
```

- `private Unity.Entities.EntityQuery m_MovingAwayQuery`  

```csharp
private Unity.Entities.EntityQuery m_MovingAwayQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityArchetype m_RentEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_RentEventArchetype;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Simulation.CompanyMoveAwaySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CompanyMoveAwaySystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_731167828_0`  

```csharp
private Unity.Entities.EntityQuery __query_731167828_0;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public CompanyMoveAwaySystem()`  

```csharp
public CompanyMoveAwaySystem();
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

- `Game.Simulation.CompanyMoveAwaySystem+CheckMoveAwayJob`  
- `Game.Simulation.CompanyMoveAwaySystem+MovingAwayJob`  
- `Game.Simulation.CompanyMoveAwaySystem+TypeHandle`  

