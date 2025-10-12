# Game.Routes.RoutePathReadySystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Unity.Entities.EntityQuery m_PathReadyQuery`  
- `private Unity.Entities.EntityQuery m_RouteQuery`  
- `private Unity.Entities.EntityQuery m_RouteConfigQuery`  
- `private System.Boolean m_Loaded`  
- `private Game.Routes.RoutePathReadySystem+TypeHandle __TypeHandle`  

## Constructors

- `public RoutePathReadySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Routes.RoutePathReadySystem+RoutePathReadyJob`  
- `Game.Routes.RoutePathReadySystem+TypeHandle`  

