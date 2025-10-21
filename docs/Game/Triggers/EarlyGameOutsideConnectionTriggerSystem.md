# Game.Triggers.EarlyGameOutsideConnectionTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EarlyGameOutsideConnectionTriggerSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.ResourceAvailabilitySystem m_ResourceAvailabilitySystem;
    private System.Boolean m_Started;
    private System.Double m_StartTime;
    private System.Boolean m_Triggered;
    private Game.Triggers.EarlyGameOutsideConnectionTriggerSystem+TypeHandle __TypeHandle;
    private static readonly System.Single kDelaySeconds;
    private static const System.UInt32 UPDATE_INTERVAL;

    public EarlyGameOutsideConnectionTriggerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.ResourceAvailabilitySystem m_ResourceAvailabilitySystem`  

```csharp
private Game.Simulation.ResourceAvailabilitySystem m_ResourceAvailabilitySystem;
```

- `private System.Boolean m_Started`  

```csharp
private System.Boolean m_Started;
```

- `private System.Double m_StartTime`  

```csharp
private System.Double m_StartTime;
```

- `private System.Boolean m_Triggered`  

```csharp
private System.Boolean m_Triggered;
```

- `private Game.Triggers.EarlyGameOutsideConnectionTriggerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Triggers.EarlyGameOutsideConnectionTriggerSystem+TypeHandle __TypeHandle;
```

- `private static readonly System.Single kDelaySeconds`  

```csharp
private static readonly System.Single kDelaySeconds;
```

- `private static const System.UInt32 UPDATE_INTERVAL`  

```csharp
private static const System.UInt32 UPDATE_INTERVAL;
```


## Constructors

- `public EarlyGameOutsideConnectionTriggerSystem()`  

```csharp
public EarlyGameOutsideConnectionTriggerSystem();
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```


## Nested types

- `Game.Triggers.EarlyGameOutsideConnectionTriggerSystem+TriggerJob`  
- `Game.Triggers.EarlyGameOutsideConnectionTriggerSystem+TypeHandle`  

