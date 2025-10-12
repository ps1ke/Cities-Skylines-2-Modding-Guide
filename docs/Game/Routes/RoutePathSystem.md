# Game.Routes.RoutePathSystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  
- `private Unity.Entities.EntityQuery m_UpdatedSegmentQuery`  
- `private Unity.Entities.EntityQuery m_DeletedLaneQuery`  
- `private Unity.Entities.EntityQuery m_AppliedLaneQuery`  
- `private Unity.Entities.EntityQuery m_SegmentQuery`  
- `private Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> m_LazyUpdateSet`  
- `private Game.Routes.RoutePathSystem+TypeHandle __TypeHandle`  

## Constructors

- `public RoutePathSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private SetupPathfind(Unity.Entities.Entity entity, Unity.Mathematics.float3 startPos, Unity.Mathematics.float3 endPos, Game.Routes.RouteLane startLane, Game.Routes.RouteLane endLane, Game.Prefabs.RouteData route, Game.Prefabs.RouteConnectionData routeConnection, System.Boolean highPriority) : System.Void`  

## Nested types

- `Game.Routes.RoutePathSystem+RoutePathType`  
- `Game.Routes.RoutePathSystem+CheckRoutePathsJob`  
- `Game.Routes.RoutePathSystem+CheckAppliedLanesJob`  
- `Game.Routes.RoutePathSystem+CheckSegmentRoutes`  
- `Game.Routes.RoutePathSystem+TypeHandle`  

