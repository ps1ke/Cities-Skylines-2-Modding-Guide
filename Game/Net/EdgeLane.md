# Game.Net.EdgeLane

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct EdgeLane : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float2 m_EdgeDelta;
    public System.Byte m_ConnectedStartCount;
    public System.Byte m_ConnectedEndCount;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float2 m_EdgeDelta`  

```csharp
public Unity.Mathematics.float2 m_EdgeDelta;
```

- `public System.Byte m_ConnectedStartCount`  

```csharp
public System.Byte m_ConnectedStartCount;
```

- `public System.Byte m_ConnectedEndCount`  

```csharp
public System.Byte m_ConnectedEndCount;
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


