# Game.Net.LaneOverlap

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `Colossal.Serialization.Entities.IEmptySerializable`, `System.IComparable<Game.Net.LaneOverlap>`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct LaneOverlap : Unity.Entities.IBufferElementData, Colossal.Serialization.Entities.IEmptySerializable, System.IComparable<Game.Net.LaneOverlap>
{
    public Unity.Entities.Entity m_Other;
    public Game.Net.OverlapFlags m_Flags;
    public System.Byte m_ThisStart;
    public System.Byte m_ThisEnd;
    public System.Byte m_OtherStart;
    public System.Byte m_OtherEnd;
    public System.Byte m_Parallelism;
    public System.SByte m_PriorityDelta;

    public LaneOverlap(Unity.Entities.Entity other, Unity.Mathematics.float4 overlap, Game.Net.OverlapFlags flags, System.Single parallelism, System.Int32 priorityDelta);

    public System.Int32 CompareTo(Game.Net.LaneOverlap other);
}
```


## Fields

- `public Unity.Entities.Entity m_Other`  

```csharp
public Unity.Entities.Entity m_Other;
```

- `public Game.Net.OverlapFlags m_Flags`  

```csharp
public Game.Net.OverlapFlags m_Flags;
```

- `public System.Byte m_ThisStart`  

```csharp
public System.Byte m_ThisStart;
```

- `public System.Byte m_ThisEnd`  

```csharp
public System.Byte m_ThisEnd;
```

- `public System.Byte m_OtherStart`  

```csharp
public System.Byte m_OtherStart;
```

- `public System.Byte m_OtherEnd`  

```csharp
public System.Byte m_OtherEnd;
```

- `public System.Byte m_Parallelism`  

```csharp
public System.Byte m_Parallelism;
```

- `public System.SByte m_PriorityDelta`  

```csharp
public System.SByte m_PriorityDelta;
```


## Constructors

- `public LaneOverlap(Unity.Entities.Entity other, Unity.Mathematics.float4 overlap, Game.Net.OverlapFlags flags, System.Single parallelism, System.Int32 priorityDelta)`  

```csharp
public LaneOverlap(Entity other, float4 overlap, OverlapFlags flags, float parallelism, int priorityDelta)
	{
		int4 @int = math.clamp((int4)math.round(overlap * 255f), 0, 255);
		m_Other = other;
		m_ThisStart = (byte)@int.x;
		m_ThisEnd = (byte)@int.y;
		m_OtherStart = (byte)@int.z;
		m_OtherEnd = (byte)@int.w;
		m_Flags = flags;
		m_Parallelism = (byte)math.clamp((int)math.round(parallelism * 128f), 0, 255);
		m_PriorityDelta = (sbyte)priorityDelta;
	}
```


## Methods

- `public CompareTo(Game.Net.LaneOverlap other) : System.Int32`  

```csharp
public int CompareTo(LaneOverlap other)
	{
		return ((m_ThisStart << 8) | m_ThisEnd) - ((other.m_ThisStart << 8) | other.m_ThisEnd);
	}
```


