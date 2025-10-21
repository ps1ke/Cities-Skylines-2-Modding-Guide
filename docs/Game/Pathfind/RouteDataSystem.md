# Game.Pathfind.RouteDataSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RouteDataSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_UpdateQuery;
    private Game.Pathfind.RouteDataSystem+TypeHandle __TypeHandle;

    public RouteDataSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_UpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdateQuery;
```

- `private Game.Pathfind.RouteDataSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Pathfind.RouteDataSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RouteDataSystem()`  

```csharp
public RouteDataSystem();
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

- `Game.Pathfind.RouteDataSystem+UpdateRouteDataJob`  
- `Game.Pathfind.RouteDataSystem+TypeHandle`  

