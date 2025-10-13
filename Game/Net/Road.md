# Game.Net.Road

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct Road : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float4 m_TrafficFlowDuration0;
    public Unity.Mathematics.float4 m_TrafficFlowDuration1;
    public Unity.Mathematics.float4 m_TrafficFlowDistance0;
    public Unity.Mathematics.float4 m_TrafficFlowDistance1;
    public Game.Net.RoadFlags m_Flags;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float4 m_TrafficFlowDuration0`  

```csharp
public Unity.Mathematics.float4 m_TrafficFlowDuration0;
```

- `public Unity.Mathematics.float4 m_TrafficFlowDuration1`  

```csharp
public Unity.Mathematics.float4 m_TrafficFlowDuration1;
```

- `public Unity.Mathematics.float4 m_TrafficFlowDistance0`  

```csharp
public Unity.Mathematics.float4 m_TrafficFlowDistance0;
```

- `public Unity.Mathematics.float4 m_TrafficFlowDistance1`  

```csharp
public Unity.Mathematics.float4 m_TrafficFlowDistance1;
```

- `public Game.Net.RoadFlags m_Flags`  

```csharp
public Game.Net.RoadFlags m_Flags;
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


