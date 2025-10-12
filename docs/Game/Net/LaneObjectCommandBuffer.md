# Game.Net.LaneObjectCommandBuffer

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Colossal.Collections.NativeParallelQueue<Game.Net.LaneObjectAction> m_LaneActionQueue`  
- `private Unity.Collections.NativeQueue<Game.Net.TreeObjectAction> m_TreeActionQueue`  

## Constructors

- `public LaneObjectCommandBuffer(Colossal.Collections.NativeParallelQueue<Game.Net.LaneObjectAction> laneActionQueue, Unity.Collections.NativeQueue<Game.Net.TreeObjectAction> treeActionQueue)`  

## Methods

- `public Add(Unity.Entities.Entity lane, Unity.Entities.Entity entity, Unity.Mathematics.float2 curvePosition) : System.Void`  
- `public Add(Unity.Entities.Entity entity, Colossal.Mathematics.Bounds3 bounds) : System.Void`  
- `public Remove(Unity.Entities.Entity lane, Unity.Entities.Entity entity) : System.Void`  
- `public Remove(Unity.Entities.Entity entity) : System.Void`  
- `public Update(Unity.Entities.Entity lane, Unity.Entities.Entity entity, Unity.Mathematics.float2 curvePosition) : System.Void`  
- `public Update(Unity.Entities.Entity entity, Colossal.Mathematics.Bounds3 bounds) : System.Void`  

