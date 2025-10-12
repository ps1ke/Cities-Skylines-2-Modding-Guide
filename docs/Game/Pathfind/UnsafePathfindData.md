# Game.Pathfind.UnsafePathfindData

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

**Attributes:** `GenerateTestsForBurstCompatibility`  

## Fields

- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.Edge> m_Edges`  
- `public Unity.Collections.LowLevel.Unsafe.UnsafeList<Game.Pathfind.EdgeID> m_FreeIDs`  
- `public Unity.Collections.LowLevel.Unsafe.UnsafeHashMap<Unity.Entities.Entity, Game.Pathfind.EdgeID> m_PathEdges`  
- `public Unity.Collections.LowLevel.Unsafe.UnsafeHashMap<Unity.Entities.Entity, Game.Pathfind.EdgeID> m_SecondaryEdges`  
- `public Unity.Collections.LowLevel.Unsafe.UnsafeHashMap<Game.Pathfind.PathNode, Game.Pathfind.NodeID> m_NodeIDs`  
- `public Unity.Collections.LowLevel.Unsafe.UnsafeHashMap<Game.Pathfind.NodeID, Game.Pathfind.PathNode> m_PathNodes`  
- `private Colossal.Collections.UnsafeHeapAllocator m_ConnectionAllocator`  
- `private System.Void* m_Connections`  
- `private System.Void* m_ReversedConnections`  
- `private System.Int32 m_NodeCount`  
- `private readonly Unity.Collections.Allocator m_AllocatorLabel`  
- `private static const System.Int32 NODE_META_SIZE`  

## Constructors

- `public UnsafePathfindData(Unity.Collections.Allocator allocator)`  

## Methods

- `private AddConnection(Game.Pathfind.PathNode pathNode, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex) : Game.Pathfind.NodeID`  
- `public AddEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID) : System.Void`  
- `private AddReversedConnection(Game.Pathfind.PathNode pathNode, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex) : Game.Pathfind.NodeID`  
- `public AddSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID) : System.Void`  
- `private AllocateConnections(System.Int32 connectionCapacity) : Colossal.Collections.UnsafeHeapBlock`  
- `public Clear() : System.Void`  
- `private CreateConnections(System.Int32 connectionCapacity) : Game.Pathfind.NodeID`  
- `public CreateEdge(Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location) : Game.Pathfind.EdgeID`  
- `private DestroyConnections(Game.Pathfind.NodeID nodeID) : System.Void`  
- `public DestroyEdge(Game.Pathfind.EdgeID edgeID) : System.Void`  
- `public Dispose() : System.Void`  
- `public GetAccessRequirement(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex) : System.Int32&`  
- `public GetConnection(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex) : System.Int32&`  
- `public GetConnectionCapacity(Game.Pathfind.NodeID nodeID) : System.UInt16&`  
- `public GetConnectionCount(Game.Pathfind.NodeID nodeID) : System.UInt16&`  
- `public GetEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  
- `public GetEdge(Game.Pathfind.EdgeID edgeID) : Game.Pathfind.Edge&`  
- `public GetMemoryStats(System.UInt32& used, System.UInt32& allocated) : System.Void`  
- `public GetNodeIDSize() : System.Int32`  
- `public GetReversedAccessRequirement(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex) : System.Int32&`  
- `public GetReversedConnection(Game.Pathfind.NodeID nodeID, System.Int32 connectionIndex) : System.Int32&`  
- `public GetReversedConnectionCapacity(Game.Pathfind.NodeID nodeID) : System.UInt16&`  
- `public GetReversedConnectionCount(Game.Pathfind.NodeID nodeID) : System.UInt16&`  
- `public GetSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  
- `private RemoveConnection(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID) : System.Void`  
- `public RemoveEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  
- `private RemoveReversedConnection(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID) : System.Void`  
- `public RemoveSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  
- `private ResizeConnections(Game.Pathfind.NodeID& nodeID, System.Int32 connectionCapacity) : System.Void`  
- `public SetEdgeDirections(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode endNode, System.Boolean enableForward, System.Boolean enableBackward) : System.Void`  
- `public SwapConnections() : System.Void`  
- `private UpdateAccessRequirement(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex) : System.Void`  
- `public UpdateEdge(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location) : System.Void`  
- `private UpdateReversedAccessRequirement(Game.Pathfind.NodeID nodeID, Game.Pathfind.EdgeID edgeID, System.Int32 accessIndex) : System.Void`  

