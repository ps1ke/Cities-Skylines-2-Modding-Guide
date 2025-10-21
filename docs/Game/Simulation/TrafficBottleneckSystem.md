# Game.Simulation.TrafficBottleneckSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class TrafficBottleneckSystem : Game.GameSystemBase
{
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_BlockerQuery;
    private Unity.Entities.EntityQuery m_BottleneckQuery;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private Game.Simulation.TrafficBottleneckSystem+TypeHandle __TypeHandle;

    public TrafficBottleneckSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Unity.Entities.EntityQuery m_BlockerQuery`  

```csharp
private Unity.Entities.EntityQuery m_BlockerQuery;
```

- `private Unity.Entities.EntityQuery m_BottleneckQuery`  

```csharp
private Unity.Entities.EntityQuery m_BottleneckQuery;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private Game.Simulation.TrafficBottleneckSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.TrafficBottleneckSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public TrafficBottleneckSystem()`  

```csharp
public TrafficBottleneckSystem();
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

- `Game.Simulation.TrafficBottleneckSystem+GroupData`  
- `Game.Simulation.TrafficBottleneckSystem+BottleneckData`  
- `Game.Simulation.TrafficBottleneckSystem+BottleneckState`  
- `Game.Simulation.TrafficBottleneckSystem+TrafficBottleneckJob`  
- `Game.Simulation.TrafficBottleneckSystem+TypeHandle`  

