# Game.Prefabs.NetLaneData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct NetLaneData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_PathfindPrefab;
    public Game.Prefabs.LaneFlags m_Flags;
    public System.Single m_Width;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_PathfindPrefab`  

```csharp
public Unity.Entities.Entity m_PathfindPrefab;
```

- `public Game.Prefabs.LaneFlags m_Flags`  

```csharp
public Game.Prefabs.LaneFlags m_Flags;
```

- `public System.Single m_Width`  

```csharp
public System.Single m_Width;
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


