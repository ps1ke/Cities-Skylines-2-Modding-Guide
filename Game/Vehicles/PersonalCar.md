# Game.Vehicles.PersonalCar

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PersonalCar : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Keeper;
    public Game.Vehicles.PersonalCarFlags m_State;

    public PersonalCar(Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Keeper`  

```csharp
public Unity.Entities.Entity m_Keeper;
```

- `public Game.Vehicles.PersonalCarFlags m_State`  

```csharp
public Game.Vehicles.PersonalCarFlags m_State;
```


## Constructors

- `public PersonalCar(Unity.Entities.Entity keeper, Game.Vehicles.PersonalCarFlags state)`  

```csharp
public PersonalCar(Entity keeper, PersonalCarFlags state)
	{
		m_Keeper = keeper;
		m_State = state;
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


