# Game.Prefabs.NetPieceArea

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IComparable<Game.Prefabs.NetPieceArea>`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct NetPieceArea : Unity.Entities.IBufferElementData, System.IComparable<Game.Prefabs.NetPieceArea>
{
    public Game.Prefabs.NetAreaFlags m_Flags;
    public Unity.Mathematics.float3 m_Position;
    public System.Single m_Width;
    public Unity.Mathematics.float3 m_SnapPosition;
    public System.Single m_SnapWidth;

    public System.Int32 CompareTo(Game.Prefabs.NetPieceArea other);
}
```


## Fields

- `public Game.Prefabs.NetAreaFlags m_Flags`  

```csharp
public Game.Prefabs.NetAreaFlags m_Flags;
```

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public System.Single m_Width`  

```csharp
public System.Single m_Width;
```

- `public Unity.Mathematics.float3 m_SnapPosition`  

```csharp
public Unity.Mathematics.float3 m_SnapPosition;
```

- `public System.Single m_SnapWidth`  

```csharp
public System.Single m_SnapWidth;
```


## Methods

- `public CompareTo(Game.Prefabs.NetPieceArea other) : System.Int32`  

```csharp
public int CompareTo(NetPieceArea other)
	{
		return math.select(0, math.select(-1, 1, m_Position.x > other.m_Position.x), m_Position.x != other.m_Position.x);
	}
```


