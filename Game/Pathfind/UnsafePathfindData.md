# Game.Pathfind.UnsafePathfindData

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

**Attributes:** `GenerateTestsForBurstCompatibility`  

## Code

```csharp
public sealed struct UnsafePathfindData : System.IDisposable
{
    public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.Edge> m_Edges;
    public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.EdgeID> m_FreeIDs;
    public Unity.Collections.LowLevel.Unsafe.UnsafeHashMap<Unity.Entities.Entity, Game.Pathfind.EdgeID> m_PathEdges;
    public Unity.Collections.LowLevel.Unsafe.UnsafeHashMap<Unity.Entities.Entity, Game.Pathfind.EdgeID> m_SecondaryEdges;
    public Unity.Collections.LowLevel.Unsafe.UnsafeHashMap<Game.Pathfind.PathNode, Game.Pathfind.NodeID> m_NodeIDs;
    public Unity.Collections.LowLevel.Unsafe.UnsafeHashMap<Game.Pathfind.NodeID, Game.Pathfind.PathNode> m_PathNodes;
    private Colossal.Collections.UnsafeHeapAllocator m_ConnectionAllocator;
    private System.Void* m_Connections;
    private System.Void* m_ReversedConnections;
    private System.Int32 m_NodeCount;
    private readonly Unity.Collections.Allocator m_AllocatorLabel;
    private static const System.Int32 NODE_META_SIZE;

    public UnsafePathfindData(Unity.Collections.Allocator allocator);

    private Game.Pathfind.NodeID AddConnection(Game.Pathfind.PathNode pathNode, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex);
    public System.Void AddEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID);
    private Game.Pathfind.NodeID AddReversedConnection(Game.Pathfind.PathNode pathNode, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex);
    public System.Void AddSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID);
    private Colossal.Collections.UnsafeHeapBlock AllocateConnections(System.Int32 connectionCapacity);
    public System.Void Clear();
    private Game.Pathfind.NodeID CreateConnections(System.Int32 connectionCapacity);
    public Game.Pathfind.EdgeID CreateEdge(Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location);
    private System.Void DestroyConnections(Game.Pathfind.NodeID nodeID);
    public System.Void DestroyEdge(Game.Pathfind.EdgeID edgeID);
    public System.Void Dispose();
    public System.Int32& GetAccessRequirement(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex);
    public System.Int32& GetConnection(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex);
    public System.UInt16& GetConnectionCapacity(Game.Pathfind.NodeID nodeID);
    public System.UInt16& GetConnectionCount(Game.Pathfind.NodeID nodeID);
    public System.Boolean GetEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID);
    public Game.Pathfind.Edge& GetEdge(Game.Pathfind.EdgeID edgeID);
    public System.Void GetMemoryStats(System.UInt32& used, System.UInt32& allocated);
    public System.Int32 GetNodeIDSize();
    public System.Int32& GetReversedAccessRequirement(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex);
    public System.Int32& GetReversedConnection(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex);
    public System.UInt16& GetReversedConnectionCapacity(Game.Pathfind.NodeID nodeID);
    public System.UInt16& GetReversedConnectionCount(Game.Pathfind.NodeID nodeID);
    public System.Boolean GetSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID);
    private System.Void RemoveConnection(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID);
    public System.Boolean RemoveEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID);
    private System.Void RemoveReversedConnection(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID);
    public System.Boolean RemoveSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID);
    private System.Void ResizeConnections(Game.Pathfind.NodeID& nodeID, System.Int32 connectionCapacity);
    public System.Void SetEdgeDirections(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode endNode, System.Boolean enableForward, System.Boolean enableBackward);
    public System.Void SwapConnections();
    private System.Void UpdateAccessRequirement(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex);
    public System.Void UpdateEdge(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location);
    private System.Void UpdateReversedAccessRequirement(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex);
}
```


## Fields

- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.Edge> m_Edges`  

```csharp
public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.Edge> m_Edges;
```

- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.EdgeID> m_FreeIDs`  

```csharp
public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.EdgeID> m_FreeIDs;
```

- `public Unity.Collections.LowLevel.Unsafe.UnsafeHashMap<Unity.Entities.Entity, Game.Pathfind.EdgeID> m_PathEdges`  

```csharp
public Unity.Collections.LowLevel.Unsafe.UnsafeHashMap<Unity.Entities.Entity, Game.Pathfind.EdgeID> m_PathEdges;
```

- `public Unity.Collections.LowLevel.Unsafe.UnsafeHashMap<Unity.Entities.Entity, Game.Pathfind.EdgeID> m_SecondaryEdges`  

```csharp
public Unity.Collections.LowLevel.Unsafe.UnsafeHashMap<Unity.Entities.Entity, Game.Pathfind.EdgeID> m_SecondaryEdges;
```

- `public Unity.Collections.LowLevel.Unsafe.UnsafeHashMap<Game.Pathfind.PathNode, Game.Pathfind.NodeID> m_NodeIDs`  

