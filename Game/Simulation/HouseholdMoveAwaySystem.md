# Game.Simulation.HouseholdMoveAwaySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdMoveAwaySystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_MoveAwayGroup;
    private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
    private Unity.Entities.EntityArchetype m_RentEventArchetype;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.HouseholdMoveAwaySystem+TypeHandle __TypeHandle;

    public HouseholdMoveAwaySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_MoveAwayGroup`  

```csharp
private Unity.Entities.EntityQuery m_MoveAwayGroup;
```

- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
```

- `private Unity.Entities.EntityArchetype m_RentEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_RentEventArchetype;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.HouseholdMoveAwaySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.HouseholdMoveAwaySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HouseholdMoveAwaySystem()`  

```csharp
public HouseholdMoveAwaySystem();
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

- `Game.Simulation.HouseholdMoveAwaySystem+MoveAwayJob`  
- `Game.Simulation.HouseholdMoveAwaySystem+TypeHandle`  

