# Game.Prefabs.RoadData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct RoadData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_ZoneBlockPrefab;
    public System.Single m_SpeedLimit;
    public Game.Prefabs.RoadFlags m_Flags;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_ZoneBlockPrefab`  

```csharp
public Unity.Entities.Entity m_ZoneBlockPrefab;
```

- `public System.Single m_SpeedLimit`  

```csharp
public System.Single m_SpeedLimit;
```

- `public Game.Prefabs.RoadFlags m_Flags`  

```csharp
public Game.Prefabs.RoadFlags m_Flags;
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


