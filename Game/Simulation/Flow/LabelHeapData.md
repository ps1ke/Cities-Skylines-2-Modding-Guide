# Game.Simulation.Flow.LabelHeapData

**Assembly:** `Game`  
**Namespace:** `Game.Simulation.Flow`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.ILessThan<Game.Simulation.Flow.LabelHeapData>`  

## Code

```csharp
public sealed struct LabelHeapData : Colossal.Collections.ILessThan<Game.Simulation.Flow.LabelHeapData>
{
    public System.Int32 m_NodeIndex;
    public System.Int32 m_Distance;

    public LabelHeapData(System.Int32 nodeIndex, System.Int32 distance);

    public System.Boolean LessThan(Game.Simulation.Flow.LabelHeapData other);
    public virtual System.String ToString();
}
```


## Fields

- `public System.Int32 m_NodeIndex`  

```csharp
public System.Int32 m_NodeIndex;
```

- `public System.Int32 m_Distance`  

```csharp
public System.Int32 m_Distance;
```


## Constructors

- `public LabelHeapData(System.Int32 nodeIndex, System.Int32 distance)`  

```csharp
public LabelHeapData(System.Int32 nodeIndex, System.Int32 distance);
```


## Methods

- `public LessThan(Game.Simulation.Flow.LabelHeapData other) : System.Boolean`  

```csharp
public System.Boolean LessThan(Game.Simulation.Flow.LabelHeapData other);
```

- `public virtual ToString() : System.String`  

```csharp
public virtual System.String ToString();
```


