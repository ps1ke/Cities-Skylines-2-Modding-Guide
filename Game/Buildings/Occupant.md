# Game.Buildings.Occupant

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Buildings.Occupant>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Occupant : Unity.Entities.IBufferElementData, System.IEquatable<Game.Buildings.Occupant>, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Occupant;

    public Occupant(Unity.Entities.Entity occupant);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Buildings.Occupant other);
    public virtual System.Int32 GetHashCode();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Occupant`  

```csharp
public Unity.Entities.Entity m_Occupant;
```


## Constructors

- `public Occupant(Unity.Entities.Entity occupant)`  

```csharp
public Occupant(Entity occupant)
	{
		m_Occupant = occupant;
	}
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Buildings.Occupant other) : System.Boolean`  

```csharp
public bool Equals(Occupant other)
	{
		return m_Occupant.Equals(other.m_Occupant);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return m_Occupant.GetHashCode();
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


