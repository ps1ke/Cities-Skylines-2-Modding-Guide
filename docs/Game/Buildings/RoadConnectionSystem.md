# Game.Buildings.RoadConnectionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private Unity.Entities.EntityQuery m_ModificationQuery`  
- `private Unity.Entities.EntityQuery m_UpdatedNetQuery`  
- `private Unity.Entities.EntityQuery m_TrafficConfigQuery`  
- `private Unity.Entities.EntityQuery m_BuildingConfigQuery`  
- `private Unity.Entities.EntityQuery m_ConnectionQuery`  
- `private Unity.Entities.EntityArchetype m_RoadConnectionEventArchetype`  
- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  
- `private Game.Buildings.RoadConnectionSystem+TypeHandle __TypeHandle`  

## Constructors

- `public RoadConnectionSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private static CheckDistance(Game.Net.EdgeGeometry edgeGeometry, Game.Net.EdgeNodeGeometry startGeometry, Game.Net.EdgeNodeGeometry endGeometry, Unity.Mathematics.float3 position, System.Boolean canBeOnRoad, System.Single& maxDistance) : System.Void`  
- `private static CheckDistance(Colossal.Mathematics.Bezier4x3 curve1, Colossal.Mathematics.Bezier4x3 curve2, Unity.Mathematics.float3 position, System.Single& maxDistance) : System.Void`  
- `private static CheckDistance(Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float3 position, System.Single& maxDistance) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Buildings.RoadConnectionSystem+CheckRoadConnectionJob`  
- `Game.Buildings.RoadConnectionSystem+FillReplacementListJob`  
- `Game.Buildings.RoadConnectionSystem+ReplaceRoad`  
- `Game.Buildings.RoadConnectionSystem+FindRoadConnectionJob`  
- `Game.Buildings.RoadConnectionSystem+ReplaceRoadConnectionJob`  
- `Game.Buildings.RoadConnectionSystem+ConnectionLaneKey`  
- `Game.Buildings.RoadConnectionSystem+SpawnLocationData`  
- `Game.Buildings.RoadConnectionSystem+UpdateSecondaryLanesJob`  
- `Game.Buildings.RoadConnectionSystem+TypeHandle`  

