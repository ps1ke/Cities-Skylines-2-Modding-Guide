# Game.Zones.CellCheckHelpers+FindUpdatedBlocksDoubleIterationJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelForDefer`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeArray<Colossal.Mathematics.Bounds2> m_Bounds`  
- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree`  
- `public Unity.Collections.NativeQueue<Unity.Entities.Entity> m_ResultQueue`  

## Methods

- `public Execute(System.Int32 index) : System.Void`  

## Nested types

- `Game.Zones.CellCheckHelpers+FindUpdatedBlocksDoubleIterationJob+FirstIterator`  
- `Game.Zones.CellCheckHelpers+FindUpdatedBlocksDoubleIterationJob+SecondIterator`  

