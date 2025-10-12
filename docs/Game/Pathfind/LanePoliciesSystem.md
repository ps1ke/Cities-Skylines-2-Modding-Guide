# Game.Pathfind.LanePoliciesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_PolicyModifyQuery`  
- `private Unity.Entities.EntityQuery m_LaneOwnerQuery`  
- `private Unity.Entities.EntityQuery m_CarLaneQuery`  
- `private Unity.Entities.EntityQuery m_ParkingLaneQuery`  
- `private Game.Pathfind.LanePoliciesSystem+TypeHandle __TypeHandle`  

## Constructors

- `public LanePoliciesSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Pathfind.LanePoliciesSystem+LaneCheckMask`  
- `Game.Pathfind.LanePoliciesSystem+CheckDistrictLanesJob`  
- `Game.Pathfind.LanePoliciesSystem+CheckBuildingLanesJob`  
- `Game.Pathfind.LanePoliciesSystem+TypeHandle`  

