# Game.Simulation.HealthcareDispatchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HealthcareDispatchSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Unity.Entities.EntityQuery m_RequestQuery;
    private Game.Simulation.HealthcareDispatchSystem+TypeHandle __TypeHandle;

    public HealthcareDispatchSystem();

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

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Unity.Entities.EntityQuery m_RequestQuery`  

```csharp
private Unity.Entities.EntityQuery m_RequestQuery;
```

- `private Game.Simulation.HealthcareDispatchSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.HealthcareDispatchSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HealthcareDispatchSystem()`  

```csharp
public HealthcareDispatchSystem();
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

- `Game.Simulation.HealthcareDispatchSystem+VehicleDispatch`  
- `Game.Simulation.HealthcareDispatchSystem+HealthcareDispatchJob`  
- `Game.Simulation.HealthcareDispatchSystem+DispatchVehiclesJob`  
- `Game.Simulation.HealthcareDispatchSystem+TypeHandle`  

