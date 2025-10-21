# Game.Prefabs.ParkingLaneData

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ParkingLaneData : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Mathematics.float2 m_SlotSize;
    public System.Single m_SlotAngle;
    public System.Single m_SlotInterval;
    public System.Single m_MaxCarLength;
    public Game.Net.RoadTypes m_RoadTypes;

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Mathematics.float2 m_SlotSize`  

```csharp
public Unity.Mathematics.float2 m_SlotSize;
```

- `public System.Single m_SlotAngle`  

```csharp
public System.Single m_SlotAngle;
```

- `public System.Single m_SlotInterval`  

```csharp
public System.Single m_SlotInterval;
```

- `public System.Single m_MaxCarLength`  

```csharp
public System.Single m_MaxCarLength;
```

- `public Game.Net.RoadTypes m_RoadTypes`  

```csharp
public Game.Net.RoadTypes m_RoadTypes;
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


