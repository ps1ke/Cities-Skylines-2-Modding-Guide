# Game.Simulation.PostVanDispatchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PostVanDispatchSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Unity.Entities.EntityQuery m_RequestQuery;
    private Unity.Entities.EntityQuery m_PostConfigurationQuery;
    private Game.Simulation.PostVanDispatchSystem+TypeHandle __TypeHandle;

    public PostVanDispatchSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
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

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Unity.Entities.EntityQuery m_RequestQuery`  

```csharp
private Unity.Entities.EntityQuery m_RequestQuery;
```

- `private Unity.Entities.EntityQuery m_PostConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_PostConfigurationQuery;
```

- `private Game.Simulation.PostVanDispatchSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PostVanDispatchSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PostVanDispatchSystem()`  

```csharp
public PostVanDispatchSystem();
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

- `Game.Simulation.PostVanDispatchSystem+VehicleDispatch`  
- `Game.Simulation.PostVanDispatchSystem+PostVanDispatchJob`  
- `Game.Simulation.PostVanDispatchSystem+DispatchVehiclesJob`  
- `Game.Simulation.PostVanDispatchSystem+TypeHandle`  

