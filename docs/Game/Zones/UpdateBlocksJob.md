# Game.Zones.CellCheckHelpers+UpdateBlocksJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks`  
- `public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData`  
- `public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells`  

## Methods

- `public Execute(System.Int32 index) : System.Void`  
- `private SetVisible(Game.Zones.Block blockData, Unity.Entities.DynamicBuffer<Game.Zones.Cell> cells) : System.Void`  

