# Game.Routes.RoutePathSystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RoutePathSystem : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable
{
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Unity.Entities.EntityQuery m_UpdatedSegmentQuery;
    private Unity.Entities.EntityQuery m_DeletedLaneQuery;
    private Unity.Entities.EntityQuery m_AppliedLaneQuery;
    private Unity.Entities.EntityQuery m_SegmentQuery;
    private Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> m_LazyUpdateSet;
    private Game.Routes.RoutePathSystem+TypeHandle __TypeHandle;

    public RoutePathSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void Deserialize<TReader>(TReader reader);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    private System.Void SetupPathfind(Unity.Entities.Entity entity, Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 endPos, Game.Routes.RouteLane startLane, Game.Routes.RouteLane endLane, Game.Prefabs.RouteData route, Game.Prefabs.RouteConnectionData routeConnection, System.Boolean highPriority);
}
```


## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedSegmentQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedSegmentQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedLaneQuery;
```

- `private Unity.Entities.EntityQuery m_AppliedLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_AppliedLaneQuery;
```

- `private Unity.Entities.EntityQuery m_SegmentQuery`  

```csharp
private Unity.Entities.EntityQuery m_SegmentQuery;
```

- `private Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> m_LazyUpdateSet`  

```csharp
private Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> m_LazyUpdateSet;
```

- `private Game.Routes.RoutePathSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Routes.RoutePathSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public RoutePathSystem()`  

```csharp
public RoutePathSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `private SetupPathfind(Unity.Entities.Entity entity, Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 endPos, Game.Routes.RouteLane startLane, Game.Routes.RouteLane endLane, Game.Prefabs.RouteData route, Game.Prefabs.RouteConnectionData routeConnection, System.Boolean highPriority) : System.Void`  

```csharp
private System.Void SetupPathfind(Unity.Entities.Entity entity, Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 endPos, Game.Routes.RouteLane startLane, Game.Routes.RouteLane endLane, Game.Prefabs.RouteData route, Game.Prefabs.RouteConnectionData routeConnection, System.Boolean highPriority);
```


## Nested types

- `Game.Routes.RoutePathSystem+RoutePathType`  
- `Game.Routes.RoutePathSystem+CheckRoutePathsJob`  
- `Game.Routes.RoutePathSystem+CheckAppliedLanesJob`  
- `Game.Routes.RoutePathSystem+CheckSegmentRoutes`  
- `Game.Routes.RoutePathSystem+TypeHandle`  

