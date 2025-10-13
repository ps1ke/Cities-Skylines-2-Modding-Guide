# Game.Vehicles.Aircraft

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Aircraft : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Vehicles.AircraftFlags m_Flags;

    public Aircraft(Game.Vehicles.AircraftFlags flags);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Vehicles.AircraftFlags m_Flags`  

```csharp
public Game.Vehicles.AircraftFlags m_Flags;
```


## Constructors

- `public Aircraft(Game.Vehicles.AircraftFlags flags)`  

```csharp
public Aircraft(Game.Vehicles.AircraftFlags flags);
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


