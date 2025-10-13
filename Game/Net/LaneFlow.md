# Game.Net.LaneFlow

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct LaneFlow : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float4 m_Duration;
    public Unity.Mathematics.float4 m_Distance;
    public Unity.Mathematics.float2 m_Next;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float4 m_Duration`  

```csharp
public Unity.Mathematics.float4 m_Duration;
```

- `public Unity.Mathematics.float4 m_Distance`  

```csharp
public Unity.Mathematics.float4 m_Distance;
```

- `public Unity.Mathematics.float2 m_Next`  

```csharp
public Unity.Mathematics.float2 m_Next;
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