```csharp
public Unity.Collections.LowLevel.Unsafe.UnsafeHashMap<Game.Pathfind.PathNode, Game.Pathfind.NodeID> m_NodeIDs;
```

- `public Unity.Collections.LowLevel.Unsafe.UnsafeHashMap<Game.Pathfind.NodeID, Game.Pathfind.PathNode> m_PathNodes`  

```csharp
public Unity.Collections.LowLevel.Unsafe.UnsafeHashMap<Game.Pathfind.NodeID, Game.Pathfind.PathNode> m_PathNodes;
```

- `private Colossal.Collections.UnsafeHeapAllocator m_ConnectionAllocator`  

```csharp
private Colossal.Collections.UnsafeHeapAllocator m_ConnectionAllocator;
```

- `private System.Void* m_Connections`  

```csharp
private System.Void* m_Connections;
```

- `private System.Void* m_ReversedConnections`  

```csharp
private System.Void* m_ReversedConnections;
```

- `private System.Int32 m_NodeCount`  

```csharp
private System.Int32 m_NodeCount;
```

- `private readonly Unity.Collections.Allocator m_AllocatorLabel`  

```csharp
private readonly Unity.Collections.Allocator m_AllocatorLabel;
```

- `private static const System.Int32 NODE_META_SIZE`  

```csharp
private static const System.Int32 NODE_META_SIZE;
```


## Constructors

- `public UnsafePathfindData(Unity.Collections.Allocator allocator)`  

```csharp
public unsafe UnsafePathfindData(Allocator allocator)
	{
		m_Edges = new UnsafeList<Edge>(1000, allocator);
		m_FreeIDs = new UnsafeList<EdgeID>(100, allocator);
		m_PathEdges = new UnsafeHashMap<Entity, EdgeID>(1000, allocator);
		m_SecondaryEdges = new UnsafeHashMap<Entity, EdgeID>(1000, allocator);
		m_NodeIDs = new UnsafeHashMap<PathNode, NodeID>(1000, allocator);
		m_PathNodes = new UnsafeHashMap<NodeID, PathNode>(1000, allocator);
		m_ConnectionAllocator = new UnsafeHeapAllocator(1000u, 1u, allocator);
		m_Connections = UnsafeUtility.Malloc(m_ConnectionAllocator.Size * 4, (int)(m_ConnectionAllocator.MinimumAlignment * 4), allocator);
		m_ReversedConnections = UnsafeUtility.Malloc(m_ConnectionAllocator.Size * 4, (int)(m_ConnectionAllocator.MinimumAlignment * 4), allocator);
		m_AllocatorLabel = allocator;
		m_NodeCount = 0;
	}
```


## Methods

- `private AddConnection(Game.Pathfind.PathNode pathNode, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex) : Game.Pathfind.NodeID`  

```csharp
private NodeID AddConnection(PathNode pathNode, EdgeID edgeID, int accessIndex)
	{
		if (m_NodeIDs.TryGetValue(pathNode, out var item))
		{
			ref ushort connectionCount = ref GetConnectionCount(item);
			ref ushort connectionCapacity = ref GetConnectionCapacity(item);
			int num = (connectionCount << 1) + 2;
			if (num > connectionCapacity)
			{
				m_PathNodes.Remove(item);
				ResizeConnections(ref item, num);
				connectionCount = ref GetConnectionCount(item);
				m_NodeIDs[pathNode] = item;
				m_PathNodes.Add(item, pathNode);
			}
			ref int connection = ref GetConnection(item, connectionCount);
			ref int accessRequirement = ref GetAccessRequirement(item, connectionCount);
			connection = edgeID.m_Index;
			accessRequirement = accessIndex;
			connectionCount++;
			return item;
		}
		item = CreateConnections(2);
		ref ushort connectionCount2 = ref GetConnectionCount(item);
		ref int connection2 = ref GetConnection(item, connectionCount2);
		ref int accessRequirement2 = ref GetAccessRequirement(item, connectionCount2);
		connection2 = edgeID.m_Index;
		accessRequirement2 = accessIndex;
		connectionCount2++;
		m_NodeIDs.Add(pathNode, item);
		m_PathNodes.Add(item, pathNode);
		m_NodeCount++;
		return item;
	}
```

- `public AddEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID) : System.Void`  

```csharp
public void AddEdge(Entity owner, EdgeID edgeID)
	{
		m_Edges.ElementAt(edgeID.m_Index).m_Owner = owner;
		m_PathEdges.Add(owner, edgeID);
	}
```

- `private AddReversedConnection(Game.Pathfind.PathNode pathNode, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex) : Game.Pathfind.NodeID`  

