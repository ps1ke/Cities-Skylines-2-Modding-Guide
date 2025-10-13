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
public UnsafePathfindData(Unity.Collections.Allocator allocator);
```


## Methods

- `private AddConnection(Game.Pathfind.PathNode pathNode, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex) : Game.Pathfind.NodeID`  

```csharp
private Game.Pathfind.NodeID AddConnection(Game.Pathfind.PathNode pathNode, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex);
```

- `public AddEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID) : System.Void`  

```csharp
public System.Void AddEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID);
```

- `private AddReversedConnection(Game.Pathfind.PathNode pathNode, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex) : Game.Pathfind.NodeID`  

```csharp
private Game.Pathfind.NodeID AddReversedConnection(Game.Pathfind.PathNode pathNode, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex);
```

- `public AddSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID) : System.Void`  

```csharp
public System.Void AddSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID);
```

- `private AllocateConnections(System.Int32 connectionCapacity) : Colossal.Collections.UnsafeHeapBlock`  

```csharp
private Colossal.Collections.UnsafeHeapBlock AllocateConnections(System.Int32 connectionCapacity);
```

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `private CreateConnections(System.Int32 connectionCapacity) : Game.Pathfind.NodeID`  

```csharp
private Game.Pathfind.NodeID CreateConnections(System.Int32 connectionCapacity);
```

- `public CreateEdge(Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location) : Game.Pathfind.EdgeID`  

```csharp
public Game.Pathfind.EdgeID CreateEdge(Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location);
```

- `private DestroyConnections(Game.Pathfind.NodeID nodeID) : System.Void`  

```csharp
private System.Void DestroyConnections(Game.Pathfind.NodeID nodeID);
```

- `public DestroyEdge(Game.Pathfind.EdgeID edgeID) : System.Void`  

```csharp
public System.Void DestroyEdge(Game.Pathfind.EdgeID edgeID);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetAccessRequirement(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex) : System.Int32&`  

```csharp
public System.Int32& GetAccessRequirement(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex);
```

- `public GetConnection(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex) : System.Int32&`  

```csharp
public System.Int32& GetConnection(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex);
```

- `public GetConnectionCapacity(Game.Pathfind.NodeID nodeID) : System.UInt16&`  

```csharp
public System.UInt16& GetConnectionCapacity(Game.Pathfind.NodeID nodeID);
```

- `public GetConnectionCount(Game.Pathfind.NodeID nodeID) : System.UInt16&`  

```csharp
public System.UInt16& GetConnectionCount(Game.Pathfind.NodeID nodeID);
```

- `public GetEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  

```csharp
public System.Boolean GetEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID);
```

- `public GetEdge(Game.Pathfind.EdgeID edgeID) : Game.Pathfind.Edge&`  

```csharp
public Game.Pathfind.Edge& GetEdge(Game.Pathfind.EdgeID edgeID);
```

- `public GetMemoryStats(System.UInt32& used, System.UInt32& allocated) : System.Void`  

```csharp
public System.Void GetMemoryStats(System.UInt32& used, System.UInt32& allocated);
```

- `public GetNodeIDSize() : System.Int32`  

```csharp
public System.Int32 GetNodeIDSize();
```

- `public GetReversedAccessRequirement(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex) : System.Int32&`  

```csharp
public System.Int32& GetReversedAccessRequirement(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex);
```

- `public GetReversedConnection(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex) : System.Int32&`  

```csharp
public System.Int32& GetReversedConnection(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex);
```

- `public GetReversedConnectionCapacity(Game.Pathfind.NodeID nodeID) : System.UInt16&`  

```csharp
public System.UInt16& GetReversedConnectionCapacity(Game.Pathfind.NodeID nodeID);
```

- `public GetReversedConnectionCount(Game.Pathfind.NodeID nodeID) : System.UInt16&`  

```csharp
public System.UInt16& GetReversedConnectionCount(Game.Pathfind.NodeID nodeID);
```

- `public GetSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  

```csharp
public System.Boolean GetSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID);
```

- `private RemoveConnection(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID) : System.Void`  

```csharp
private System.Void RemoveConnection(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID);
```

- `public RemoveEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  

```csharp
public System.Boolean RemoveEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID);
```

- `private RemoveReversedConnection(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID) : System.Void`  

```csharp
private System.Void RemoveReversedConnection(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID);
```

- `public RemoveSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  

```csharp
public System.Boolean RemoveSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID);
```

- `private ResizeConnections(Game.Pathfind.NodeID& nodeID, System.Int32 connectionCapacity) : System.Void`  

```csharp
private System.Void ResizeConnections(Game.Pathfind.NodeID& nodeID, System.Int32 connectionCapacity);
```

- `public SetEdgeDirections(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode endNode, System.Boolean enableForward, System.Boolean enableBackward) : System.Void`  

```csharp
public System.Void SetEdgeDirections(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode endNode, System.Boolean enableForward, System.Boolean enableBackward);
```

- `public SwapConnections() : System.Void`  

```csharp
public System.Void SwapConnections();
```

- `private UpdateAccessRequirement(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex) : System.Void`  

```csharp
private System.Void UpdateAccessRequirement(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex);
```

- `public UpdateEdge(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location) : System.Void`  

```csharp
public System.Void UpdateEdge(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location);
```

- `private UpdateReversedAccessRequirement(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex) : System.Void`  

```csharp
private System.Void UpdateReversedAccessRequirement(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex);
```


