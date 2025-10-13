# Game.Net.EdgeIterator

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct EdgeIterator
{
    private Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> m_Edges;
    private Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData;
    private Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData;
    private Unity.Entities.ComponentLookup<Game.Tools.Hidden> m_HiddenData;
    private Unity.Entities.DynamicBuffer<Game.Net.ConnectedEdge> m_Buffer;
    private System.Int32 m_Iterator;
    private Unity.Entities.Entity m_Node;
    private Unity.Entities.Entity m_Edge;
    private Unity.Entities.Entity m_OriginalEdge;
    private System.Boolean m_Permanent;
    private System.Boolean m_Delete;
    private System.Boolean m_Middles;

    public EdgeIterator(Unity.Entities.Entity edge, Unity.Entities.Entity node, Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> edges, Unity.Entities.ComponentLookup<Game.Net.Edge> edgeData, Unity.Entities.ComponentLookup<Game.Tools.Temp> tempData, Unity.Entities.ComponentLookup<Game.Tools.Hidden> hiddenData, System.Boolean includeMiddleConnections);

    public System.Void AddSorted(Unity.Entities.ComponentLookup`1[[Game.Net.BuildOrder, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildOrderData, Colossal.Collections.StackList`1[[Game.Net.EdgeIteratorValueSorted, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& list);
    private System.Boolean GetDelete(Unity.Entities.Entity entity);
    private System.Boolean GetDelete(Unity.Entities.Entity entity, Unity.Entities.Entity& original);
    public System.Int32 GetMaxCount();
    public System.Boolean GetNext(Game.Net.EdgeIteratorValue& value);
}
```


## Fields

- `private Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> m_Edges`  

```csharp
private Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> m_Edges;
```

- `private Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData;
```

- `private Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Tools.Temp> m_TempData;
```

- `private Unity.Entities.ComponentLookup<Game.Tools.Hidden> m_HiddenData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Tools.Hidden> m_HiddenData;
```

- `private Unity.Entities.DynamicBuffer<Game.Net.ConnectedEdge> m_Buffer`  

```csharp
private Unity.Entities.DynamicBuffer<Game.Net.ConnectedEdge> m_Buffer;
```

- `private System.Int32 m_Iterator`  

```csharp
private System.Int32 m_Iterator;
```

- `private Unity.Entities.Entity m_Node`  

```csharp
private Unity.Entities.Entity m_Node;
```

- `private Unity.Entities.Entity m_Edge`  

```csharp
private Unity.Entities.Entity m_Edge;
```

- `private Unity.Entities.Entity m_OriginalEdge`  

```csharp
private Unity.Entities.Entity m_OriginalEdge;
```

- `private System.Boolean m_Permanent`  

```csharp
private System.Boolean m_Permanent;
```

- `private System.Boolean m_Delete`  

```csharp
private System.Boolean m_Delete;
```

- `private System.Boolean m_Middles`  

```csharp
private System.Boolean m_Middles;
```


## Constructors

- `public EdgeIterator(Unity.Entities.Entity edge, Unity.Entities.Entity node, Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> edges, Unity.Entities.ComponentLookup<Game.Net.Edge> edgeData, Unity.Entities.ComponentLookup<Game.Tools.Temp> tempData, Unity.Entities.ComponentLookup<Game.Tools.Hidden> hiddenData, System.Boolean includeMiddleConnections = False)`  

```csharp
public EdgeIterator(Entity edge, Entity node, BufferLookup<ConnectedEdge> edges, ComponentLookup<Edge> edgeData, ComponentLookup<Temp> tempData, ComponentLookup<Hidden> hiddenData, bool includeMiddleConnections = false)
	{
		m_Node = node;
		m_Edge = edge;
		m_OriginalEdge = Entity.Null;
		m_Edges = edges;
		m_EdgeData = edgeData;
		m_TempData = tempData;
		m_HiddenData = hiddenData;
		m_Buffer = m_Edges[node];
		m_Iterator = 0;
		m_Permanent = !m_TempData.HasComponent(node);
		m_Delete = false;
		m_Middles = includeMiddleConnections;
		if (edge != Entity.Null)
		{
			m_Delete = GetDelete(edge, out m_OriginalEdge);
		}
		else if (!m_Permanent)
		{
			m_Delete = GetDelete(node);
		}
	}
```


## Methods

- `public AddSorted(Unity.Entities.ComponentLookup`1[[Game.Net.BuildOrder, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& buildOrderData, Colossal.Collections.StackList`1[[Game.Net.EdgeIteratorValueSorted, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& list) : System.Void`  

```csharp
public void AddSorted(ref ComponentLookup<BuildOrder> buildOrderData, ref StackList<EdgeIteratorValueSorted> list)
	{
		EdgeIteratorValue value;
		while (GetNext(out value))
		{
			buildOrderData.TryGetComponent(value.m_Edge, out var componentData);
			list.AddNoResize(new EdgeIteratorValueSorted
			{
				m_Edge = value.m_Edge,
				m_SortIndex = (uint)((ulong)((long)componentData.m_Start + (long)componentData.m_End) >> 1),
				m_End = value.m_End,
				m_Middle = value.m_Middle
			});
		}
		list.AsArray().Sort();
	}
```

- `private GetDelete(Unity.Entities.Entity entity) : System.Boolean`  

```csharp
private bool GetDelete(Entity entity, out Entity original)
	{
		if (m_TempData.TryGetComponent(entity, out var componentData))
		{
			original = componentData.m_Original;
			return (componentData.m_Flags & TempFlags.Delete) != 0;
		}
		original = Entity.Null;
		return false;
	}
```

- `private GetDelete(Unity.Entities.Entity entity, Unity.Entities.Entity& original) : System.Boolean`  

```csharp
private bool GetDelete(Entity entity, out Entity original)
	{
		if (m_TempData.TryGetComponent(entity, out var componentData))
		{
			original = componentData.m_Original;
			return (componentData.m_Flags & TempFlags.Delete) != 0;
		}
		original = Entity.Null;
		return false;
	}
```

- `public GetMaxCount() : System.Int32`  

```csharp
public int GetMaxCount()
	{
		int num = m_Buffer.Length;
		if (!m_Permanent && m_Edges.TryGetBuffer(m_TempData[m_Node].m_Original, out var bufferData))
		{
			num += bufferData.Length;
		}
		return num;
	}
```

- `public GetNext(Game.Net.EdgeIteratorValue& value) : System.Boolean`  

```csharp
public bool GetNext(out EdgeIteratorValue value)
	{
		while (true)
		{
			bool flag = m_Buffer.Length > m_Iterator;
			if (flag)
			{
				value.m_Edge = m_Buffer[m_Iterator++].m_Edge;
			}
			else
			{
				value.m_Edge = Entity.Null;
			}
			while (flag)
			{
				if (m_Permanent)
				{
					Edge edge = m_EdgeData[value.m_Edge];
					value.m_End = edge.m_End == m_Node;
					if (value.m_End || edge.m_Start == m_Node)
					{
						value.m_Middle = false;
						return true;
					}
					if (m_Middles)
					{
						value.m_Middle = true;
						return true;
					}
				}
				else if (m_Delete)
				{
					if (value.m_Edge == m_Edge || (m_HiddenData.HasComponent(value.m_Edge) && value.m_Edge != m_OriginalEdge))
					{
						Edge edge2 = m_EdgeData[value.m_Edge];
						value.m_End = edge2.m_End == m_Node;
						if (value.m_End || edge2.m_Start == m_Node)
						{
							value.m_Middle = false;
							return true;
						}
						if (m_Middles)
						{
							value.m_Middle = true;
							return true;
						}
					}
				}
				else if (!m_HiddenData.HasComponent(value.m_Edge) && !GetDelete(value.m_Edge))
				{
					Edge edge3 = m_EdgeData[value.m_Edge];
					value.m_End = edge3.m_End == m_Node;
					if (value.m_End || edge3.m_Start == m_Node)
					{
						value.m_Middle = false;
						return true;
					}
					if (m_Middles)
					{
						value.m_Middle = true;
						return true;
					}
				}
				flag = m_Buffer.Length > m_Iterator;
				if (flag)
				{
					value.m_Edge = m_Buffer[m_Iterator++].m_Edge;
				}
				else
				{
					value.m_Edge = Entity.Null;
				}
			}
			if (!m_TempData.TryGetComponent(m_Node, out var componentData))
			{
				break;
			}
			m_Node = componentData.m_Original;
			if (!m_Edges.TryGetBuffer(m_Node, out m_Buffer))
			{
				break;
			}
			m_Iterator = 0;
		}
		value.m_Edge = Entity.Null;
		value.m_End = false;
		value.m_Middle = false;
		return false;
	}
```


