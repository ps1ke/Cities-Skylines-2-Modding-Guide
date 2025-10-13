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
public QuadTreeBoundsXZ(Bounds3 bounds, BoundsMask mask, int minLod, int maxLod)
	{
		m_Bounds = bounds;
		m_Mask = mask;
		m_MinLod = (byte)minLod;
		m_MaxLod = (byte)maxLod;
	}
```

- `public QuadTreeBoundsXZ(Colossal.Mathematics.Bounds3 bounds, Game.Common.BoundsMask mask, System.Int32 lod)`  

```csharp
public QuadTreeBoundsXZ(Bounds3 bounds, BoundsMask mask, int minLod, int maxLod)
	{
		m_Bounds = bounds;
		m_Mask = mask;
		m_MinLod = (byte)minLod;
		m_MaxLod = (byte)maxLod;
	}
```

- `public QuadTreeBoundsXZ(Colossal.Mathematics.Bounds3 bounds, Game.Common.BoundsMask mask, System.Int32 minLod, System.Int32 maxLod)`  

```csharp
public QuadTreeBoundsXZ(Bounds3 bounds, BoundsMask mask, int minLod, int maxLod)
	{
		m_Bounds = bounds;
		m_Mask = mask;
		m_MinLod = (byte)minLod;
		m_MaxLod = (byte)maxLod;
	}
```


## Methods

- `public Center() : Unity.Mathematics.float2`  

```csharp
public float2 Center()
	{
		return MathUtils.Center(m_Bounds).xz;
	}
```

- `public Equals(Game.Common.QuadTreeBoundsXZ other) : System.Boolean`  

```csharp
public bool Equals(QuadTreeBoundsXZ other)
	{
		return m_Bounds.Equals(other.m_Bounds) & (m_Mask == other.m_Mask) & m_MinLod.Equals(other.m_MinLod) & m_MaxLod.Equals(other.m_MaxLod);
	}
```

- `public Intersect(Game.Common.QuadTreeBoundsXZ other) : System.Boolean`  

```csharp
public bool Intersect(QuadTreeBoundsXZ other)
	{
		return MathUtils.Intersect(m_Bounds, other.m_Bounds);
	}
```

- `public Merge(Game.Common.QuadTreeBoundsXZ other) : Game.Common.QuadTreeBoundsXZ`  

```csharp
public QuadTreeBoundsXZ Merge(QuadTreeBoundsXZ other)
	{
		return new QuadTreeBoundsXZ(m_Bounds | other.m_Bounds, m_Mask | other.m_Mask, math.min((int)m_MinLod, (int)other.m_MinLod), math.max((int)m_MaxLod, (int)other.m_MaxLod));
	}
```

- `public Reset() : System.Void`  

```csharp
public void Reset()
	{
		m_Bounds.min = float.MaxValue;
		m_Bounds.max = float.MinValue;
		m_Mask = (BoundsMask)0;
		m_MinLod = byte.MaxValue;
		m_MaxLod = 0;
	}
```

- `public Size() : Unity.Mathematics.float2`  

```csharp
public float2 Size()
	{
		return MathUtils.Size(m_Bounds).xz;
	}
```


## Nested types

- `Game.Common.QuadTreeBoundsXZ+DebugIterator<TItem>`  

