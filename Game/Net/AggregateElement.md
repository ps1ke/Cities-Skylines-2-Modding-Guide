# Game.Net.AggregateElement

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Net.AggregateElement>`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct AggregateElement : Unity.Entities.IBufferElementData, System.IEquatable<Game.Net.AggregateElement>, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Edge;

    public AggregateElement(Unity.Entities.Entity edge);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Net.AggregateElement other);
    public virtual System.Int32 GetHashCode();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Edge`  

```csharp
public Unity.Entities.Entity m_Edge;
```


## Constructors

- `public AggregateElement(Unity.Entities.Entity edge)`  

```csharp
public AggregateElement(Entity edge)
	{
		m_Edge = edge;
	}
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Net.AggregateElement other) : System.Boolean`  

```csharp
public bool Equals(AggregateElement other)
	{
		return m_Edge.Equals(other.m_Edge);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return m_Edge.GetHashCode();
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


