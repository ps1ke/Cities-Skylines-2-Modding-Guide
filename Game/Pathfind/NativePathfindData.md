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
private unsafe NativePathfindData(Allocator allocator, int disposeSentinelStackDepth)
	{
		m_PathfindData = (UnsafePathfindData*)UnsafeUtility.Malloc(UnsafeUtility.SizeOf<UnsafePathfindData>(), UnsafeUtility.AlignOf<UnsafePathfindData>(), allocator);
		*m_PathfindData = new UnsafePathfindData(allocator);
		m_AllocatorLabel = allocator;
	}
```

- `private NativePathfindData(Unity.Collections.Allocator allocator, System.Int32 disposeSentinelStackDepth)`  

```csharp
private unsafe NativePathfindData(Allocator allocator, int disposeSentinelStackDepth)
	{
		m_PathfindData = (UnsafePathfindData*)UnsafeUtility.Malloc(UnsafeUtility.SizeOf<UnsafePathfindData>(), UnsafeUtility.AlignOf<UnsafePathfindData>(), allocator);
		*m_PathfindData = new UnsafePathfindData(allocator);
		m_AllocatorLabel = allocator;
	}
```


## Methods

- `public AddEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID) : System.Void`  

```csharp
public unsafe void AddEdge(Entity owner, EdgeID edgeID)
	{
		m_PathfindData->AddEdge(owner, edgeID);
	}
```

- `public AddSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID edgeID) : System.Void`  

```csharp
public unsafe void AddSecondaryEdge(Entity owner, EdgeID edgeID)
	{
		m_PathfindData->AddSecondaryEdge(owner, edgeID);
	}
```

- `private CheckRead() : System.Void`  

```csharp
private void CheckRead()
	{
	}
```

- `private CheckWrite() : System.Void`  

```csharp
private void CheckWrite()
	{
	}
```

- `public Clear() : System.Void`  

```csharp
public unsafe void Clear()
	{
		m_PathfindData->Clear();
	}
```

- `public CreateEdge(Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location) : Game.Pathfind.EdgeID`  

```csharp
public unsafe EdgeID CreateEdge(PathNode startNode, PathNode middleNode, PathNode endNode, PathSpecification specification, LocationSpecification location)
	{
		return m_PathfindData->CreateEdge(startNode, middleNode, endNode, specification, location);
	}
```

- `public DestroyEdge(Game.Pathfind.EdgeID edgeID) : System.Void`  

```csharp
public unsafe void DestroyEdge(EdgeID edgeID)
	{
		m_PathfindData->DestroyEdge(edgeID);
	}
```

- `public Dispose() : System.Void`  

```csharp
public unsafe void Dispose()
	{
		m_PathfindData->Dispose();
		UnsafeUtility.Free(m_PathfindData, m_AllocatorLabel);
		m_PathfindData = null;
	}
```

- `public GetEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  

```csharp
public unsafe bool GetEdge(Entity owner, out EdgeID edgeID)
	{
		return m_PathfindData->GetEdge(owner, out edgeID);
	}
```

- `public GetFlags(Game.Pathfind.EdgeID edgeID) : Game.Pathfind.EdgeFlags`  

```csharp
public unsafe EdgeFlags GetFlags(EdgeID edgeID)
	{
		return m_PathfindData->GetEdge(edgeID).m_Specification.m_Flags;
	}
```

- `public GetMemoryStats(System.UInt32& used, System.UInt32& allocated) : System.Void`  

```csharp
public unsafe void GetMemoryStats(out uint used, out uint allocated)
	{
		m_PathfindData->GetMemoryStats(out used, out allocated);
	}
```

- `public GetReadOnlyData() : Game.Pathfind.UnsafePathfindData`  

```csharp
public unsafe UnsafePathfindData GetReadOnlyData()
	{
		return *m_PathfindData;
	}
```

- `public GetSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  

```csharp
public unsafe bool GetSecondaryEdge(Entity owner, out EdgeID edgeID)
	{
		return m_PathfindData->GetSecondaryEdge(owner, out edgeID);
	}
```

- `public RemoveEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  

```csharp
public unsafe bool RemoveEdge(Entity owner, out EdgeID edgeID)
	{
		return m_PathfindData->RemoveEdge(owner, out edgeID);
	}
```

- `public RemoveSecondaryEdge(Unity.Entities.Entity owner, Game.Pathfind.EdgeID& edgeID) : System.Boolean`  

```csharp
public unsafe bool RemoveSecondaryEdge(Entity owner, out EdgeID edgeID)
	{
		return m_PathfindData->RemoveSecondaryEdge(owner, out edgeID);
	}
```

- `public SetCosts(Game.Pathfind.EdgeID edgeID) : Game.Pathfind.PathfindCosts&`  

```csharp
public unsafe ref PathfindCosts SetCosts(EdgeID edgeID)
	{
		return ref m_PathfindData->GetEdge(edgeID).m_Specification.m_Costs;
	}
```

- `public SetDensity(Game.Pathfind.EdgeID edgeID) : System.Single&`  

```csharp
public unsafe ref float SetDensity(EdgeID edgeID)
	{
		return ref m_PathfindData->GetEdge(edgeID).m_Specification.m_Density;
	}
```

- `public SetEdgeDirections(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode endNode, System.Boolean enableForward, System.Boolean enableBackward) : System.Void`  

```csharp
public unsafe void SetEdgeDirections(EdgeID edgeID, PathNode startNode, PathNode endNode, bool enableForward, bool enableBackward)
	{
		m_PathfindData->SetEdgeDirections(edgeID, startNode, endNode, enableForward, enableBackward);
	}
```

- `public SetFlowOffset(Game.Pathfind.EdgeID edgeID) : System.Byte&`  

```csharp
public unsafe ref byte SetFlowOffset(EdgeID edgeID)
	{
		return ref m_PathfindData->GetEdge(edgeID).m_Specification.m_FlowOffset;
	}
```

- `public UpdateEdge(Game.Pathfind.EdgeID edgeID, Game.Pathfind.PathNode startNode, Game.Pathfind.PathNode middleNode, Game.Pathfind.PathNode endNode, Game.Pathfind.PathSpecification specification, Game.Pathfind.LocationSpecification location) : System.Void`  

```csharp
public unsafe void UpdateEdge(EdgeID edgeID, PathNode startNode, PathNode middleNode, PathNode endNode, PathSpecification specification, LocationSpecification location)
	{
		m_PathfindData->UpdateEdge(edgeID, startNode, middleNode, endNode, specification, location);
	}
```


