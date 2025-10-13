# Game.Pathfind.NativePathfindData

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

**Attributes:** `NativeContainer`, `GenerateTestsForBurstCompatibility`  

## Code

```csharp
public sealed struct NativePathfindData : System.IDisposable
{
    internal Game.Pathfind.UnsafePathfindData* m_PathfindData;
    internal Unity.Collections.Allocator m_AllocatorLabel;

    public System.Boolean IsCreated { get; }
    public System.Int32 Size { get; }

    public NativePathfindData(Unity.Collections.Allocator allocator);
    private NativePathfindData(Unity.Collections.Allocator allocator, System.Int32 disposeSentinelStackDepth);

    public System.Void AddEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID);
    public System.Void AddSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID);
    private System.Void CheckRead();
    private System.Void CheckWrite();
    public System.Void Clear();
    public Game.Pathfind.EdgeID CreateEdge(Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location);
    public System.Void DestroyEdge(Game.Pathfind.EdgeID edgeID);
    public System.Void Dispose();
    public System.Boolean GetEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID);
    public Game.Pathfind.EdgeFlags GetFlags(Game.Pathfind.EdgeID edgeID);
    public System.Void GetMemoryStats(System.UInt32& used, System.UInt32& allocated);
    public Game.Pathfind.UnsafePathfindData GetReadOnlyData();
    public System.Boolean GetSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID);
    public System.Boolean RemoveEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID);
    public System.Boolean RemoveSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID);
    public Game.Pathfind.PathfindCosts& SetCosts(Game.Pathfind.EdgeID edgeID);
    public System.Single& SetDensity(Game.Pathfind.EdgeID edgeID);
    public System.Void SetEdgeDirections(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode endNode, System.Boolean enableForward, System.Boolean enableBackward);
    public System.Byte& SetFlowOffset(Game.Pathfind.EdgeID edgeID);
    public System.Void UpdateEdge(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location);
}
```


## Fields

- `internal Game.Pathfind.UnsafePathfindData* m_PathfindData`  

```csharp
internal Game.Pathfind.UnsafePathfindData* m_PathfindData;
```

- `internal Unity.Collections.Allocator m_AllocatorLabel`  

```csharp
internal Unity.Collections.Allocator m_AllocatorLabel;
```


## Properties

- `public System.Boolean IsCreated { get }`  

```csharp
public System.Boolean IsCreated { get; }
```

- `public System.Int32 Size { get }`  

```csharp
public System.Int32 Size { get; }
```


## Constructors

- `public NativePathfindData(Unity.Collections.Allocator allocator)`  

```csharp
public NativePathfindData(Unity.Collections.Allocator allocator);
```

- `private NativePathfindData(Unity.Collections.Allocator allocator, System.Int32 disposeSentinelStackDepth)`  

```csharp
private NativePathfindData(Unity.Collections.Allocator allocator, System.Int32 disposeSentinelStackDepth);
```


## Methods

- `public AddEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID) : System.Void`  

```csharp
public System.Void AddEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID);
```

- `public AddSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID) : System.Void`  

```csharp
public System.Void AddSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID);
```

- `private CheckRead() : System.Void`  

```csharp
private System.Void CheckRead();
```

- `private CheckWrite() : System.Void`  

```csharp
private System.Void CheckWrite();
```

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `public CreateEdge(Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location) : Game.Pathfind.EdgeID`  

```csharp
public Game.Pathfind.EdgeID CreateEdge(Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location);
```

- `public DestroyEdge(Game.Pathfind.EdgeID edgeID) : System.Void`  

```csharp
public System.Void DestroyEdge(Game.Pathfind.EdgeID edgeID);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GetEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  

```csharp
public System.Boolean GetEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID);
```

- `public GetFlags(Game.Pathfind.EdgeID edgeID) : Game.Pathfind.EdgeFlags`  

```csharp
public Game.Pathfind.EdgeFlags GetFlags(Game.Pathfind.EdgeID edgeID);
```

- `public GetMemoryStats(System.UInt32& used, System.UInt32& allocated) : System.Void`  

```csharp
public System.Void GetMemoryStats(System.UInt32& used, System.UInt32& allocated);
```

- `public GetReadOnlyData() : Game.Pathfind.UnsafePathfindData`  

```csharp
public Game.Pathfind.UnsafePathfindData GetReadOnlyData();
```

- `public GetSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  

```csharp
public System.Boolean GetSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID);
```

- `public RemoveEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  

```csharp
public System.Boolean RemoveEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID);
```

- `public RemoveSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  

```csharp
public System.Boolean RemoveSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID);
```

- `public SetCosts(Game.Pathfind.EdgeID edgeID) : Game.Pathfind.PathfindCosts&`  

```csharp
public Game.Pathfind.PathfindCosts& SetCosts(Game.Pathfind.EdgeID edgeID);
```

- `public SetDensity(Game.Pathfind.EdgeID edgeID) : System.Single&`  

```csharp
public System.Single& SetDensity(Game.Pathfind.EdgeID edgeID);
```

- `public SetEdgeDirections(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode endNode, System.Boolean enableForward, System.Boolean enableBackward) : System.Void`  

```csharp
public System.Void SetEdgeDirections(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode endNode, System.Boolean enableForward, System.Boolean enableBackward);
```

- `public SetFlowOffset(Game.Pathfind.EdgeID edgeID) : System.Byte&`  

```csharp
public System.Byte& SetFlowOffset(Game.Pathfind.EdgeID edgeID);
```

- `public UpdateEdge(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location) : System.Void`  

```csharp
public System.Void UpdateEdge(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location);
```


