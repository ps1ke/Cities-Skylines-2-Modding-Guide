# Game.Pathfind.RoutesModifiedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  
- `private Unity.Entities.EntityQuery m_CreatedSubElementQuery`  
- `private Unity.Entities.EntityQuery m_UpdatedSubElementQuery`  
- `private Unity.Entities.EntityQuery m_DeletedSubElementQuery`  
- `private Unity.Entities.EntityQuery m_AllSubElementQuery`  
- `private System.Boolean m_Loaded`  
- `private Game.Pathfind.RoutesModifiedSystem+TypeHandle __TypeHandle`  

## Constructors

- `public RoutesModifiedSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Pathfind.RoutesModifiedSystem+AddPathEdgeJob`  
- `Game.Pathfind.RoutesModifiedSystem+UpdatePathEdgeJob`  
- `Game.Pathfind.RoutesModifiedSystem+RemovePathEdgeJob`  
- `Game.Pathfind.RoutesModifiedSystem+TypeHandle`  

