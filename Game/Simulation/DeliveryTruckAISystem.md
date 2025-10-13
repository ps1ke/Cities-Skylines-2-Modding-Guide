# Game.Simulation.DeliveryTruckAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DeliveryTruckAISystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Simulation.DeliveryTruckAISystem+Actions m_Actions;
    private Unity.Entities.EntityQuery m_DeliveryTruckQuery;
    private Game.Simulation.DeliveryTruckAISystem+TypeHandle __TypeHandle;

    public DeliveryTruckAISystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
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

- `private Game.Simulation.DeliveryTruckAISystem+Actions m_Actions`  

```csharp
private Game.Simulation.DeliveryTruckAISystem+Actions m_Actions;
```

- `private Unity.Entities.EntityQuery m_DeliveryTruckQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeliveryTruckQuery;
```

- `private Game.Simulation.DeliveryTruckAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.DeliveryTruckAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public DeliveryTruckAISystem()`  

```csharp
public DeliveryTruckAISystem();
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

- `Game.Simulation.DeliveryTruckAISystem+DeliveredStack`  
- `Game.Simulation.DeliveryTruckAISystem+RemoveGuestVehicle`  
- `Game.Simulation.DeliveryTruckAISystem+Actions`  
- `Game.Simulation.DeliveryTruckAISystem+DeliverJob`  
- `Game.Simulation.DeliveryTruckAISystem+DeliveryTruckTickJob`  
- `Game.Simulation.DeliveryTruckAISystem+TypeHandle`  

