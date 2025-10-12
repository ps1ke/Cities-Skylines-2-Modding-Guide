# Game.Net.LaneObjectUpdater

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Game.Objects.SearchSystem m_SearchSystem`  
- `private Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects`  
- `private Colossal.Collections.NativeParallelQueue<Game.Net.LaneObjectAction> m_LaneActionQueue`  
- `private Unity.Collections.NativeQueue<Game.Net.TreeObjectAction> m_TreeActionQueue`  

## Constructors

- `public LaneObjectUpdater(Unity.Entities.SystemBase system)`  

## Methods

- `public Apply(Unity.Entities.SystemBase system, Unity.Jobs.JobHandle dependencies) : Unity.Jobs.JobHandle`  
- `public Begin(Unity.Collections.Allocator allocator) : Game.Net.LaneObjectCommandBuffer`  

## Nested types

- `Game.Net.LaneObjectUpdater+UpdateLaneObjectsJob`  
- `Game.Net.LaneObjectUpdater+UpdateTreeObjectsJob`  

