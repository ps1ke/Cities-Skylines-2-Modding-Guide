# Game.Zones.RaycastJobs+FindZoneBlockJob

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Jobs.IJobParallelFor`  

**Attributes:** `BurstCompile`  

## Fields

- `public Unity.Collections.NativeArray<Game.Common.RaycastInput> m_Input`  
- `public Unity.Entities.ComponentLookup<Game.Zones.Block> m_BlockData`  
- `public Unity.Entities.BufferLookup<Game.Zones.Cell> m_Cells`  
- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Colossal.Mathematics.Bounds2> m_SearchTree`  
- `public Unity.Collections.NativeArray<Game.Common.RaycastResult> m_TerrainResults`  
- `public Colossal.Collections.NativeAccumulator<Game.Common.RaycastResult> m_Results`  

## Methods

- `public Execute(System.Int32 index) : System.Void`  

## Nested types

- `Game.Zones.RaycastJobs+FindZoneBlockJob+Iterator`  

