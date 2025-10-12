# Game.Areas.CurrentDistrictSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Areas.UpdateCollectSystem m_UpdateCollectSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_CurrentDistrictQuery`  
- `private Game.Areas.CurrentDistrictSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CurrentDistrictSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Areas.CurrentDistrictSystem+FindUpdatedDistrictItemsJob`  
- `Game.Areas.CurrentDistrictSystem+CollectUpdatedDistrictItemsJob`  
- `Game.Areas.CurrentDistrictSystem+FindDistrictParallelJob`  
- `Game.Areas.CurrentDistrictSystem+FindDistrictChunkJob`  
- `Game.Areas.CurrentDistrictSystem+DistrictIterator`  
- `Game.Areas.CurrentDistrictSystem+TypeHandle`  

