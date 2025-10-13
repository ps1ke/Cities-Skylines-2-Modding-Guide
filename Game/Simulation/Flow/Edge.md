# Game.Simulation.Flow.Edge

**Assembly:** `Game`  
**Namespace:** `Game.Simulation.Flow`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct Edge
{
    public System.Int32 m_Capacity;
    public Game.Net.FlowDirection m_Direction;
    public System.Int32 m_FinalFlow;
    public System.Int32 m_TempFlow;
    public Game.Simulation.Flow.Identifier m_CutElementId;

    public System.Int32 flow { get; }

    public Edge(System.Int32 capacity, Game.Net.FlowDirection direction);

    public System.Void FinalizeTempFlow();
    public System.Int32 GetCapacity(System.Boolean backwards);
    public System.Int32 GetFinalFlow(System.Boolean backwards);
    public System.Int32 GetResidualCapacity(System.Boolean backwards);
}
```


## Fields

- `public System.Int32 m_Capacity`  

```csharp
public System.Int32 m_Capacity;
```

- `public Game.Net.FlowDirection m_Direction`  

```csharp
public Game.Net.FlowDirection m_Direction;
```

- `public System.Int32 m_FinalFlow`  

```csharp
public System.Int32 m_FinalFlow;
```

- `public System.Int32 m_TempFlow`  

```csharp
public System.Int32 m_TempFlow;
```

- `public Game.Simulation.Flow.Identifier m_CutElementId`  

```csharp
public Game.Simulation.Flow.Identifier m_CutElementId;
```


## Properties

- `public System.Int32 flow { get }`  

```csharp
public System.Int32 flow { get; }
```


## Constructors

- `public Edge(System.Int32 capacity, Game.Net.FlowDirection direction = Both)`  

```csharp
public Edge(System.Int32 capacity, Game.Net.FlowDirection direction);
```


## Methods

- `public FinalizeTempFlow() : System.Void`  

```csharp
public System.Void FinalizeTempFlow();
```

- `public GetCapacity(System.Boolean backwards) : System.Int32`  

```csharp
public System.Int32 GetCapacity(System.Boolean backwards);
```

- `public GetFinalFlow(System.Boolean backwards) : System.Int32`  

```csharp
public System.Int32 GetFinalFlow(System.Boolean backwards);
```

- `public GetResidualCapacity(System.Boolean backwards) : System.Int32`  

```csharp
public System.Int32 GetResidualCapacity(System.Boolean backwards);
```


