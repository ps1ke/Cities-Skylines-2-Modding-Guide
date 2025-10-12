# Game.Areas.ValidationHelpers+BrushAreaIterator

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>`  

## Fields

- `public Unity.Entities.Entity m_BrushEntity`  
- `public Game.Tools.Brush m_Brush`  
- `public Colossal.Mathematics.Bounds3 m_BrushBounds`  
- `public Game.Tools.ValidationSystem+EntityData m_Data`  
- `public Unity.Collections.NativeQueue<Game.Tools.ErrorData> m_ErrorQueue`  

## Methods

- `public Intersect(Game.Common.QuadTreeBoundsXZ bounds) : System.Boolean`  
- `public Iterate(Game.Common.QuadTreeBoundsXZ bounds, Game.Areas.AreaSearchItem areaItem2) : System.Void`  

