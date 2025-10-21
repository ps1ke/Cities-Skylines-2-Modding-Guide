# Game.Creatures.CurrentVehicle

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CurrentVehicle : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_Vehicle;
    public Game.Creatures.CreatureVehicleFlags m_Flags;

    public CurrentVehicle(Unity.Entities.Entity vehicle, Game.Creatures.CreatureVehicleFlags flags);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Vehicle`  

```csharp
public Unity.Entities.Entity m_Vehicle;
```

- `public Game.Creatures.CreatureVehicleFlags m_Flags`  

```csharp
public Game.Creatures.CreatureVehicleFlags m_Flags;
```


## Constructors

- `public CurrentVehicle(Unity.Entities.Entity vehicle, Game.Creatures.CreatureVehicleFlags flags)`  

```csharp
public CurrentVehicle(Unity.Entities.Entity vehicle, Game.Creatures.CreatureVehicleFlags flags);
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


