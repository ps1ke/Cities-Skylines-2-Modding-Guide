# Game.Citizens.HouseholdCitizen

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IBufferElementData`, `System.IEquatable<Game.Citizens.HouseholdCitizen>`, `Colossal.Serialization.Entities.IEmptySerializable`  

**Attributes:** `InternalBufferCapacity`  

## Code

```csharp
public sealed struct HouseholdCitizen : Unity.Entities.IBufferElementData, System.IEquatable<Game.Citizens.HouseholdCitizen>, Colossal.Serialization.Entities.IEmptySerializable
{
    public Unity.Entities.Entity m_Citizen;

    public HouseholdCitizen(Unity.Entities.Entity citizen);

    public System.Boolean Equals(Game.Citizens.HouseholdCitizen other);
    public virtual System.Int32 GetHashCode();
}
```


## Fields

- `public Unity.Entities.Entity m_Citizen`  

```csharp
public Unity.Entities.Entity m_Citizen;
```


## Constructors

- `public HouseholdCitizen(Unity.Entities.Entity citizen)`  

```csharp
public HouseholdCitizen(Unity.Entities.Entity citizen);
```


## Methods

- `public Equals(Game.Citizens.HouseholdCitizen other) : System.Boolean`  

```csharp
public System.Boolean Equals(Game.Citizens.HouseholdCitizen other);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```


