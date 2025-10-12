# Game.Zones.CellCheckHelpers+FindOverlappingBlocksJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks`  
- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree`  
- `public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData`  
- `public Unity.Entities.ComponentLookup<Game.Zones.ValidArea> m_ValidAreaData`  
- `public Unity.Entities.ComponentLookup<Game.Zones.BuildOrder> m_BuildOrderData`  
- `public Unity.Collections.NativeQueue<Game.Zones.CellCheckHelpers+BlockOverlap> m_ResultQueue`  

## Methods

- `public Execute(System.Int32 index) : System.Void`  

## Nested types

- `Game.Zones.CellCheckHelpers+FindOverlappingBlocksJob+Iterator`  

