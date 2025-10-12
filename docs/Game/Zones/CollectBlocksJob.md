# Game.Zones.CellCheckHelpers+CollectBlocksJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJob`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Queue1`  
- `public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Queue2`  
- `public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Queue3`  
- `public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_Queue4`  
- `public Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+SortedEntity> m_ResultList`  

## Methods

- `public Execute() : System.Void`  
- `private ProcessQueue(Unity.Collections.NativeQueue<Unity.Entities.Entity> queue) : System.Void`  
- `private RemoveDuplicates() : System.Void`  

