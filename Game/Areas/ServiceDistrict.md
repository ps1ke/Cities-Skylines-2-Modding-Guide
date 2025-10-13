# Game.Areas.ServiceDistrict

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Areas.ServiceDistrict>`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct ServiceDistrict : Unity.Entities.IBufferElementData, System.IEquatable<Game.Areas.ServiceDistrict>, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_District;

    public ServiceDistrict(Unity.Entities.Entity district);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Areas.ServiceDistrict other);
    public virtual System.Int32 GetHashCode();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_District`  

```csharp
public Unity.Entities.Entity m_District;
```


## Constructors

- `public ServiceDistrict(Unity.Entities.Entity district)`  

```csharp
public ServiceDistrict(Entity district)
	{
		m_District = district;
	}
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Areas.ServiceDistrict other) : System.Boolean`  

```csharp
public bool Equals(ServiceDistrict other)
	{
		return m_District.Equals(other.m_District);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return m_District.GetHashCode();
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


