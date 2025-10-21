# Game.Simulation.NetEdgeDensitySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class NetEdgeDensitySystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_EdgeQuery;
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Game.Simulation.NetEdgeDensitySystem+TypeHandle __TypeHandle;

    public NetEdgeDensitySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_EdgeQuery;
```

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Game.Simulation.NetEdgeDensitySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.NetEdgeDensitySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public NetEdgeDensitySystem()`  

```csharp
public NetEdgeDensitySystem();
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

- `Game.Simulation.NetEdgeDensitySystem+CalculateDensityJob`  
- `Game.Simulation.NetEdgeDensitySystem+TypeHandle`  

