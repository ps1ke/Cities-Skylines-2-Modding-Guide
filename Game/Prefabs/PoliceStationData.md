# Game.Prefabs.PoliceStationData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Game.Prefabs.ICombineData<Game.Prefabs.PoliceStationData>`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct PoliceStationData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Game.Prefabs.ICombineData<Game.Prefabs.PoliceStationData>, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_PatrolCarCapacity;
    public System.Int32 m_PoliceHelicopterCapacity;
    public System.Int32 m_JailCapacity;
    public Game.Prefabs.PolicePurpose m_PurposeMask;

    public System.Void Combine(Game.Prefabs.PoliceStationData otherData);
    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_PatrolCarCapacity`  

```csharp
public System.Int32 m_PatrolCarCapacity;
```

- `public System.Int32 m_PoliceHelicopterCapacity`  

```csharp
public System.Int32 m_PoliceHelicopterCapacity;
```

- `public System.Int32 m_JailCapacity`  

```csharp
public System.Int32 m_JailCapacity;
```

- `public Game.Prefabs.PolicePurpose m_PurposeMask`  

```csharp
public Game.Prefabs.PolicePurpose m_PurposeMask;
```


## Methods

- `public Combine(Game.Prefabs.PoliceStationData otherData) : System.Void`  

```csharp
public System.Void Combine(Game.Prefabs.PoliceStationData otherData);
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```


