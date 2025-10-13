# Game.Prefabs.TransportStationData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.TransportStationData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TransportStationData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.TransportStationData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_ComfortFactor;
    public System.Single m_LoadingFactor;
    public Game.Vehicles.EnergyTypes m_CarRefuelTypes;
    public Game.Vehicles.EnergyTypes m_TrainRefuelTypes;
    public Game.Vehicles.EnergyTypes m_WatercraftRefuelTypes;
    public Game.Vehicles.EnergyTypes m_AircraftRefuelTypes;

    public System.Void Combine(Game.Prefabs.TransportStationData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_ComfortFactor`  

```csharp
public System.Single m_ComfortFactor;
```

- `public System.Single m_LoadingFactor`  

```csharp
public System.Single m_LoadingFactor;
```

- `public Game.Vehicles.EnergyTypes m_CarRefuelTypes`  

```csharp
public Game.Vehicles.EnergyTypes m_CarRefuelTypes;
```

- `public Game.Vehicles.EnergyTypes m_TrainRefuelTypes`  

```csharp
public Game.Vehicles.EnergyTypes m_TrainRefuelTypes;
```

- `public Game.Vehicles.EnergyTypes m_WatercraftRefuelTypes`  

```csharp
public Game.Vehicles.EnergyTypes m_WatercraftRefuelTypes;
```

- `public Game.Vehicles.EnergyTypes m_AircraftRefuelTypes`  

```csharp
public Game.Vehicles.EnergyTypes m_AircraftRefuelTypes;
```


## Methods

- `public Combine(Game.Prefabs.TransportStationData otherData) : System.Void`  

```csharp
public System.Void Combine(Game.Prefabs.TransportStationData otherData);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


