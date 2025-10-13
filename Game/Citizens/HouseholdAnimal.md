# Game.Citizens.HouseholdAnimal

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Citizens.HouseholdAnimal>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct HouseholdAnimal : Unity.Entities.IBufferElementData, System.IEquatable<Game.Citizens.HouseholdAnimal>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_HouseholdPet;

    public HouseholdAnimal(Unity.Entities.Entity householdPet);

    public System.Boolean Equals(Game.Citizens.HouseholdAnimal other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_HouseholdPet`  

```csharp
public Unity.Entities.Entity m_HouseholdPet;
```


## Constructors

- `public HouseholdAnimal(Unity.Entities.Entity householdPet)`  

```csharp
public HouseholdAnimal(Entity householdPet)
	{
		m_HouseholdPet = householdPet;
	}
```


## Methods

- `public Equals(Game.Citizens.HouseholdAnimal other) : System.Boolean`  

```csharp
public bool Equals(HouseholdAnimal other)
	{
		return m_HouseholdPet.Equals(other.m_HouseholdPet);
	}
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public override int GetHashCode()
	{
		return m_HouseholdPet.GetHashCode();
	}
```


