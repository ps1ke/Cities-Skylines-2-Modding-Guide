# Game.Net.LaneConnection

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct LaneConnection : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_StartLane;
    public Unity.Entities.Entity m_EndLane;
    public System.Single m_StartPosition;
    public System.Single m_EndPosition;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_StartLane`  

```csharp
public Unity.Entities.Entity m_StartLane;
```

- `public Unity.Entities.Entity m_EndLane`  

```csharp
public Unity.Entities.Entity m_EndLane;
```

- `public System.Single m_StartPosition`  

```csharp
public System.Single m_StartPosition;
```

- `public System.Single m_EndPosition`  

```csharp
public System.Single m_EndPosition;
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


