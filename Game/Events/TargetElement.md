# Game.Events.TargetElement

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Events.TargetElement>`, `Colossal.Serialization.Entities.ISerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct TargetElement : Unity.Entities.IBufferElementData, System.IEquatable<Game.Events.TargetElement>, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Entity;

    public TargetElement(Unity.Entities.Entity entity);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Boolean Equals(Game.Events.TargetElement other);
    public virtual System.Int32 GetHashCode();
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```


## Constructors

- `public TargetElement(Unity.Entities.Entity entity)`  

```csharp
public TargetElement(Entity entity)
	{
		m_Entity = entity;
	}
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Equals(Game.Events.TargetElement other) : System.Boolean`  

```csharp
public bool Equals(TargetElement other)
	{
		return m_Entity.Equals(other.m_Entity);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return m_Entity.GetHashCode();
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


