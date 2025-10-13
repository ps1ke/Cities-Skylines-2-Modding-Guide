# Game.Simulation.CalendarEventLaunchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CalendarEventLaunchSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Unity.Entities.EntityQuery m_CalendarEventQuery;
    private Game.Simulation.CalendarEventLaunchSystem+TypeHandle __TypeHandle;
    private static const System.Int32 UPDATES_PER_DAY;

    public CalendarEventLaunchSystem();

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

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Unity.Entities.EntityQuery m_CalendarEventQuery`  

```csharp
private Unity.Entities.EntityQuery m_CalendarEventQuery;
```

- `private Game.Simulation.CalendarEventLaunchSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CalendarEventLaunchSystem+TypeHandle __TypeHandle;
```

- `private static const System.Int32 UPDATES_PER_DAY`  

```csharp
private static const System.Int32 UPDATES_PER_DAY;
```


## Constructors

- `public CalendarEventLaunchSystem()`  

```csharp
public CalendarEventLaunchSystem();
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

- `Game.Simulation.CalendarEventLaunchSystem+CheckEventLaunchJob`  
- `Game.Simulation.CalendarEventLaunchSystem+TypeHandle`  

