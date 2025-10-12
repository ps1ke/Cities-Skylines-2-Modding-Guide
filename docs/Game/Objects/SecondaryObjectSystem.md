# Game.Objects.SecondaryObjectSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Common.ModificationBarrier4B m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_ObjectQuery`  
- `private Unity.Entities.EntityQuery m_LaneQuery`  
- `private Unity.Entities.ComponentTypeSet m_AppliedTypes`  
- `private Unity.Entities.ComponentTypeSet m_SecondaryOwnerTypes`  
- `private Unity.Entities.ComponentTypeSet m_TempAnimationTypes`  
- `private Game.Objects.SecondaryObjectSystem+TypeHandle __TypeHandle`  

## Constructors

- `public SecondaryObjectSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private UpdateLanes(Unity.Collections.NativeQueue<Game.Objects.SecondaryObjectSystem+UpdateData> updateQueue) : System.Void`  
- `private UpdateObjects(Unity.Collections.NativeQueue<Game.Objects.SecondaryObjectSystem+UpdateData> updateQueue) : System.Void`  

## Nested types

- `Game.Objects.SecondaryObjectSystem+UpdateData`  
- `Game.Objects.SecondaryObjectSystem+SubObjectOwnerData`  
- `Game.Objects.SecondaryObjectSystem+TrafficSignNeeds`  
- `Game.Objects.SecondaryObjectSystem+TrafficSignData`  
- `Game.Objects.SecondaryObjectSystem+StreetLightData`  
- `Game.Objects.SecondaryObjectSystem+UtilityObjectData`  
- `Game.Objects.SecondaryObjectSystem+UtilityNodeData`  
- `Game.Objects.SecondaryObjectSystem+TargetLaneData`  
- `Game.Objects.SecondaryObjectSystem+PlaceholderKey`  
- `Game.Objects.SecondaryObjectSystem+UpdateSecondaryObjectsData`  
- `Game.Objects.SecondaryObjectSystem+FillUpdateMapJob`  
- `Game.Objects.SecondaryObjectSystem+SecondaryLaneAnchorJob`  
- `Game.Objects.SecondaryObjectSystem+CheckSubObjectOwnersJob`  
- `Game.Objects.SecondaryObjectSystem+CollectSubObjectOwnersJob`  
- `Game.Objects.SecondaryObjectSystem+UpdateSubObjectsJob`  
- `Game.Objects.SecondaryObjectSystem+TypeHandle`  

