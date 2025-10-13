# Game.Prefabs.EmergencyShelterData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.EmergencyShelterData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct EmergencyShelterData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.EmergencyShelterData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_ShelterCapacity;
    public System.Int32 m_VehicleCapacity;

    public System.Void Combine(Game.Prefabs.EmergencyShelterData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_ShelterCapacity`  

```csharp
public System.Int32 m_ShelterCapacity;
```

- `public System.Int32 m_VehicleCapacity`  

```csharp
public System.Int32 m_VehicleCapacity;
```


## Methods

- `public Combine(Game.Prefabs.EmergencyShelterData otherData) : System.Void`  

```csharp
public System.Void Combine(Game.Prefabs.EmergencyShelterData otherData);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


