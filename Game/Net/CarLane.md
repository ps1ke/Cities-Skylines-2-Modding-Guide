# Game.Net.CarLane

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct CarLane : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public Unity.Entities.Entity m_AccessRestriction;
    public Game.Net.CarLaneFlags m_Flags;
    public System.Single m_DefaultSpeedLimit;
    public System.Single m_SpeedLimit;
    public System.Single m_Curviness;
    public System.UInt16 m_CarriagewayGroup;
    public System.Byte m_BlockageStart;
    public System.Byte m_BlockageEnd;
    public System.Byte m_CautionStart;
    public System.Byte m_CautionEnd;
    public System.Byte m_FlowOffset;
    public System.Byte m_LaneCrossCount;

    public Colossal.Mathematics.Bounds1 blockageBounds { get; }
    public Colossal.Mathematics.Bounds1 cautionBounds { get; }

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public Unity.Entities.Entity m_AccessRestriction`  

```csharp
public Unity.Entities.Entity m_AccessRestriction;
```

- `public Game.Net.CarLaneFlags m_Flags`  

```csharp
public Game.Net.CarLaneFlags m_Flags;
```

- `public System.Single m_DefaultSpeedLimit`  

```csharp
public System.Single m_DefaultSpeedLimit;
```

- `public System.Single m_SpeedLimit`  

```csharp
public System.Single m_SpeedLimit;
```

- `public System.Single m_Curviness`  

```csharp
public System.Single m_Curviness;
```

- `public System.UInt16 m_CarriagewayGroup`  

```csharp
public System.UInt16 m_CarriagewayGroup;
```

- `public System.Byte m_BlockageStart`  

```csharp
public System.Byte m_BlockageStart;
```

- `public System.Byte m_BlockageEnd`  

```csharp
public System.Byte m_BlockageEnd;
```

- `public System.Byte m_CautionStart`  

```csharp
public System.Byte m_CautionStart;
```

- `public System.Byte m_CautionEnd`  

```csharp
public System.Byte m_CautionEnd;
```

- `public System.Byte m_FlowOffset`  

```csharp
public System.Byte m_FlowOffset;
```

- `public System.Byte m_LaneCrossCount`  

```csharp
public System.Byte m_LaneCrossCount;
```


## Properties

- `public Colossal.Mathematics.Bounds1 blockageBounds { get }`  

```csharp
public Colossal.Mathematics.Bounds1 blockageBounds { get; }
```

- `public Colossal.Mathematics.Bounds1 cautionBounds { get }`  

```csharp
public Colossal.Mathematics.Bounds1 cautionBounds { get; }
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


