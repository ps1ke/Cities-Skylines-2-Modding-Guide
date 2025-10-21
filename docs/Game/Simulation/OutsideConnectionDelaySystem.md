# Game.Simulation.OutsideConnectionDelaySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class OutsideConnectionDelaySystem : Game.GameSystemBase
{
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Unity.Entities.EntityQuery m_NodeQuery;
    private Game.Simulation.OutsideConnectionDelaySystem+TypeHandle __TypeHandle;
    public static const System.Int32 UPDATES_PER_DAY;

    public OutsideConnectionDelaySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Unity.Entities.EntityQuery m_NodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_NodeQuery;
```

- `private Game.Simulation.OutsideConnectionDelaySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.OutsideConnectionDelaySystem+TypeHandle __TypeHandle;
```

- `public static const System.Int32 UPDATES_PER_DAY`  

```csharp
public static const System.Int32 UPDATES_PER_DAY;
```


## Constructors

- `public OutsideConnectionDelaySystem()`  

```csharp
public OutsideConnectionDelaySystem();
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

- `Game.Simulation.OutsideConnectionDelaySystem+AccumulationData`  
- `Game.Simulation.OutsideConnectionDelaySystem+OutsideConnectionDelayJob`  
- `Game.Simulation.OutsideConnectionDelaySystem+TypeHandle`  