```csharp
private NodeID AddReversedConnection(PathNode pathNode, EdgeID edgeID, int accessIndex)
	{
		if (m_NodeIDs.TryGetValue(pathNode, out var item))
		{
			ref ushort reversedConnectionCount = ref GetReversedConnectionCount(item);
			ref ushort reversedConnectionCapacity = ref GetReversedConnectionCapacity(item);
			int num = (reversedConnectionCount << 1) + 2;
			if (num > reversedConnectionCapacity)
			{
				m_PathNodes.Remove(item);
				ResizeConnections(ref item, num);
				reversedConnectionCount = ref GetReversedConnectionCount(item);
				m_NodeIDs[pathNode] = item;
				m_PathNodes.Add(item, pathNode);
			}
			ref int reversedConnection = ref GetReversedConnection(item, reversedConnectionCount);
			ref int reversedAccessRequirement = ref GetReversedAccessRequirement(item, reversedConnectionCount);
			reversedConnection = edgeID.m_Index;
			reversedAccessRequirement = accessIndex;
			reversedConnectionCount++;
			return item;
		}
		item = CreateConnections(2);
		ref ushort reversedConnectionCount2 = ref GetReversedConnectionCount(item);
		ref int reversedConnection2 = ref GetReversedConnection(item, reversedConnectionCount2);
		ref int reversedAccessRequirement2 = ref GetReversedAccessRequirement(item, reversedConnectionCount2);
		reversedConnection2 = edgeID.m_Index;
		reversedAccessRequirement2 = accessIndex;
		reversedConnectionCount2++;
		m_NodeIDs.Add(pathNode, item);
		m_PathNodes.Add(item, pathNode);
		m_NodeCount++;
		return item;
	}
```

- `public AddSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID) : System.Void`  

```csharp
public void AddSecondaryEdge(Entity owner, EdgeID edgeID)
	{
		m_Edges.ElementAt(edgeID.m_Index).m_Owner = owner;
		m_SecondaryEdges.Add(owner, edgeID);
	}
```

- `private AllocateConnections(System.Int32 connectionCapacity) : Colossal.Collections.UnsafeHeapBlock`  

```csharp
private unsafe UnsafeHeapBlock AllocateConnections(int connectionCapacity)
	{
		uint num = (uint)(connectionCapacity + 1);
		UnsafeHeapBlock result = m_ConnectionAllocator.Allocate(num);
		if (!result.Empty)
		{
			return result;
		}
		m_ConnectionAllocator.Resize(math.max(m_ConnectionAllocator.Size * 3 / 2, m_ConnectionAllocator.Size + num));
		void* ptr = UnsafeUtility.Malloc(m_ConnectionAllocator.Size * 4, (int)(m_ConnectionAllocator.MinimumAlignment * 4), m_AllocatorLabel);
		void* ptr2 = UnsafeUtility.Malloc(m_ConnectionAllocator.Size * 4, (int)(m_ConnectionAllocator.MinimumAlignment * 4), m_AllocatorLabel);
		uint num2 = m_ConnectionAllocator.OnePastHighestUsedAddress * 4;
		if (num2 != 0)
		{
			UnsafeUtility.MemCpy(ptr, m_Connections, num2);
			UnsafeUtility.MemCpy(ptr2, m_ReversedConnections, num2);
		}
		UnsafeUtility.Free(m_Connections, m_AllocatorLabel);
		UnsafeUtility.Free(m_ReversedConnections, m_AllocatorLabel);
		m_Connections = ptr;
		m_ReversedConnections = ptr2;
		return m_ConnectionAllocator.Allocate(num);
	}
```

- `public Clear() : System.Void`  

```csharp
public void Clear()
	{
		m_Edges.Clear();
		m_FreeIDs.Clear();
		m_PathEdges.Clear();
		m_SecondaryEdges.Clear();
		m_NodeIDs.Clear();
		m_PathNodes.Clear();
		m_ConnectionAllocator.Clear();
		m_NodeCount = 0;
	}
```

- `private CreateConnections(System.Int32 connectionCapacity) : Game.Pathfind.NodeID`  

```csharp
private NodeID CreateConnections(int connectionCapacity)
	{
		UnsafeHeapBlock unsafeHeapBlock = AllocateConnections(connectionCapacity);
		NodeID nodeID = new NodeID
		{
			m_Index = (int)unsafeHeapBlock.begin
		};
		ref ushort connectionCount = ref GetConnectionCount(nodeID);
		ref ushort connectionCapacity2 = ref GetConnectionCapacity(nodeID);
		connectionCount = 0;
		connectionCapacity2 = (ushort)(unsafeHeapBlock.end - unsafeHeapBlock.begin - 1);
		connectionCount = ref GetReversedConnectionCount(nodeID);
		ref ushort reversedConnectionCapacity = ref GetReversedConnectionCapacity(nodeID);
		connectionCount = 0;
		reversedConnectionCapacity = (ushort)(unsafeHeapBlock.end - unsafeHeapBlock.begin - 1);
		return nodeID;
	}
```

- `public CreateEdge(Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location) : Game.Pathfind.EdgeID`  

