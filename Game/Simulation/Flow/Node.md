# Game.Simulation.Flow.Node

**Assembly:** `Game`  
**Namespace:** `Game.Simulation.Flow`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct Node
{
    public System.Int32 m_FirstConnection;
    public System.Int32 m_LastConnection;
    public System.Int32 m_Height;
    public System.Int32 m_Excess;
    public System.Int32 m_Version;
    public Game.Simulation.Flow.Identifier m_CutElementId;
    public System.Boolean m_Retreat;
    public System.Int32 m_Distance;
    public System.Int32 m_Predecessor;
    public System.Boolean m_Enqueued;

    public System.Int32 connectionCount { get; }

}
```


## Fields

- `public System.Int32 m_FirstConnection`  

```csharp
public System.Int32 m_FirstConnection;
```

- `public System.Int32 m_LastConnection`  

```csharp
public System.Int32 m_LastConnection;
```

- `public System.Int32 m_Height`  

```csharp
public System.Int32 m_Height;
```

- `public System.Int32 m_Excess`  

```csharp
public System.Int32 m_Excess;
```

- `public System.Int32 m_Version`  

```csharp
public System.Int32 m_Version;
```

- `public Game.Simulation.Flow.Identifier m_CutElementId`  

```csharp
public Game.Simulation.Flow.Identifier m_CutElementId;
```

- `public System.Boolean m_Retreat`  

```csharp
public System.Boolean m_Retreat;
```

- `public System.Int32 m_Distance`  

```csharp
public System.Int32 m_Distance;
```

- `public System.Int32 m_Predecessor`  

```csharp
public System.Int32 m_Predecessor;
```

- `public System.Boolean m_Enqueued`  

```csharp
public System.Boolean m_Enqueued;
```


## Properties

- `public System.Int32 connectionCount { get }`  

```csharp
public System.Int32 connectionCount { get; }
```


