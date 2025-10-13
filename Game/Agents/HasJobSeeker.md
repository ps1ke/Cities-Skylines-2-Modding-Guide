# Game.Agents.HasJobSeeker

**Assembly:** `Game`  
**Namespace:** `Game.Agents`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`, `Unity.Entities.IEnableableComponent`  

## Code

```csharp
public sealed struct HasJobSeeker : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable, Unity.Entities.IEnableableComponent
{
    public Unity.Entities.Entity m_Seeker;
    public System.UInt32 m_LastJobSeekFrameIndex;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_Seeker`  

```csharp
public Unity.Entities.Entity m_Seeker;
```

- `public System.UInt32 m_LastJobSeekFrameIndex`  

```csharp
public System.UInt32 m_LastJobSeekFrameIndex;
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