```csharp
public EdgeID CreateEdge(PathNode startNode, PathNode middleNode, PathNode endNode, PathSpecification specification, LocationSpecification location)
	{
		EdgeID edgeID;
		if (m_FreeIDs.Length > 0)
		{
			int num = m_FreeIDs.Length - 1;
			edgeID = m_FreeIDs[num];
			m_FreeIDs.Length = num;
		}
		else
		{
			edgeID = new EdgeID
			{
				m_Index = m_Edges.Length
			};
			m_Edges.Add(default(Edge));
		}
		ref Edge reference = ref m_Edges.ElementAt(edgeID.m_Index);
		reference.m_StartID = new NodeID
		{
			m_Index = -1
		};
		reference.m_MiddleID = new NodeID
		{
			m_Index = -1
		};
		reference.m_EndID = new NodeID
		{
			m_Index = -1
		};
		int accessIndex = math.select(-1, specification.m_AccessRequirement, (specification.m_Flags & EdgeFlags.AllowEnter) == 0);
		if ((specification.m_Flags & EdgeFlags.Forward) != 0)
		{
			reference.m_StartID = AddConnection(startNode.StripCurvePos(), edgeID, accessIndex);
			reference.m_EndID = AddReversedConnection(endNode.StripCurvePos(), edgeID, accessIndex);
		}
		if ((specification.m_Flags & EdgeFlags.AllowMiddle) != 0)
		{
			reference.m_MiddleID = AddConnection(middleNode.StripCurvePos(), edgeID, accessIndex);
			reference.m_MiddleID = AddReversedConnection(middleNode.StripCurvePos(), edgeID, accessIndex);
		}
		if ((specification.m_Flags & EdgeFlags.Backward) != 0)
		{
			reference.m_EndID = AddConnection(endNode.StripCurvePos(), edgeID, accessIndex);
			reference.m_StartID = AddReversedConnection(startNode.StripCurvePos(), edgeID, accessIndex);
		}
		reference.m_StartCurvePos = startNode.GetCurvePos();
		reference.m_EndCurvePos = endNode.GetCurvePos();
		reference.m_Specification = specification;
		reference.m_Location = location;
		return edgeID;
	}
```

- `private DestroyConnections(Game.Pathfind.NodeID nodeID) : System.Void`  

```csharp
private void DestroyConnections(NodeID nodeID)
	{
		ref ushort connectionCapacity = ref GetConnectionCapacity(nodeID);
		UnsafeHeapBlock block = new UnsafeHeapBlock((uint)nodeID.m_Index, (uint)(nodeID.m_Index + connectionCapacity + 1));
		m_ConnectionAllocator.Release(block);
	}
```

- `public DestroyEdge(Game.Pathfind.EdgeID edgeID) : System.Void`  

```csharp
public void DestroyEdge(EdgeID edgeID)
	{
		ref Edge reference = ref m_Edges.ElementAt(edgeID.m_Index);
		if ((reference.m_Specification.m_Flags & EdgeFlags.Forward) != 0)
		{
			RemoveConnection(reference.m_StartID, edgeID);
			RemoveReversedConnection(reference.m_EndID, edgeID);
		}
		if ((reference.m_Specification.m_Flags & EdgeFlags.AllowMiddle) != 0)
		{
			RemoveConnection(reference.m_MiddleID, edgeID);
			RemoveReversedConnection(reference.m_MiddleID, edgeID);
		}
		if ((reference.m_Specification.m_Flags & EdgeFlags.Backward) != 0)
		{
			RemoveConnection(reference.m_EndID, edgeID);
			RemoveReversedConnection(reference.m_StartID, edgeID);
		}
		if (edgeID.m_Index == m_Edges.Length - 1)
		{
			m_Edges.RemoveAt(edgeID.m_Index);
			return;
		}
		m_Edges[edgeID.m_Index] = default(Edge);
		m_FreeIDs.Add(in edgeID);
	}
```

- `public Dispose() : System.Void`  

```csharp
public unsafe void Dispose()
	{
		m_Edges.Dispose();
		m_FreeIDs.Dispose();
		m_PathEdges.Dispose();
		m_SecondaryEdges.Dispose();
		m_NodeIDs.Dispose();
		m_PathNodes.Dispose();
		m_ConnectionAllocator.Dispose();
		UnsafeUtility.Free(m_Connections, m_AllocatorLabel);
		UnsafeUtility.Free(m_ReversedConnections, m_AllocatorLabel);
	}
```

- `public GetAccessRequirement(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex) : System.Int32&`  

```csharp
public unsafe ref int GetAccessRequirement(NodeID nodeID, int connectionIndex)
	{
		return ref *(int*)((byte*)m_Connections + (nint)(nodeID.m_Index + (connectionIndex << 1) + 2) * (nint)4);
	}
```

- `public GetConnection(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex) : System.Int32&`  

```csharp
public unsafe ref int GetConnection(NodeID nodeID, int connectionIndex)
	{
		return ref *(int*)((byte*)m_Connections + (nint)(nodeID.m_Index + (connectionIndex << 1) + 1) * (nint)4);
	}
```

- `public GetConnectionCapacity(Game.Pathfind.NodeID nodeID) : System.UInt16&`  

```csharp
public unsafe ref ushort GetConnectionCapacity(NodeID nodeID)
	{
		return ref *(ushort*)((byte*)m_Connections + (nint)((nodeID.m_Index << 1) + 1) * (nint)2);
	}
```

- `public GetConnectionCount(Game.Pathfind.NodeID nodeID) : System.UInt16&`  

