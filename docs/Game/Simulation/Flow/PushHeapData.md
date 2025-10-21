# Game.Simulation.Flow.PushHeapData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation.Flow`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.ILessThan<Game.Simulation.Flow.PushHeapData>`  

## Code

```csharp
public sealed struct PushHeapData : Colossal.Collections.ILessThan<Game.Simulation.Flow.PushHeapData>
{
    public System.Int32 m_NodeIndex;
    public System.Int32 m_Height;

    public PushHeapData(System.Int32 nodeIndex, System.Int32 height);

    public System.Boolean LessThan(Game.Simulation.Flow.PushHeapData other);
    public virtual System.String ToString();
}
```


## Fields

- `public System.Int32 m_NodeIndex`  

```csharp
public System.Int32 m_NodeIndex;
```

- `public System.Int32 m_Height`  

```csharp
public System.Int32 m_Height;
```


## Constructors

- `public PushHeapData(System.Int32 nodeIndex, System.Int32 height)`  

```csharp
public PushHeapData(System.Int32 nodeIndex, System.Int32 height);
```


## Methods

- `public LessThan(Game.Simulation.Flow.PushHeapData other) : System.Boolean`  

```csharp
public System.Boolean LessThan(Game.Simulation.Flow.PushHeapData other);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


