# Game.Zones.CellOverlapJobs+CheckBlockOverlapJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+BlockOverlap> m_BlockOverlaps`  
- `public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+OverlapGroup> m_OverlapGroups`  
- `public Game.Prefabs.ZonePrefabs m_ZonePrefabs`  
- `public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData`  
- `public Unity.Entities.ComponentLookup<Game.Zones.BuildOrder> m_BuildOrderData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ZoneData> m_ZoneData`  
- `public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells`  
- `public Unity.Entities.ComponentLookup<Game.Zones.ValidArea> m_ValidAreaData`  

## Methods

- `public Execute(System.Int32 index) : System.Void`  

## Nested types

- `Game.Zones.CellOverlapJobs+CheckBlockOverlapJob+CellReduction`  
- `Game.Zones.CellOverlapJobs+CheckBlockOverlapJob+OverlapIterator`  

