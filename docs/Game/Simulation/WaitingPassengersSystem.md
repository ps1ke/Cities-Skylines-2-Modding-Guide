# Game.Simulation.WaitingPassengersSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class WaitingPassengersSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Unity.Entities.EntityQuery m_StopQuery;
    private Unity.Entities.EntityQuery m_ResidentQuery;
    private Game.Simulation.WaitingPassengersSystem+TypeHandle __TypeHandle;

    public WaitingPassengersSystem();

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

- `private Unity.Entities.EntityQuery m_StopQuery`  

```csharp
private Unity.Entities.EntityQuery m_StopQuery;
```

- `private Unity.Entities.EntityQuery m_ResidentQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResidentQuery;
```

- `private Game.Simulation.WaitingPassengersSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.WaitingPassengersSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public WaitingPassengersSystem()`  

```csharp
public WaitingPassengersSystem();
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

- `Game.Simulation.WaitingPassengersSystem+ClearWaitingPassengersJob`  
- `Game.Simulation.WaitingPassengersSystem+CountWaitingPassengersJob`  
- `Game.Simulation.WaitingPassengersSystem+TickWaitingPassengersJob`  
- `Game.Simulation.WaitingPassengersSystem+TypeHandle`  

