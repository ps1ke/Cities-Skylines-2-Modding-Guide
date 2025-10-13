# Game.Vehicles.Watercraft

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Watercraft : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Vehicles.WatercraftFlags m_Flags;

    public Watercraft(Game.Vehicles.WatercraftFlags flags);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Vehicles.WatercraftFlags m_Flags`  

```csharp
public Game.Vehicles.WatercraftFlags m_Flags;
```


## Constructors

- `public Watercraft(Game.Vehicles.WatercraftFlags flags)`  

```csharp
public Watercraft(WatercraftFlags flags)
	{
		m_Flags = flags;
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


