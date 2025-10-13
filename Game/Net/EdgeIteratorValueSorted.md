# Game.Net.EdgeIteratorValueSorted

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IComparable<Game.Net.EdgeIteratorValueSorted>`  

## Code

```csharp
public sealed struct EdgeIteratorValueSorted : System.IComparable<Game.Net.EdgeIteratorValueSorted>
{
    public Unity.Entities.Entity m_Edge;
    public System.UInt32 m_SortIndex;
    public System.Boolean m_End;
    public System.Boolean m_Middle;

    public System.Int32 CompareTo(Game.Net.EdgeIteratorValueSorted other);
}
```


## Fields

- `public Unity.Entities.Entity m_Edge`  

```csharp
public Unity.Entities.Entity m_Edge;
```

- `public System.UInt32 m_SortIndex`  

```csharp
public System.UInt32 m_SortIndex;
```

- `public System.Boolean m_End`  

```csharp
public System.Boolean m_End;
```

- `public System.Boolean m_Middle`  

```csharp
public System.Boolean m_Middle;
```


## Methods

- `public CompareTo(Game.Net.EdgeIteratorValueSorted other) : System.Int32`  

```csharp
public int CompareTo(EdgeIteratorValueSorted other)
	{
		return math.select(0, math.select(1, -1, m_SortIndex < other.m_SortIndex), m_SortIndex != other.m_SortIndex);
	}
```


