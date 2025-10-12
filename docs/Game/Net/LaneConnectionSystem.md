# Game.Net.LaneConnectionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem`  
- `private Unity.Entities.EntityQuery m_UpdatedQuery`  
- `private Game.Net.LaneConnectionSystem+TypeHandle __TypeHandle`  

## Constructors

- `public LaneConnectionSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Net.LaneConnectionSystem+FindUpdatedLanesJob`  
- `Game.Net.LaneConnectionSystem+CheckUpdatedLanesJob`  
- `Game.Net.LaneConnectionSystem+ListUpdatedLanesJob`  
- `Game.Net.LaneConnectionSystem+FindLaneConnectionJob`  
- `Game.Net.LaneConnectionSystem+TypeHandle`  