```csharp
public unsafe ref ushort GetConnectionCount(NodeID nodeID)
	{
		return ref *(ushort*)((byte*)m_Connections + (nint)(nodeID.m_Index << 1) * (nint)2);
	}
```

- `public GetEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  

```csharp
public ref Edge GetEdge(EdgeID edgeID)
	{
		return ref m_Edges.ElementAt(edgeID.m_Index);
	}
```

- `public GetEdge(Game.Pathfind.EdgeID edgeID) : Game.Pathfind.Edge&`  

```csharp
public ref Edge GetEdge(EdgeID edgeID)
	{
		return ref m_Edges.ElementAt(edgeID.m_Index);
	}
```

- `public GetMemoryStats(System.UInt32& used, System.UInt32& allocated) : System.Void`  

```csharp
public unsafe void GetMemoryStats(out uint used, out uint allocated)
	{
		used = (uint)(m_Edges.Length * (sizeof(Edge) + sizeof(Entity) + sizeof(EdgeID)) + m_FreeIDs.Length * sizeof(EdgeID) + m_NodeCount * (sizeof(PathNode) * 2 + sizeof(NodeID) * 2)) + m_ConnectionAllocator.UsedSpace * 4;
		allocated = (uint)(m_Edges.Capacity * sizeof(Edge) + m_FreeIDs.Capacity * sizeof(EdgeID) + (m_PathEdges.Capacity + m_SecondaryEdges.Capacity) * (sizeof(Entity) + sizeof(EdgeID)) + (int)(m_NodeIDs.Capacity + (uint)m_PathNodes.Capacity) * (sizeof(PathNode) + sizeof(NodeID))) + m_ConnectionAllocator.Size * 4;
	}
```

- `public GetNodeIDSize() : System.Int32`  

```csharp
public int GetNodeIDSize()
	{
		return (int)m_ConnectionAllocator.OnePastHighestUsedAddress;
	}
```

- `public GetReversedAccessRequirement(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex) : System.Int32&`  

```csharp
public unsafe ref int GetReversedAccessRequirement(NodeID nodeID, int connectionIndex)
	{
		return ref *(int*)((byte*)m_ReversedConnections + (nint)(nodeID.m_Index + (connectionIndex << 1) + 2) * (nint)4);
	}
```

- `public GetReversedConnection(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex) : System.Int32&`  

```csharp
public unsafe ref int GetReversedConnection(NodeID nodeID, int connectionIndex)
	{
		return ref *(int*)((byte*)m_ReversedConnections + (nint)(nodeID.m_Index + (connectionIndex << 1) + 1) * (nint)4);
	}
```

- `public GetReversedConnectionCapacity(Game.Pathfind.NodeID nodeID) : System.UInt16&`  

```csharp
public unsafe ref ushort GetReversedConnectionCapacity(NodeID nodeID)
	{
		return ref *(ushort*)((byte*)m_ReversedConnections + (nint)((nodeID.m_Index << 1) + 1) * (nint)2);
	}
```

- `public GetReversedConnectionCount(Game.Pathfind.NodeID nodeID) : System.UInt16&`  

```csharp
public unsafe ref ushort GetReversedConnectionCount(NodeID nodeID)
	{
		return ref *(ushort*)((byte*)m_ReversedConnections + (nint)(nodeID.m_Index << 1) * (nint)2);
	}
```

- `public GetSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  

```csharp
public bool GetSecondaryEdge(Entity owner, out EdgeID edgeID)
	{
		return m_SecondaryEdges.TryGetValue(owner, out edgeID);
	}
```

- `private RemoveConnection(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID) : System.Void`  

```csharp
private void RemoveConnection(NodeID nodeID, EdgeID edgeID)
	{
		ref ushort connectionCount = ref GetConnectionCount(nodeID);
		for (int i = 0; i < connectionCount; i++)
		{
			ref int connection = ref GetConnection(nodeID, i);
			if (connection == edgeID.m_Index)
			{
				if (i != --connectionCount)
				{
					ref int accessRequirement = ref GetAccessRequirement(nodeID, i);
					connection = GetConnection(nodeID, connectionCount);
					accessRequirement = GetAccessRequirement(nodeID, connectionCount);
				}
				else if (connectionCount == 0 && GetReversedConnectionCount(nodeID) == 0)
				{
					m_NodeIDs.Remove(m_PathNodes[nodeID]);
					m_PathNodes.Remove(nodeID);
					DestroyConnections(nodeID);
					m_NodeCount--;
				}
				break;
			}
		}
	}
```

- `public RemoveEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  

```csharp
public bool RemoveEdge(Entity owner, out EdgeID edgeID)
	{
		if (m_PathEdges.TryGetValue(owner, out edgeID))
		{
			m_PathEdges.Remove(owner);
			return true;
		}
		return false;
	}
