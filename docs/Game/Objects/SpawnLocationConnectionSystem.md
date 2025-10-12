# Game.Objects.SpawnLocationConnectionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem`  
- `private Game.Net.AirwaySystem m_AirwaySystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_UpdatedQuery`  
- `private Game.Objects.SpawnLocationConnectionSystem+TypeHandle __TypeHandle`  

## Constructors

- `public SpawnLocationConnectionSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Objects.SpawnLocationConnectionSystem+FindUpdatedSpawnLocationsJob`  
- `Game.Objects.SpawnLocationConnectionSystem+CheckUpdatedSpawnLocationsJob`  
- `Game.Objects.SpawnLocationConnectionSystem+ListUpdatedSpawnLocationsJob`  
- `Game.Objects.SpawnLocationConnectionSystem+FindSpawnLocationConnectionJob`  
- `Game.Objects.SpawnLocationConnectionSystem+TypeHandle`  

