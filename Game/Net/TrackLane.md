# Game.Net.TrackLane

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct TrackLane : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_AccessRestriction;
    public Game.Net.TrackLaneFlags m_Flags;
    public System.Single m_SpeedLimit;
    public System.Single m_Curviness;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_AccessRestriction`  

```csharp
public Unity.Entities.Entity m_AccessRestriction;
```

- `public Game.Net.TrackLaneFlags m_Flags`  

```csharp
public Game.Net.TrackLaneFlags m_Flags;
```

- `public System.Single m_SpeedLimit`  

```csharp
public System.Single m_SpeedLimit;
```

- `public System.Single m_Curviness`  

```csharp
public System.Single m_Curviness;
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


