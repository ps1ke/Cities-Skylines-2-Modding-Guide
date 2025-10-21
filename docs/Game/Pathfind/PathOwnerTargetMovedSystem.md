# Game.Pathfind.PathOwnerTargetMovedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PathOwnerTargetMovedSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Entities.EntityQuery m_PathOwnerQuery;
    private Game.Pathfind.PathOwnerTargetMovedSystem+TypeHandle __TypeHandle;

    public PathOwnerTargetMovedSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Entities.EntityQuery m_PathOwnerQuery`  

```csharp
private Unity.Entities.EntityQuery m_PathOwnerQuery;
```

- `private Game.Pathfind.PathOwnerTargetMovedSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Pathfind.PathOwnerTargetMovedSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PathOwnerTargetMovedSystem()`  

```csharp
public PathOwnerTargetMovedSystem();
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

- `Game.Pathfind.PathOwnerTargetMovedSystem+CheckPathOwnerTargetsJob`  
- `Game.Pathfind.PathOwnerTargetMovedSystem+TypeHandle`  

