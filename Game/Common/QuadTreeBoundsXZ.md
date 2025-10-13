# Game.Common.QuadTreeBoundsXZ

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Common.QuadTreeBoundsXZ>`, `Colossal.Mathematics.IBounds2<Game.Common.QuadTreeBoundsXZ>`  

## Code

```csharp
public sealed struct QuadTreeBoundsXZ : System.IEquatable<Game.Common.QuadTreeBoundsXZ>, Colossal.Mathematics.IBounds2<Game.Common.QuadTreeBoundsXZ>
{
    public Colossal.Mathematics.Bounds3 m_Bounds;
    public Game.Common.BoundsMask m_Mask;
    public System.Byte m_MinLod;
    public System.Byte m_MaxLod;

    public QuadTreeBoundsXZ(Colossal.Mathematics.Bounds3 bounds);
    public QuadTreeBoundsXZ(Colossal.Mathematics.Bounds3 bounds, Game.Common.BoundsMask mask, System.Int32 lod);
    public QuadTreeBoundsXZ(Colossal.Mathematics.Bounds3 bounds, Game.Common.BoundsMask mask, System.Int32 minLod, System.Int32 maxLod);

    public Unity.Mathematics.float2 Center();
    public System.Boolean Equals(Game.Common.QuadTreeBoundsXZ other);
    public System.Boolean Intersect(Game.Common.QuadTreeBoundsXZ other);
    public Game.Common.QuadTreeBoundsXZ Merge(Game.Common.QuadTreeBoundsXZ other);
    public System.Void Reset();
    public Unity.Mathematics.float2 Size();
}
```


## Fields

- `public Colossal.Mathematics.Bounds3 m_Bounds`  

```csharp
public Colossal.Mathematics.Bounds3 m_Bounds;
```

- `public Game.Common.BoundsMask m_Mask`  

```csharp
public Game.Common.BoundsMask m_Mask;
```

- `public System.Byte m_MinLod`  

```csharp
public System.Byte m_MinLod;
```

- `public System.Byte m_MaxLod`  

```csharp
public System.Byte m_MaxLod;
```


## Constructors

- `public QuadTreeBoundsXZ(Colossal.Mathematics.Bounds3 bounds)`  

```csharp
public QuadTreeBoundsXZ(Colossal.Mathematics.Bounds3 bounds);
```

- `public QuadTreeBoundsXZ(Colossal.Mathematics.Bounds3 bounds, Game.Common.BoundsMask mask, System.Int32 lod)`  

```csharp
public QuadTreeBoundsXZ(Colossal.Mathematics.Bounds3 bounds, Game.Common.BoundsMask mask, System.Int32 lod);
```

- `public QuadTreeBoundsXZ(Colossal.Mathematics.Bounds3 bounds, Game.Common.BoundsMask mask, System.Int32 minLod, System.Int32 maxLod)`  

```csharp
public QuadTreeBoundsXZ(Colossal.Mathematics.Bounds3 bounds, Game.Common.BoundsMask mask, System.Int32 minLod, System.Int32 maxLod);
```


## Methods

- `public Center() : Unity.Mathematics.float2`  

```csharp
public Unity.Mathematics.float2 Center();
```

- `public Equals(Game.Common.QuadTreeBoundsXZ other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Common.QuadTreeBoundsXZ other);
```

- `public Intersect(Game.Common.QuadTreeBoundsXZ other) : System.Boolean`  

```csharp
public System.Boolean Intersect(Game.Common.QuadTreeBoundsXZ other);
```

- `public Merge(Game.Common.QuadTreeBoundsXZ other) : Game.Common.QuadTreeBoundsXZ`  

```csharp
public Game.Common.QuadTreeBoundsXZ Merge(Game.Common.QuadTreeBoundsXZ other);
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```

- `public Size() : Unity.Mathematics.float2`  

```csharp
public Unity.Mathematics.float2 Size();
```


## Nested types

- `Game.Common.QuadTreeBoundsXZ+DebugIterator<TItem>`  

