# Game.Simulation.TouristHouseholdBehaviorSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TouristHouseholdBehaviorSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_TouristHouseholdGroup;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.TouristHouseholdBehaviorSystem+TypeHandle __TypeHandle;

    public TouristHouseholdBehaviorSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_TouristHouseholdGroup`  

```csharp
private Unity.Entities.EntityQuery m_TouristHouseholdGroup;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.TouristHouseholdBehaviorSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TouristHouseholdBehaviorSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TouristHouseholdBehaviorSystem()`  

```csharp
public TouristHouseholdBehaviorSystem();
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

- `Game.Simulation.TouristHouseholdBehaviorSystem+TouristHouseholdTickJob`  
- `Game.Simulation.TouristHouseholdBehaviorSystem+TypeHandle`  

