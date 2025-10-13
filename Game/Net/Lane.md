# Game.Net.Lane

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `System.IEquatable<Game.Net.Lane>`, `Colossal.Serialization.Entities.IStrideSerializable`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Lane : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, System.IEquatable<Game.Net.Lane>, Colossal.Serialization.Entities.IStrideSerializable, Colossal.Serialization.Entities.ISerializable
{
    public Game.Pathfind.PathNode m_StartNode;
    public Game.Pathfind.PathNode m_MiddleNode;
    public Game.Pathfind.PathNode m_EndNode;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Net.Lane other);
    public virtual System.Int32 GetHashCode();
    public System.Int32 GetStride(Colossal.Serialization.Entities.Context context);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Pathfind.PathNode m_StartNode`  

```csharp
public Game.Pathfind.PathNode m_StartNode;
```

- `public Game.Pathfind.PathNode m_MiddleNode`  

```csharp
public Game.Pathfind.PathNode m_MiddleNode;
```

- `public Game.Pathfind.PathNode m_EndNode`  

```csharp
public Game.Pathfind.PathNode m_EndNode;
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Net.Lane other) : System.Boolean`  

```csharp
public bool Equals(Lane other)
	{
		if (m_StartNode.Equals(other.m_StartNode) && m_MiddleNode.Equals(other.m_MiddleNode))
		{
			return m_EndNode.Equals(other.m_EndNode);
		}
		return false;
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return m_MiddleNode.GetHashCode();
	}
```

- `public GetStride(Colossal.Serialization.Entities.Context context) : System.Int32`  

```csharp
public int GetStride(Context context)
	{
		return m_StartNode.GetStride(context) * 3;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


