# Game.Common.RaycastHit

**Assembly:** `Game`  
**Namespace:** `Game.Common`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IEquatable<Game.Common.RaycastHit>`  

## Code

```csharp
public sealed struct RaycastHit : System.IEquatable<Game.Common.RaycastHit>
{
    public Unity.Entities.Entity m_HitEntity;
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.float3 m_HitPosition;
    public Unity.Mathematics.float3 m_HitDirection;
    public Unity.Mathematics.int2 m_CellIndex;
    public System.Single m_NormalizedDistance;
    public System.Single m_CurvePosition;

    public System.Boolean Equals(Game.Common.RaycastHit other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_HitEntity`  

```csharp
public Unity.Entities.Entity m_HitEntity;
```

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.float3 m_HitPosition`  

```csharp
public Unity.Mathematics.float3 m_HitPosition;
```

- `public Unity.Mathematics.float3 m_HitDirection`  

```csharp
public Unity.Mathematics.float3 m_HitDirection;
```

- `public Unity.Mathematics.int2 m_CellIndex`  

```csharp
public Unity.Mathematics.int2 m_CellIndex;
```

- `public System.Single m_NormalizedDistance`  

```csharp
public System.Single m_NormalizedDistance;
```

- `public System.Single m_CurvePosition`  

```csharp
public System.Single m_CurvePosition;
```


## Methods

- `public Equals(Game.Common.RaycastHit other) : System.Boolean`  

```csharp
public bool Equals(RaycastHit other)
	{
		if (m_HitEntity.Equals(other.m_HitEntity) && m_Position.Equals(other.m_Position) && m_HitPosition.Equals(other.m_HitPosition) && m_HitDirection.Equals(other.m_HitDirection) && m_CellIndex.Equals(other.m_CellIndex) && m_NormalizedDistance == other.m_NormalizedDistance)
		{
			return m_CurvePosition == other.m_CurvePosition;
		}
		return false;
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return ((((((17 * 31 + m_HitEntity.GetHashCode()) * 31 + m_Position.GetHashCode()) * 31 + m_HitPosition.GetHashCode()) * 31 + m_HitDirection.GetHashCode()) * 31 + m_CellIndex.GetHashCode()) * 31 + m_NormalizedDistance.GetHashCode()) * 31 + m_CurvePosition.GetHashCode();
	}
```


