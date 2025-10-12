# Game.Buildings.ZoneCheckSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Zones.UpdateCollectSystem m_ZoneUpdateCollectSystem`  
- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  
- `private Game.Common.ModificationEndBarrier m_ModificationEndBarrier`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Unity.Entities.EntityQuery m_BuildingSettingsQuery`  
- `private Game.Buildings.ZoneCheckSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ZoneCheckSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Buildings.ZoneCheckSystem+FindSpawnableBuildingsJob`  
- `Game.Buildings.ZoneCheckSystem+CollectEntitiesJob`  
- `Game.Buildings.ZoneCheckSystem+CheckBuildingZonesJob`  
- `Game.Buildings.ZoneCheckSystem+TypeHandle`  

