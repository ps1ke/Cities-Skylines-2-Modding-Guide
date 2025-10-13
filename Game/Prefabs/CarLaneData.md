# Game.Prefabs.CarLaneData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CarLaneData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_NotTrackLanePrefab;
    public Unity.Entities.Entity m_NotBusLanePrefab;
    public Game.Net.RoadTypes m_RoadTypes;
    public Game.Vehicles.SizeClass m_MaxSize;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_NotTrackLanePrefab`  

```csharp
public Unity.Entities.Entity m_NotTrackLanePrefab;
```

- `public Unity.Entities.Entity m_NotBusLanePrefab`  

```csharp
public Unity.Entities.Entity m_NotBusLanePrefab;
```

- `public Game.Net.RoadTypes m_RoadTypes`  

```csharp
public Game.Net.RoadTypes m_RoadTypes;
```

- `public Game.Vehicles.SizeClass m_MaxSize`  

```csharp
public Game.Vehicles.SizeClass m_MaxSize;
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


