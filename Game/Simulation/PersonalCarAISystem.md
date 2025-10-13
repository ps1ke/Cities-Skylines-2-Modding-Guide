# Game.Simulation.PersonalCarAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PersonalCarAISystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
    private Game.Simulation.PersonalCarAISystem+Actions m_Actions;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Unity.Entities.ComponentTypeSet m_MovingToParkedCarRemoveTypes;
    private Unity.Entities.ComponentTypeSet m_MovingToParkedCarAddTypes;
    private Game.Simulation.PersonalCarAISystem+TypeHandle __TypeHandle;

    public PersonalCarAISystem();

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

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem`  

```csharp
private Game.Simulation.ServiceFeeSystem m_ServiceFeeSystem;
```

- `private Game.Simulation.PersonalCarAISystem+Actions m_Actions`  

```csharp
private Game.Simulation.PersonalCarAISystem+Actions m_Actions;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Unity.Entities.ComponentTypeSet m_MovingToParkedCarRemoveTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_MovingToParkedCarRemoveTypes;
```

- `private Unity.Entities.ComponentTypeSet m_MovingToParkedCarAddTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_MovingToParkedCarAddTypes;
```

- `private Game.Simulation.PersonalCarAISystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PersonalCarAISystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PersonalCarAISystem()`  

```csharp
public PersonalCarAISystem();
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

- `Game.Simulation.PersonalCarAISystem+Actions`  
- `Game.Simulation.PersonalCarAISystem+MoneyTransfer`  
- `Game.Simulation.PersonalCarAISystem+PersonalCarTickJob`  
- `Game.Simulation.PersonalCarAISystem+TransferMoneyJob`  
- `Game.Simulation.PersonalCarAISystem+TypeHandle`  

