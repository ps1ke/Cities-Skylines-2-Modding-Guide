# Game.Prefabs.TrackLaneData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TrackLaneData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_FallbackPrefab;
    public Unity.Entities.Entity m_EndObjectPrefab;
    public Game.Net.TrackTypes m_TrackTypes;
    public System.Single m_MaxCurviness;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_FallbackPrefab`  

```csharp
public Unity.Entities.Entity m_FallbackPrefab;
```

- `public Unity.Entities.Entity m_EndObjectPrefab`  

```csharp
public Unity.Entities.Entity m_EndObjectPrefab;
```

- `public Game.Net.TrackTypes m_TrackTypes`  

```csharp
public Game.Net.TrackTypes m_TrackTypes;
```

- `public System.Single m_MaxCurviness`  

```csharp
public System.Single m_MaxCurviness;
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


