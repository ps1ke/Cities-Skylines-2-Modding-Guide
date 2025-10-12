# Game.Simulation.CarNavigationHelpers+FindBlockedLanesIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

## Fields

- `public Colossal.Mathematics.Bounds3 m_Bounds`  
- `public Colossal.Mathematics.Line3+Segment m_Line`  
- `public System.Single m_Radius`  
- `public Unity.Collections.NativeList<Game.Objects.BlockedLane> m_BlockedLanes`  
- `public Unity.Entities.BufferLookup<Game.Net.SubLane> m_SubLanes`  
- `public Unity.Entities.ComponentLookup<Game.Net.MasterLane> m_MasterLaneData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> m_PrefabLaneData`  

## Methods

- `public Intersect(Game.Common.QuadTreeBoundsXZ bounds) : System.Boolean`  
- `public Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity edgeEntity) : System.Void`  

