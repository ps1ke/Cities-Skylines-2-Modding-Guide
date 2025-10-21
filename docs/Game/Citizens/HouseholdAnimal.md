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
public HouseholdAnimal(Unity.Entities.Entity householdPet);
```


## Methods

- `public Equals(Game.Citizens.HouseholdAnimal other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Citizens.HouseholdAnimal other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


