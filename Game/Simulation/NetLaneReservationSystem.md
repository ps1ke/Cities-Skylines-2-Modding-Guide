# Game.Simulation.NetLaneReservationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetLaneReservationSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Unity.Entities.EntityQuery m_LaneQuery;
    private Game.Simulation.NetLaneReservationSystem+TypeHandle __TypeHandle;

    public NetLaneReservationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `private Unity.Entities.EntityQuery m_LaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneQuery;
```

- `private Game.Simulation.NetLaneReservationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.NetLaneReservationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NetLaneReservationSystem()`  

```csharp
public NetLaneReservationSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `Game.Simulation.NetLaneReservationSystem+ResetLaneReservationsJob`  
- `Game.Simulation.NetLaneReservationSystem+TypeHandle`  

