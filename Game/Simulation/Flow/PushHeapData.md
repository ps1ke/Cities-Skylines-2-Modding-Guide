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
public PushHeapData(int nodeIndex, int height)
	{
		m_NodeIndex = nodeIndex;
		m_Height = height;
	}
```


## Methods

- `public LessThan(Game.Simulation.Flow.PushHeapData other) : System.Boolean`  

```csharp
public bool LessThan(PushHeapData other)
	{
		return m_Height > other.m_Height;
	}
```

- `public virtual ToString() : System.String`  

```csharp
public override string ToString()
	{
		return string.Format("{0}: {1}, {2}: {3}", "m_NodeIndex", m_NodeIndex, "m_Height", m_Height);
	}
```


