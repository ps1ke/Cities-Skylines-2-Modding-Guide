# Game.Net.LaneOverlapSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Unity.Entities.EntityQuery m_UpdatedOwnersQuery`  
- `private Unity.Entities.EntityQuery m_UpdatedLanesQuery`  
- `private Unity.Entities.EntityQuery m_AllOwnersQuery`  
- `private Unity.Entities.EntityQuery m_AllLanesQuery`  
- `private System.Boolean m_Loaded`  
- `private Game.Net.LaneOverlapSystem+TypeHandle __TypeHandle`  

## Constructors

- `public LaneOverlapSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Net.LaneOverlapSystem+AddNonUpdatedEdgesJob`  
- `Game.Net.LaneOverlapSystem+UpdateLaneFlagsJob`  
- `Game.Net.LaneOverlapSystem+LaneSourceData`  
- `Game.Net.LaneOverlapSystem+LaneTargetData`  
- `Game.Net.LaneOverlapSystem+CollectLaneDirectionsJob`  
- `Game.Net.LaneOverlapSystem+OverlapData`  
- `Game.Net.LaneOverlapSystem+ApplyExtraOverlapsJob`  
- `Game.Net.LaneOverlapSystem+SortLaneOverlapsJob`  
- `Game.Net.LaneOverlapSystem+UpdateLaneOverlapsJob`  
- `Game.Net.LaneOverlapSystem+TypeHandle`  

