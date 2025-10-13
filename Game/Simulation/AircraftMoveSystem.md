# Game.Simulation.AircraftMoveSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AircraftMoveSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Rendering.LightingSystem m_LightingSystem;
    private Unity.Entities.EntityQuery m_AircraftQuery;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.AircraftMoveSystem+TypeHandle __TypeHandle;

    public AircraftMoveSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
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

- `private Game.Rendering.LightingSystem m_LightingSystem`  

```csharp
private Game.Rendering.LightingSystem m_LightingSystem;
```

- `private Unity.Entities.EntityQuery m_AircraftQuery`  

```csharp
private Unity.Entities.EntityQuery m_AircraftQuery;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.AircraftMoveSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AircraftMoveSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AircraftMoveSystem()`  

```csharp
public AircraftMoveSystem();
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

- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public virtual System.Int32 GetUpdateOffset(Game.SystemUpdatePhase phase);
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

- `Game.Simulation.AircraftMoveSystem+AircraftMoveJob`  
- `Game.Simulation.AircraftMoveSystem+TypeHandle`  

