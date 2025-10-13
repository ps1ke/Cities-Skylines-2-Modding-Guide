# Game.Simulation.WaterPipeEdge

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct WaterPipeEdge : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Index;
    public Unity.Entities.Entity m_Start;
    public Unity.Entities.Entity m_End;
    public System.Int32 m_FreshFlow;
    public System.Single m_FreshPollution;
    public System.Int32 m_SewageFlow;
    public System.Int32 m_FreshCapacity;
    public System.Int32 m_SewageCapacity;
    public Game.Simulation.WaterPipeEdgeFlags m_Flags;

    public Unity.Mathematics.int2 flow { get; }
    public Unity.Mathematics.int2 capacity { get; }

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Serialize<TWriter>(TWriter writer);
}
```


## Fields

- `public System.Int32 m_Index`  

```csharp
public System.Int32 m_Index;
```

- `public Unity.Entities.Entity m_Start`  

```csharp
public Unity.Entities.Entity m_Start;
```

- `public Unity.Entities.Entity m_End`  

```csharp
public Unity.Entities.Entity m_End;
```

- `public System.Int32 m_FreshFlow`  

```csharp
public System.Int32 m_FreshFlow;
```

- `public System.Single m_FreshPollution`  

```csharp
public System.Single m_FreshPollution;
```

- `public System.Int32 m_SewageFlow`  

```csharp
public System.Int32 m_SewageFlow;
```

- `public System.Int32 m_FreshCapacity`  

```csharp
public System.Int32 m_FreshCapacity;
```

- `public System.Int32 m_SewageCapacity`  

```csharp
public System.Int32 m_SewageCapacity;
```

- `public Game.Simulation.WaterPipeEdgeFlags m_Flags`  

```csharp
public Game.Simulation.WaterPipeEdgeFlags m_Flags;
```


## Properties

- `public Unity.Mathematics.int2 flow { get }`  

```csharp
public Unity.Mathematics.int2 flow { get; }
```

- `public Unity.Mathematics.int2 capacity { get }`  

```csharp
public Unity.Mathematics.int2 capacity { get; }
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


