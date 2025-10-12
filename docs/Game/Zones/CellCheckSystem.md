# Game.Zones.CellCheckSystem

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Zones.UpdateCollectSystem m_ZoneUpdateCollectSystem`  
- `private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem`  
- `private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem`  
- `private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem`  
- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Prefabs.ZoneSystem m_ZonePrefabSystem`  
- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_DeletedBlocksQuery`  
- `private Game.Zones.CellCheckSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CellCheckSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private CollectUpdatedBlocks(Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+SortedEntity> updateBlocksList) : Unity.Jobs.JobHandle`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Zones.CellCheckSystem+TypeHandle`  