```

- `private RemoveReversedConnection(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID) : System.Void`  

```csharp
private void RemoveReversedConnection(NodeID nodeID, EdgeID edgeID)
	{
		ref ushort reversedConnectionCount = ref GetReversedConnectionCount(nodeID);
		for (int i = 0; i < reversedConnectionCount; i++)
		{
			ref int reversedConnection = ref GetReversedConnection(nodeID, i);
			if (reversedConnection == edgeID.m_Index)
			{
				if (i != --reversedConnectionCount)
				{
					ref int reversedAccessRequirement = ref GetReversedAccessRequirement(nodeID, i);
					reversedConnection = GetReversedConnection(nodeID, reversedConnectionCount);
					reversedAccessRequirement = GetReversedAccessRequirement(nodeID, reversedConnectionCount);
				}
				else if (reversedConnectionCount == 0 && GetConnectionCount(nodeID) == 0)
				{
					m_NodeIDs.Remove(m_PathNodes[nodeID]);
					m_PathNodes.Remove(nodeID);
					DestroyConnections(nodeID);
					m_NodeCount--;
				}
				break;
			}
		}
	}
```

- `public RemoveSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  

```csharp
public bool RemoveSecondaryEdge(Entity owner, out EdgeID edgeID)
	{
		if (m_SecondaryEdges.TryGetValue(owner, out edgeID))
		{
			m_SecondaryEdges.Remove(owner);
			return true;
		}
		return false;
	}
```

- `private ResizeConnections(Game.Pathfind.NodeID& nodeID, System.Int32 connectionCapacity) : System.Void`  

```csharp
private void ResizeConnections(ref NodeID nodeID, int connectionCapacity)
	{
		UnsafeHeapBlock unsafeHeapBlock = AllocateConnections(connectionCapacity);
		UnsafeHeapBlock block = new UnsafeHeapBlock((uint)nodeID.m_Index, (uint)(nodeID.m_Index + GetConnectionCapacity(nodeID) + 1));
		NodeID nodeID2 = new NodeID
		{
			m_Index = (int)unsafeHeapBlock.begin
		};
		ref ushort connectionCount = ref GetConnectionCount(nodeID);
		ref ushort connectionCount2 = ref GetConnectionCount(nodeID2);
		ref ushort connectionCapacity2 = ref GetConnectionCapacity(nodeID2);
		connectionCount2 = connectionCount;
		connectionCapacity2 = (ushort)(unsafeHeapBlock.end - unsafeHeapBlock.begin - 1);
		for (int i = 0; i < connectionCount; i++)
		{
			ref int connection = ref GetConnection(nodeID, i);
			ref int accessRequirement = ref GetAccessRequirement(nodeID, i);
			ref int connection2 = ref GetConnection(nodeID2, i);
			ref int accessRequirement2 = ref GetAccessRequirement(nodeID2, i);
			connection2 = connection;
			accessRequirement2 = accessRequirement;
			ref Edge reference = ref m_Edges.ElementAt(connection);
			reference.m_StartID.m_Index = math.select(reference.m_StartID.m_Index, nodeID2.m_Index, reference.m_StartID.Equals(nodeID));
			reference.m_MiddleID.m_Index = math.select(reference.m_MiddleID.m_Index, nodeID2.m_Index, reference.m_MiddleID.Equals(nodeID));
			reference.m_EndID.m_Index = math.select(reference.m_EndID.m_Index, nodeID2.m_Index, reference.m_EndID.Equals(nodeID));
		}
		connectionCount = ref GetReversedConnectionCount(nodeID);
		connectionCount2 = ref GetReversedConnectionCount(nodeID2);
		ref ushort reversedConnectionCapacity = ref GetReversedConnectionCapacity(nodeID2);
		connectionCount2 = connectionCount;
		reversedConnectionCapacity = (ushort)(unsafeHeapBlock.end - unsafeHeapBlock.begin - 1);
		for (int j = 0; j < connectionCount; j++)
		{
			ref int reversedConnection = ref GetReversedConnection(nodeID, j);
			ref int reversedAccessRequirement = ref GetReversedAccessRequirement(nodeID, j);
			ref int reversedConnection2 = ref GetReversedConnection(nodeID2, j);
			ref int reversedAccessRequirement2 = ref GetReversedAccessRequirement(nodeID2, j);
			reversedConnection2 = reversedConnection;
			reversedAccessRequirement2 = reversedAccessRequirement;
			ref Edge reference2 = ref m_Edges.ElementAt(reversedConnection);
			reference2.m_StartID.m_Index = math.select(reference2.m_StartID.m_Index, nodeID2.m_Index, reference2.m_StartID.Equals(nodeID));
			reference2.m_MiddleID.m_Index = math.select(reference2.m_MiddleID.m_Index, nodeID2.m_Index, reference2.m_MiddleID.Equals(nodeID));
			reference2.m_EndID.m_Index = math.select(reference2.m_EndID.m_Index, nodeID2.m_Index, reference2.m_EndID.Equals(nodeID));
		}
		m_ConnectionAllocator.Release(block);
		nodeID = nodeID2;
	}
```

- `public SetEdgeDirections(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode endNode, System.Boolean enableForward, System.Boolean enableBackward) : System.Void`  

