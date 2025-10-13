# Game.Simulation.AccidentVehicleSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AccidentVehicleSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_VehicleQuery;
    private Unity.Entities.EntityQuery m_ConfigQuery;
    private Unity.Entities.EntityArchetype m_AddAccidentSiteArchetype;
    private Unity.Entities.EntityArchetype m_EventIgniteArchetype;
    private Unity.Entities.EntityArchetype m_AddImpactArchetype;
    private Game.Simulation.AccidentVehicleSystem+TypeHandle __TypeHandle;
    private static const System.UInt32 UPDATE_INTERVAL;

    public AccidentVehicleSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
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

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_VehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_VehicleQuery;
```

- `private Unity.Entities.EntityQuery m_ConfigQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigQuery;
```

- `private Unity.Entities.EntityArchetype m_AddAccidentSiteArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_AddAccidentSiteArchetype;
```

- `private Unity.Entities.EntityArchetype m_EventIgniteArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EventIgniteArchetype;
```

- `private Unity.Entities.EntityArchetype m_AddImpactArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_AddImpactArchetype;
```

- `private Game.Simulation.AccidentVehicleSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.AccidentVehicleSystem+TypeHandle __TypeHandle;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public AccidentVehicleSystem()`  

```csharp
public AccidentVehicleSystem();
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

- `Game.Simulation.AccidentVehicleSystem+AccidentVehicleJob`  
- `Game.Simulation.AccidentVehicleSystem+TypeHandle`  

