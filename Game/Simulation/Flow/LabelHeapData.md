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
public LabelHeapData(int nodeIndex, int distance)
	{
		m_NodeIndex = nodeIndex;
		m_Distance = distance;
	}
```


## Methods

- `public LessThan(Game.Simulation.Flow.LabelHeapData other) : System.Boolean`  

```csharp
public bool LessThan(LabelHeapData other)
	{
		return m_Distance < other.m_Distance;
	}
```

- `public virtual ToString() : System.String`  

```csharp
public override string ToString()
	{
		return string.Format("{0}: {1}, {2}: {3}", "m_NodeIndex", m_NodeIndex, "m_Distance", m_Distance);
	}
```


