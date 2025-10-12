# Game.Routes.WaypointConnectionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  
- `private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Net.AirwaySystem m_AirwaySystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Routes.SearchSystem m_RouteSearchSystem`  
- `private Unity.Entities.EntityQuery m_WaypointQuery`  
- `private Unity.Entities.EntityArchetype m_PathTargetEventArchetype`  
- `private Game.Routes.WaypointConnectionSystem+TypeHandle __TypeHandle`  

## Constructors

- `public WaypointConnectionSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Routes.WaypointConnectionSystem+UpdateWaypointReferencesJob`  
- `Game.Routes.WaypointConnectionSystem+FindUpdatedWaypointsJob`  
- `Game.Routes.WaypointConnectionSystem+DequeUpdatedWaypointsJob`  
- `Game.Routes.WaypointConnectionSystem+RemoveDuplicatedWaypointsJob`  
- `Game.Routes.WaypointConnectionSystem+FindWaypointConnectionsJob`  
- `Game.Routes.WaypointConnectionSystem+PathTargetInfo`  
- `Game.Routes.WaypointConnectionSystem+ClearPathTargetsJob`  
- `Game.Routes.WaypointConnectionSystem+TypeHandle`  

