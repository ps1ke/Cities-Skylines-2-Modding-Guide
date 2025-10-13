# Game.Objects.Transform

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `System.IEquatable<Game.Objects.Transform>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Transform : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, System.IEquatable<Game.Objects.Transform>, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float3 m_Position;
    public Unity.Mathematics.quaternion m_Rotation;

    public Transform(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Objects.Transform other);
    public virtual System.Int32 GetHashCode();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float3 m_Position`  

```csharp
public Unity.Mathematics.float3 m_Position;
```

- `public Unity.Mathematics.quaternion m_Rotation`  

```csharp
public Unity.Mathematics.quaternion m_Rotation;
```


## Constructors

- `public Transform(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation)`  

```csharp
public Transform(float3 position, quaternion rotation)
	{
		m_Position = position;
		m_Rotation = rotation;
	}
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Objects.Transform other) : System.Boolean`  

```csharp
public bool Equals(Transform other)
	{
		if (m_Position.Equals(other.m_Position))
		{
			return m_Rotation.Equals(other.m_Rotation);
		}
		return false;
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return (17 * 31 + m_Position.GetHashCode()) * 31 + m_Rotation.GetHashCode();
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