```csharp
public void SetEdgeDirections(EdgeID edgeID, PathNode startNode, PathNode endNode, bool enableForward, bool enableBackward)
	{
		ref Edge reference = ref m_Edges.ElementAt(edgeID.m_Index);
		int accessIndex = math.select(-1, reference.m_Specification.m_AccessRequirement, (reference.m_Specification.m_Flags & EdgeFlags.AllowEnter) == 0);
		if (enableForward != ((reference.m_Specification.m_Flags & EdgeFlags.Forward) != 0))
		{
			if (enableForward)
			{
				reference.m_StartID = AddConnection(startNode.StripCurvePos(), edgeID, accessIndex);
				reference.m_EndID = AddReversedConnection(endNode.StripCurvePos(), edgeID, accessIndex);
				reference.m_Specification.m_Flags |= EdgeFlags.Forward;
			}
			else
			{
				RemoveConnection(reference.m_StartID, edgeID);
				RemoveReversedConnection(reference.m_EndID, edgeID);
				reference.m_Specification.m_Flags &= ~EdgeFlags.Forward;
			}
		}
		if (enableBackward != ((reference.m_Specification.m_Flags & EdgeFlags.Backward) != 0))
		{
			if (enableBackward)
			{
				reference.m_EndID = AddConnection(endNode.StripCurvePos(), edgeID, accessIndex);
				reference.m_StartID = AddReversedConnection(startNode.StripCurvePos(), edgeID, accessIndex);
				reference.m_Specification.m_Flags |= EdgeFlags.Backward;
			}
			else
			{
				RemoveConnection(reference.m_EndID, edgeID);
				RemoveReversedConnection(reference.m_StartID, edgeID);
				reference.m_Specification.m_Flags &= ~EdgeFlags.Backward;
			}
		}
		if ((reference.m_Specification.m_Flags & (EdgeFlags.Forward | EdgeFlags.Backward)) == 0)
		{
			reference.m_StartID = new NodeID
			{
				m_Index = -1
			};
			reference.m_EndID = new NodeID
			{
				m_Index = -1
			};
		}
	}
```

- `public SwapConnections() : System.Void`  

```csharp
public unsafe void SwapConnections()
	{
		void* connections = m_Connections;
		m_Connections = m_ReversedConnections;
		m_ReversedConnections = connections;
	}
```

- `private UpdateAccessRequirement(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex) : System.Void`  

```csharp
private void UpdateAccessRequirement(NodeID nodeID, EdgeID edgeID, int accessIndex)
	{
		ref ushort connectionCount = ref GetConnectionCount(nodeID);
		for (int i = 0; i < connectionCount; i++)
		{
			if (GetConnection(nodeID, i) == edgeID.m_Index)
			{
				GetAccessRequirement(nodeID, i) = accessIndex;
				break;
			}
		}
	}
```

- `public UpdateEdge(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location) : System.Void`  

