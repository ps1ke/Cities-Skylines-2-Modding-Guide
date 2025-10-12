# Game.Net.ConnectionWarningSystem+CollectOwnersJob2+BuildingIterator

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

## Fields

- `public Colossal.Mathematics.Bounds2 m_Bounds`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingData`  
- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  
- `public Unity.Collections.NativeParallelHashSet<Unity.Entities.Entity> m_OwnerSet`  
- `public Unity.Collections.NativeList<Unity.Entities.Entity> m_Owners`  

## Methods

- `public Intersect(Game.Common.QuadTreeBoundsXZ bounds) : System.Boolean`  
- `public Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity entity) : System.Void`  

