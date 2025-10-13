# Game.Creatures.Pet

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Pet : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_HouseholdPet;
    public Game.Creatures.PetFlags m_Flags;

    public Pet(Unity.Entities.Entity householdPet);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_HouseholdPet`  

```csharp
public Unity.Entities.Entity m_HouseholdPet;
```

- `public Game.Creatures.PetFlags m_Flags`  

```csharp
public Game.Creatures.PetFlags m_Flags;
```


## Constructors

- `public Pet(Unity.Entities.Entity householdPet)`  

```csharp
public Pet(Entity householdPet)
	{
		m_HouseholdPet = householdPet;
		m_Flags = PetFlags.None;
	}
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


