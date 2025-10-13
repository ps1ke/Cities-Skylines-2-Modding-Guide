# Game.Simulation.Flow.Connection

**Assembly:** `Game`  
**Namespace:** `Game.Simulation.Flow`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct Connection
{
    public System.Int32 m_StartNode;
    public System.Int32 m_EndNode;
    public System.Int32 m_Edge;
    public System.Boolean m_Backwards;

    public System.Int32 GetIncomingCapacity(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges);
    public System.Int32 GetIncomingFinalFlow(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges);
    public System.Int32 GetIncomingResidualCapacity(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges);
    public System.Int32 GetOutgoingCapacity(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges);
    public System.Int32 GetOutgoingFinalFlow(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges);
    public System.Int32 GetOutgoingResidualCapacity(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges);
    public Game.Simulation.Flow.Connection Reverse();
}
```


## Fields

- `public System.Int32 m_StartNode`  

```csharp
public System.Int32 m_StartNode;
```

- `public System.Int32 m_EndNode`  

```csharp
public System.Int32 m_EndNode;
```

- `public System.Int32 m_Edge`  

```csharp
public System.Int32 m_Edge;
```

- `public System.Boolean m_Backwards`  

```csharp
public System.Boolean m_Backwards;
```


## Methods

- `public GetIncomingCapacity(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges) : System.Int32`  

```csharp
public int GetIncomingCapacity(NativeArray<Edge> edges)
	{
		return edges[m_Edge].GetCapacity(!m_Backwards);
	}
```

- `public GetIncomingFinalFlow(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges) : System.Int32`  

```csharp
public int GetIncomingFinalFlow(NativeArray<Edge> edges)
	{
		return edges[m_Edge].GetFinalFlow(!m_Backwards);
	}
```

- `public GetIncomingResidualCapacity(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges) : System.Int32`  

```csharp
public int GetIncomingResidualCapacity(NativeArray<Edge> edges)
	{
		return edges[m_Edge].GetResidualCapacity(!m_Backwards);
	}
```

- `public GetOutgoingCapacity(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges) : System.Int32`  

```csharp
public int GetOutgoingCapacity(NativeArray<Edge> edges)
	{
		return edges[m_Edge].GetCapacity(m_Backwards);
	}
```

- `public GetOutgoingFinalFlow(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges) : System.Int32`  

```csharp
public int GetOutgoingFinalFlow(NativeArray<Edge> edges)
	{
		return edges[m_Edge].GetFinalFlow(m_Backwards);
	}
```

- `public GetOutgoingResidualCapacity(Unity.Collections.NativeArray<Game.Simulation.Flow.Edge> edges) : System.Int32`  

```csharp
public int GetOutgoingResidualCapacity(NativeArray<Edge> edges)
	{
		return edges[m_Edge].GetResidualCapacity(m_Backwards);
	}
```

- `public Reverse() : Game.Simulation.Flow.Connection`  

```csharp
public Connection Reverse()
	{
		return new Connection
		{
			m_StartNode = m_EndNode,
			m_EndNode = m_StartNode,
			m_Edge = m_Edge,
			m_Backwards = !m_Backwards
		};
	}
```


