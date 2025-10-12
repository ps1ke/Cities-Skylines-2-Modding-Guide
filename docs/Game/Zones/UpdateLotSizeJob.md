# Game.Zones.LotSizeJobs+UpdateLotSizeJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks`  
- `public Game.Prefabs.ZonePrefabs m_ZonePrefabs`  
- `public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData`  
- `public Unity.Entities.ComponentLookup<Game.Zones.ValidArea> m_ValidAreaData`  
- `public Unity.Entities.ComponentLookup<Game.Zones.BuildOrder> m_BuildOrderData`  
- `public Unity.Entities.ComponentLookup<Game.Common.Updated> m_UpdatedData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> m_ZoneData`  
- `public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells`  
- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree`  
- `public Unity.Entities.BufferLookup<Game.Zones.VacantLot> m_VacantLots`  
- `public Unity.Entities.EntityCommandBuffer+ParallelWriter m_CommandBuffer`  
- `public Unity.Collections.NativeQueue<Colossal.Mathematics.Bounds2> m_BoundsQueue`  

## Methods

- `public Execute(System.Int32 index) : System.Void`  
- `private ExpandArea(Unity.Entities.Entity entity, Game.Zones.Block block, Game.Zones.ValidArea validArea, Game.Zones.BuildOrder buildOrder, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2& expandedOffset, Game.Zones.Block& expandedBlock) : Unity.Collections.NativeArray<Game.Zones.Cell>`  
- `private ExpandLeft(Game.Zones.Block block, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, Game.Zones.ZoneType zone) : System.Void`  
- `private ExpandRight(Game.Zones.Block block, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, Game.Zones.ZoneType zone) : System.Void`  
- `private FindDepth(Game.Zones.Block block, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, Game.Zones.ZoneType zone) : System.Void`  
- `private FindHeight(Game.Zones.Block block, Unity.Collections.NativeArray<Game.Zones.Cell> cells, Unity.Mathematics.int2 min, Unity.Mathematics.int2 max, System.Int32& height) : System.Void`  
- `private WidthReductionLeft(Game.Zones.Block block, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, System.Int32 sizeOffset) : System.Void`  
- `private WidthReductionRight(Game.Zones.Block block, Unity.Mathematics.int2& min, Unity.Mathematics.int2& max, System.Int32 sizeOffset) : System.Void`  

## Nested types

- `Game.Zones.LotSizeJobs+UpdateLotSizeJob+Iterator`  

