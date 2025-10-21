# Game.Prefabs.FireStationData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.FireStationData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct FireStationData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.FireStationData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_FireEngineCapacity;
    public System.Int32 m_FireHelicopterCapacity;
    public System.Int32 m_DisasterResponseCapacity;
    public System.Single m_VehicleEfficiency;

    public System.Void Combine(Game.Prefabs.FireStationData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_FireEngineCapacity`  

```csharp
public System.Int32 m_FireEngineCapacity;
```

- `public System.Int32 m_FireHelicopterCapacity`  

```csharp
public System.Int32 m_FireHelicopterCapacity;
```

- `public System.Int32 m_DisasterResponseCapacity`  

```csharp
public System.Int32 m_DisasterResponseCapacity;
```

- `public System.Single m_VehicleEfficiency`  

```csharp
public System.Single m_VehicleEfficiency;
```


## Methods

- `public Combine(Game.Prefabs.FireStationData otherData) : System.Void`  

```csharp
public System.Void Combine(Game.Prefabs.FireStationData otherData);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


