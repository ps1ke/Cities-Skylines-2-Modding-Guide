# Game.Areas.ValidationHelpers+BrushAreaIterator

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>`  

## Code

```csharp
public sealed struct BrushAreaIterator : Colossal.Collections.INativeQuadTreeIterator<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>, Colossal.Collections.IUnsafeQuadTreeIterator<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ>
{
    public Unity.Entities.Entity m_BrushEntity;
    public Game.Tools.Brush m_Brush;
    public Colossal.Mathematics.Bounds3 m_BrushBounds;
    public Game.Tools.ValidationSystem+EntityData m_Data;
    public Unity.Collections.NativeQueue<Game.Tools.ErrorData> m_ErrorQueue;

    public System.Boolean Intersect(Game.Common.QuadTreeBoundsXZ bounds);
    public System.Void Iterate(Game.Common.QuadTreeBoundsXZ bounds, Game.Areas.AreaSearchItem areaItem2);
}
```


## Fields

- `public Unity.Entities.Entity m_BrushEntity`  

```csharp
public Unity.Entities.Entity m_BrushEntity;
```

- `public Game.Tools.Brush m_Brush`  

```csharp
public Game.Tools.Brush m_Brush;
```

- `public Colossal.Mathematics.Bounds3 m_BrushBounds`  

```csharp
public Colossal.Mathematics.Bounds3 m_BrushBounds;
```

- `public Game.Tools.ValidationSystem+EntityData m_Data`  

```csharp
public Game.Tools.ValidationSystem+EntityData m_Data;
```

- `public Unity.Collections.NativeQueue<Game.Tools.ErrorData> m_ErrorQueue`  

```csharp
public Unity.Collections.NativeQueue<Game.Tools.ErrorData> m_ErrorQueue;
```


## Methods

- `public Intersect(Game.Common.QuadTreeBoundsXZ bounds) : System.Boolean`  

```csharp
public System.Boolean Intersect(Game.Common.QuadTreeBoundsXZ bounds);
```

- `public Iterate(Game.Common.QuadTreeBoundsXZ bounds, Game.Areas.AreaSearchItem areaItem2) : System.Void`  

```csharp
public System.Void Iterate(Game.Common.QuadTreeBoundsXZ bounds, Game.Areas.AreaSearchItem areaItem2);
```


