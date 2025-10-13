# Game.Prefabs.TrafficSpawnerData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TrafficSpawnerData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Single m_SpawnRate;
    public Game.Net.RoadTypes m_RoadType;
    public Game.Net.TrackTypes m_TrackType;
    public System.Boolean m_NoSlowVehicles;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Single m_SpawnRate`  

```csharp
public System.Single m_SpawnRate;
```

- `public Game.Net.RoadTypes m_RoadType`  

```csharp
public Game.Net.RoadTypes m_RoadType;
```

- `public Game.Net.TrackTypes m_TrackType`  

```csharp
public Game.Net.TrackTypes m_TrackType;
```

- `public System.Boolean m_NoSlowVehicles`  

```csharp
public System.Boolean m_NoSlowVehicles;
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


