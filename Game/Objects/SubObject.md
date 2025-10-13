# Game.Objects.SubObject

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Objects.SubObject>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct SubObject : Unity.Entities.IBufferElementData, System.IEquatable<Game.Objects.SubObject>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_SubObject;

    public SubObject(Unity.Entities.Entity subObject);

    public System.Boolean Equals(Game.Objects.SubObject other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_SubObject`  

```csharp
public Unity.Entities.Entity m_SubObject;
```


## Constructors

- `public SubObject(Unity.Entities.Entity subObject)`  

```csharp
public SubObject(Entity subObject)
	{
		m_SubObject = subObject;
	}
```


## Methods

- `public Equals(Game.Objects.SubObject other) : System.Boolean`  

```csharp
public bool Equals(SubObject other)
	{
		return m_SubObject.Equals(other.m_SubObject);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return m_SubObject.GetHashCode();
	}
```


