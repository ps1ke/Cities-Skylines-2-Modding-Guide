# Game.Net.FixLaneObjectsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Unity.Entities.EntityQuery m_LaneQuery`  
- `private Game.Net.LaneObjectUpdater m_LaneObjectUpdater`  
- `private Game.Net.FixLaneObjectsSystem+TypeHandle __TypeHandle`  

## Constructors

- `public FixLaneObjectsSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Net.FixLaneObjectsSystem+CollectLaneObjectsJob`  
- `Game.Net.FixLaneObjectsSystem+FixLaneObjectsJob`  
- `Game.Net.FixLaneObjectsSystem+TypeHandle`  

