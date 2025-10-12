# Game.Zones.CellCheckHelpers+GroupOverlappingBlocksJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeArray<Game.Zones.CellCheckHelpers+SortedEntity> m_Blocks`  
- `public Unity.Collections.NativeQueue<Game.Zones.CellCheckHelpers+BlockOverlap> m_OverlapQueue`  
- `public Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+BlockOverlap> m_BlockOverlaps`  
- `public Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+OverlapGroup> m_OverlapGroups`  

## Methods

- `private CreateGroup(Unity.Collections.NativeList<System.Int32> groups) : System.Int32`  
- `public Execute() : System.Void`  
- `private MergeGroups(Unity.Collections.NativeList<System.Int32> groups, System.Int32 group1, System.Int32 group2) : System.Int32`  