```csharp
public void UpdateEdge(EdgeID edgeID, PathNode startNode, PathNode middleNode, PathNode endNode, PathSpecification specification, LocationSpecification location)
	{
		ref Edge reference = ref m_Edges.ElementAt(edgeID.m_Index);
		EdgeFlags edgeFlags = reference.m_Specification.m_Flags & specification.m_Flags;
		EdgeFlags edgeFlags2 = (EdgeFlags)((uint)reference.m_Specification.m_Flags & (uint)(ushort)(~(int)specification.m_Flags));
		EdgeFlags edgeFlags3 = (EdgeFlags)((uint)(ushort)(~(int)reference.m_Specification.m_Flags) & (uint)specification.m_Flags);
		EdgeFlags edgeFlags4 = edgeFlags2;
		EdgeFlags edgeFlags5 = edgeFlags3;
		if (!m_NodeIDs.TryGetValue(startNode.StripCurvePos(), out var item))
		{
			item = new NodeID
			{
				m_Index = -2
			};
		}
		if (!m_NodeIDs.TryGetValue(middleNode.StripCurvePos(), out var item2))
		{
			item2 = new NodeID
			{
				m_Index = -2
			};
		}
		if (!m_NodeIDs.TryGetValue(endNode.StripCurvePos(), out var item3))
		{
			item3 = new NodeID
			{
				m_Index = -2
			};
		}
		EdgeFlags edgeFlags6 = edgeFlags & EdgeFlags.Forward;
		EdgeFlags edgeFlags7 = edgeFlags & EdgeFlags.AllowMiddle;
		EdgeFlags edgeFlags8 = edgeFlags & EdgeFlags.Backward;
		if (!reference.m_StartID.Equals(item))
		{
			edgeFlags2 |= edgeFlags6;
			edgeFlags3 |= edgeFlags6;
			edgeFlags4 |= edgeFlags8;
			edgeFlags5 |= edgeFlags8;
		}
		if (!reference.m_MiddleID.Equals(item2))
		{
			edgeFlags2 |= edgeFlags7;
			edgeFlags3 |= edgeFlags7;
			edgeFlags4 |= edgeFlags7;
			edgeFlags5 |= edgeFlags7;
		}
		if (!reference.m_EndID.Equals(item3))
		{
			edgeFlags2 |= edgeFlags8;
			edgeFlags3 |= edgeFlags8;
			edgeFlags4 |= edgeFlags6;
			edgeFlags5 |= edgeFlags6;
		}
		int num = math.select(-1, specification.m_AccessRequirement, (specification.m_Flags & EdgeFlags.AllowEnter) == 0);
		int num2 = math.select(-1, reference.m_Specification.m_AccessRequirement, (reference.m_Specification.m_Flags & EdgeFlags.AllowEnter) == 0);
		Edge edge = reference;
		if ((edgeFlags2 & EdgeFlags.Forward) != 0)
		{
			RemoveConnection(edge.m_StartID, edgeID);
		}
		if ((edgeFlags2 & EdgeFlags.AllowMiddle) != 0)
		{
			RemoveConnection(edge.m_MiddleID, edgeID);
		}
		if ((edgeFlags2 & EdgeFlags.Backward) != 0)
		{
			RemoveConnection(edge.m_EndID, edgeID);
		}
		if ((edgeFlags3 & EdgeFlags.Forward) != 0)
		{
			reference.m_StartID = AddConnection(startNode.StripCurvePos(), edgeID, num);
		}
		if ((edgeFlags3 & EdgeFlags.AllowMiddle) != 0)
		{
			reference.m_MiddleID = AddConnection(middleNode.StripCurvePos(), edgeID, num);
		}
		if ((edgeFlags3 & EdgeFlags.Backward) != 0)
		{
			reference.m_EndID = AddConnection(endNode.StripCurvePos(), edgeID, num);
		}
		if ((edgeFlags4 & EdgeFlags.Forward) != 0)
		{
			RemoveReversedConnection(edge.m_EndID, edgeID);
		}
		if ((edgeFlags4 & EdgeFlags.AllowMiddle) != 0)
		{
			RemoveReversedConnection(edge.m_MiddleID, edgeID);
		}
		if ((edgeFlags4 & EdgeFlags.Backward) != 0)
		{
			RemoveReversedConnection(edge.m_StartID, edgeID);
		}
		if ((edgeFlags5 & EdgeFlags.Forward) != 0)
		{
			reference.m_EndID = AddReversedConnection(endNode.StripCurvePos(), edgeID, num);
		}
		if ((edgeFlags5 & EdgeFlags.AllowMiddle) != 0)
		{
			reference.m_MiddleID = AddReversedConnection(middleNode.StripCurvePos(), edgeID, num);
		}
		if ((edgeFlags5 & EdgeFlags.Backward) != 0)
		{
			reference.m_StartID = AddReversedConnection(startNode.StripCurvePos(), edgeID, num);
		}
		if (num != num2)
		{
			EdgeFlags edgeFlags9 = (EdgeFlags)((uint)edgeFlags & (uint)(ushort)(~(int)edgeFlags3));
			int num3 = (int)edgeFlags & (int)(ushort)(~(int)edgeFlags5);
			if ((edgeFlags9 & EdgeFlags.Forward) != 0)
			{
				UpdateAccessRequirement(reference.m_StartID, edgeID, num);
			}
			if ((edgeFlags9 & EdgeFlags.AllowMiddle) != 0)
			{
				UpdateAccessRequirement(reference.m_MiddleID, edgeID, num);
			}
			if ((edgeFlags9 & EdgeFlags.Backward) != 0)
			{
				UpdateAccessRequirement(reference.m_EndID, edgeID, num);
			}
			if ((num3 & 1) != 0)
			{
				UpdateReversedAccessRequirement(reference.m_EndID, edgeID, num);
			}
			if ((num3 & 4) != 0)
			{
				UpdateReversedAccessRequirement(reference.m_MiddleID, edgeID, num);
			}
			if ((num3 & 2) != 0)
			{
				UpdateReversedAccessRequirement(reference.m_StartID, edgeID, num);
			}
		}
		if ((specification.m_Flags & (EdgeFlags.Forward | EdgeFlags.Backward)) == 0)
		{
			reference.m_StartID = new NodeID
			{
				m_Index = -1
			};
			reference.m_EndID = new NodeID
			{
				m_Index = -1
			};
		}
		if ((specification.m_Flags & EdgeFlags.AllowMiddle) == 0)
		{
			reference.m_MiddleID = new NodeID
			{
				m_Index = -1
			};
		}
		reference.m_StartCurvePos = startNode.GetCurvePos();
		reference.m_EndCurvePos = endNode.GetCurvePos();
		reference.m_Specification = specification;
		reference.m_Location = location;
	}
```

- `private UpdateReversedAccessRequirement(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex) : System.Void`  

```csharp
private void UpdateReversedAccessRequirement(NodeID nodeID, EdgeID edgeID, int accessIndex)
	{
		ref ushort reversedConnectionCount = ref GetReversedConnectionCount(nodeID);
		for (int i = 0; i < reversedConnectionCount; i++)
		{
			if (GetReversedConnection(nodeID, i) == edgeID.m_Index)
			{
				GetReversedAccessRequirement(nodeID, i) = accessIndex;
				break;
			}
		}
	}
```


