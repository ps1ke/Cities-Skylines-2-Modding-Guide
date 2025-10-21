# Game.Simulation.PropertyRenterRemoveSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PropertyRenterRemoveSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_RenterGroup;
    private Unity.Entities.EntityArchetype m_RentEventArchetype;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.PropertyRenterRemoveSystem+TypeHandle __TypeHandle;

    public PropertyRenterRemoveSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_RenterGroup`  

```csharp
private Unity.Entities.EntityQuery m_RenterGroup;
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

- `private Game.Simulation.PropertyRenterRemoveSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PropertyRenterRemoveSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PropertyRenterRemoveSystem()`  

```csharp
public PropertyRenterRemoveSystem();
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

- `Game.Simulation.PropertyRenterRemoveSystem+UpdateRentersJob`  
- `Game.Simulation.PropertyRenterRemoveSystem+RemoveData`  
- `Game.Simulation.PropertyRenterRemoveSystem+RemoveRentersJob`  
- `Game.Simulation.PropertyRenterRemoveSystem+TypeHandle`  

