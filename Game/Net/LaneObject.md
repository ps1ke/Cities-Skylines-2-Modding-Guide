# Game.Net.LaneObject

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Net.LaneObject>`, `System.IComparable<Game.Net.LaneObject>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct LaneObject : Unity.Entities.IBufferElementData, System.IEquatable<Game.Net.LaneObject>, System.IComparable<Game.Net.LaneObject>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_LaneObject;
    public Unity.Mathematics.float2 m_CurvePosition;

    public LaneObject(Unity.Entities.Entity laneObject);
    public LaneObject(Unity.Entities.Entity laneObject, Unity.Mathematics.float2 curvePosition);

    public System.Int32 CompareTo(Game.Net.LaneObject other);
    public System.Boolean Equals(Game.Net.LaneObject other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_LaneObject`  

```csharp
public Unity.Entities.Entity m_LaneObject;
```

- `public Unity.Mathematics.float2 m_CurvePosition`  

```csharp
public Unity.Mathematics.float2 m_CurvePosition;
```


## Constructors

- `public LaneObject(Unity.Entities.Entity laneObject)`  

```csharp
public LaneObject(Entity laneObject, float2 curvePosition)
	{
		m_LaneObject = laneObject;
		m_CurvePosition = curvePosition;
	}
```

- `public LaneObject(Unity.Entities.Entity laneObject, Unity.Mathematics.float2 curvePosition)`  

```csharp
public LaneObject(Entity laneObject, float2 curvePosition)
	{
		m_LaneObject = laneObject;
		m_CurvePosition = curvePosition;
	}
```


## Methods

- `public CompareTo(Game.Net.LaneObject other) : System.Int32`  

```csharp
public int CompareTo(LaneObject other)
	{
		return (int)math.sign(m_CurvePosition.x - other.m_CurvePosition.x);
	}
```

- `public Equals(Game.Net.LaneObject other) : System.Boolean`  

```csharp
public bool Equals(LaneObject other)
	{
		return m_LaneObject.Equals(other.m_LaneObject);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return (17 * 31 + m_LaneObject.GetHashCode()) * 31 + m_CurvePosition.GetHashCode();
	}
```


