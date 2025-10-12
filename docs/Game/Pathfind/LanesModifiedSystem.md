# Game.Pathfind.LanesModifiedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  
- `private Unity.Entities.EntityQuery m_CreatedLanesQuery`  
- `private Unity.Entities.EntityQuery m_UpdatedLanesQuery`  
- `private Unity.Entities.EntityQuery m_DeletedLanesQuery`  
- `private Unity.Entities.EntityQuery m_AllLanesQuery`  
- `private System.Boolean m_Loaded`  
- `private Game.Pathfind.LanesModifiedSystem+TypeHandle __TypeHandle`  

## Constructors

- `public LanesModifiedSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Pathfind.LanesModifiedSystem+AddPathEdgeJob`  
- `Game.Pathfind.LanesModifiedSystem+UpdatePathEdgeJob`  
- `Game.Pathfind.LanesModifiedSystem+RemovePathEdgeJob`  
- `Game.Pathfind.LanesModifiedSystem+TypeHandle`  

