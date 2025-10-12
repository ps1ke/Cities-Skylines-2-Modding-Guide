# Game.Pathfind.NativePathfindData

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

**Attributes:** `NativeContainer`, `GenerateTestsForBurstCompatibility`  

## Fields

- `internal Game.Pathfind.UnsafePathfindData* m_PathfindData`  
- `internal Unity.Collections.Allocator m_AllocatorLabel`  

## Properties

- `public System.Boolean IsCreated { get }`  
- `public System.Int32 Size { get }`  

## Constructors

- `public NativePathfindData(Unity.Collections.Allocator allocator)`  
- `private NativePathfindData(Unity.Collections.Allocator allocator, System.Int32 disposeSentinelStackDepth)`  

## Methods

- `public AddEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID) : System.Void`  
- `public AddSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID) : System.Void`  
- `private CheckRead() : System.Void`  
- `private CheckWrite() : System.Void`  
- `public Clear() : System.Void`  
- `public CreateEdge(Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location) : Game.Pathfind.EdgeID`  
- `public DestroyEdge(Game.Pathfind.EdgeID edgeID) : System.Void`  
- `public Dispose() : System.Void`  
- `public GetEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  
- `public GetFlags(Game.Pathfind.EdgeID edgeID) : Game.Pathfind.EdgeFlags`  
- `public GetMemoryStats(System.UInt32& used, System.UInt32& allocated) : System.Void`  
- `public GetReadOnlyData() : Game.Pathfind.UnsafePathfindData`  
- `public GetSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  
- `public RemoveEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  
- `public RemoveSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  
- `public SetCosts(Game.Pathfind.EdgeID edgeID) : Game.Pathfind.PathfindCosts&`  
- `public SetDensity(Game.Pathfind.EdgeID edgeID) : System.Single&`  
- `public SetEdgeDirections(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode endNode, System.Boolean enableForward, System.Boolean enableBackward) : System.Void`  
- `public SetFlowOffset(Game.Pathfind.EdgeID edgeID) : System.Byte&`  
- `public UpdateEdge(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location) : System.Void`  

