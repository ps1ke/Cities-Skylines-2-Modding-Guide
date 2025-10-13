# Game.Simulation.ElectricityFlowEdge

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Unity.Entities.IComponentData`, `Unity.Entities.IQueryTypeParameter`, `Colossal.Serialization.Entities.ISerializable`  

## Code

```csharp
public sealed struct ElectricityFlowEdge : Unity.Entities.IComponentData, Unity.Entities.IQueryTypeParameter, Colossal.Serialization.Entities.ISerializable
{
    public System.Int32 m_Index;
    public Unity.Entities.Entity m_Start;
    public Unity.Entities.Entity m_End;
    public System.Int32 m_Capacity;
    public System.Int32 m_Flow;
    public Game.Simulation.ElectricityFlowEdgeFlags m_Flags;

    public Game.Net.FlowDirection direction { get; set; }
    public System.Boolean isBottleneck { get; }
    public System.Boolean isBeyondBottleneck { get; }
    public System.Boolean isDisconnected { get; }

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

- `public System.Int32 m_Capacity`  

```csharp
public System.Int32 m_Capacity;
```

- `public System.Int32 m_Flow`  

```csharp
public System.Int32 m_Flow;
```

- `public Game.Simulation.ElectricityFlowEdgeFlags m_Flags`  

```csharp
public Game.Simulation.ElectricityFlowEdgeFlags m_Flags;
```


## Properties

- `public Game.Net.FlowDirection direction { get; set }`  

```csharp
public Game.Net.FlowDirection direction { get; set; }
```

- `public System.Boolean isBottleneck { get }`  

```csharp
public System.Boolean isBottleneck { get; }
```

- `public System.Boolean isBeyondBottleneck { get }`  

```csharp
public System.Boolean isBeyondBottleneck { get; }
```

- `public System.Boolean isDisconnected { get }`  

```csharp
public System.Boolean isDisconnected { get; }
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


