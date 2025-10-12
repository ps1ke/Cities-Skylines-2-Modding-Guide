# Game.Common.QuadTreeBoundsXZ

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Common.QuadTreeBoundsXZ>`, `Colossal.Mathematics.IBounds2<Game.Common.QuadTreeBoundsXZ>`  

## Fields

- `public Colossal.Mathematics.Bounds3 m_Bounds`  
- `public Game.Common.BoundsMask m_Mask`  
- `public System.Byte m_MinLod`  
- `public System.Byte m_MaxLod`  

## Constructors

- `public QuadTreeBoundsXZ(Colossal.Mathematics.Bounds3 bounds)`  
- `public QuadTreeBoundsXZ(Colossal.Mathematics.Bounds3 bounds, Game.Common.BoundsMask mask, System.Int32 lod)`  
- `public QuadTreeBoundsXZ(Colossal.Mathematics.Bounds3 bounds, Game.Common.BoundsMask mask, System.Int32 minLod, System.Int32 maxLod)`  

## Methods

- `public Center() : Unity.Mathematics.float2`  
- `public Equals(Game.Common.QuadTreeBoundsXZ other) : System.Boolean`  
- `public Intersect(Game.Common.QuadTreeBoundsXZ other) : System.Boolean`  
- `public Merge(Game.Common.QuadTreeBoundsXZ other) : Game.Common.QuadTreeBoundsXZ`  
- `public Reset() : System.Void`  
- `public Size() : Unity.Mathematics.float2`  

## Nested types

- `Game.Common.QuadTreeBoundsXZ+DebugIterator<TItem>`  

