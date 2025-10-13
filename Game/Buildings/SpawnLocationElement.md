# Game.Buildings.SpawnLocationElement

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Buildings.SpawnLocationElement>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct SpawnLocationElement : Unity.Entities.IBufferElementData, System.IEquatable<Game.Buildings.SpawnLocationElement>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_SpawnLocation;
    public Game.Buildings.SpawnLocationType m_Type;

    public SpawnLocationElement(Unity.Entities.Entity spawnLocation, Game.Buildings.SpawnLocationType type);

    public System.Boolean Equals(Game.Buildings.SpawnLocationElement other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_SpawnLocation`  

```csharp
public Unity.Entities.Entity m_SpawnLocation;
```

- `public Game.Buildings.SpawnLocationType m_Type`  

```csharp
public Game.Buildings.SpawnLocationType m_Type;
```


## Constructors

- `public SpawnLocationElement(Unity.Entities.Entity spawnLocation, Game.Buildings.SpawnLocationType type)`  

```csharp
public SpawnLocationElement(Entity spawnLocation, SpawnLocationType type)
	{
		m_SpawnLocation = spawnLocation;
		m_Type = type;
	}
```


## Methods

- `public Equals(Game.Buildings.SpawnLocationElement other) : System.Boolean`  

```csharp
public bool Equals(SpawnLocationElement other)
	{
		return m_SpawnLocation.Equals(other.m_SpawnLocation);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return m_SpawnLocation.GetHashCode();
	}
```


