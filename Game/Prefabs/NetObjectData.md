# Game.Prefabs.NetObjectData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct NetObjectData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Game.Prefabs.CompositionFlags m_CompositionFlags;
    public Game.Net.RoadTypes m_RequireRoad;
    public Game.Net.RoadTypes m_RoadPassThrough;
    public Game.Net.TrackTypes m_TrackPassThrough;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Game.Prefabs.CompositionFlags m_CompositionFlags`  

```csharp
public Game.Prefabs.CompositionFlags m_CompositionFlags;
```

- `public Game.Net.RoadTypes m_RequireRoad`  

```csharp
public Game.Net.RoadTypes m_RequireRoad;
```

- `public Game.Net.RoadTypes m_RoadPassThrough`  

```csharp
public Game.Net.RoadTypes m_RoadPassThrough;
```

- `public Game.Net.TrackTypes m_TrackPassThrough`  

```csharp
public Game.Net.TrackTypes m_TrackPassThrough;
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


