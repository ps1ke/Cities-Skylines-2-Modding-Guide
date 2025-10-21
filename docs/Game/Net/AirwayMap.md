# Game.Net.AirwayHelpers+AirwayMap

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct AirwayMap : System.IDisposable
{
    private Unity.Mathematics.int2 m_GridSize;
    private System.Single m_CellSize;
    private System.Single m_PathHeight;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_Entities;

    public Unity.Collections.NativeArray<Unity.Entities.Entity> entities { get; }

    public AirwayMap(Unity.Mathematics.int2 gridSize, System.Single cellSize, System.Single pathHeight, Unity.Collections.Allocator allocator);

    public System.Void Deserialize<TReader>(TReader reader);
    public System.Void Dispose();
    public System.Void FindClosestLane(Unity.Mathematics.float3 position, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.Entity& lane, System.Single& curvePos, System.Single& distance);
    private System.Void FindClosestLaneImpl(Unity.Mathematics.float3 position, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.Entity& bestLane, System.Single& bestCurvePos, System.Single& bestDistance, System.Int32 entityIndex);
    public Unity.Mathematics.int2 GetCellIndex(System.Int32 entityIndex, Game.Net.AirwayHelpers+LaneDirection& direction);
    public Unity.Mathematics.int2 GetCellIndex(Unity.Mathematics.float3 position);
    public System.Int32 GetEntityIndex(Unity.Mathematics.int2 nodeIndex, Game.Net.AirwayHelpers+LaneDirection direction);
    public Unity.Mathematics.float3 GetNodePosition(Unity.Mathematics.int2 nodeIndex);
    public Game.Pathfind.PathNode GetPathNode(Unity.Mathematics.int2 index);
    public System.Void Serialize<TWriter>(TWriter writer);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Unity.Mathematics.int2 m_GridSize`  

```csharp
private Unity.Mathematics.int2 m_GridSize;
```

- `private System.Single m_CellSize`  

```csharp
private System.Single m_CellSize;
```

- `private System.Single m_PathHeight`  

```csharp
private System.Single m_PathHeight;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_Entities`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_Entities;
```


## Properties

- `public Unity.Collections.NativeArray<Unity.Entities.Entity> entities { get }`  

```csharp
public Unity.Collections.NativeArray<Unity.Entities.Entity> entities { get; }
```


## Constructors

- `public AirwayMap(Unity.Mathematics.int2 gridSize, System.Single cellSize, System.Single pathHeight, Unity.Collections.Allocator allocator)`  

```csharp
public AirwayMap(Unity.Mathematics.int2 gridSize, System.Single cellSize, System.Single pathHeight, Unity.Collections.Allocator allocator);
```


## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public FindClosestLane(Unity.Mathematics.float3 position, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.Entity& lane, System.Single& curvePos, System.Single& distance) : System.Void`  

```csharp
public System.Void FindClosestLane(Unity.Mathematics.float3 position, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.Entity& lane, System.Single& curvePos, System.Single& distance);
```

- `private FindClosestLaneImpl(Unity.Mathematics.float3 position, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.Entity& bestLane, System.Single& bestCurvePos, System.Single& bestDistance, System.Int32 entityIndex) : System.Void`  

```csharp
private System.Void FindClosestLaneImpl(Unity.Mathematics.float3 position, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.Entity& bestLane, System.Single& bestCurvePos, System.Single& bestDistance, System.Int32 entityIndex);
```

- `public GetCellIndex(System.Int32 entityIndex, Game.Net.AirwayHelpers+LaneDirection& direction) : Unity.Mathematics.int2`  

```csharp
public Unity.Mathematics.int2 GetCellIndex(System.Int32 entityIndex, Game.Net.AirwayHelpers+LaneDirection& direction);
```

- `public GetCellIndex(Unity.Mathematics.float3 position) : Unity.Mathematics.int2`  

```csharp
public Unity.Mathematics.int2 GetCellIndex(Unity.Mathematics.float3 position);
```

- `public GetEntityIndex(Unity.Mathematics.int2 nodeIndex, Game.Net.AirwayHelpers+LaneDirection direction) : System.Int32`  

```csharp
public System.Int32 GetEntityIndex(Unity.Mathematics.int2 nodeIndex, Game.Net.AirwayHelpers+LaneDirection direction);
```

- `public GetNodePosition(Unity.Mathematics.int2 nodeIndex) : Unity.Mathematics.float3`  

```csharp
public Unity.Mathematics.float3 GetNodePosition(Unity.Mathematics.int2 nodeIndex);
```

- `public GetPathNode(Unity.Mathematics.int2 index) : Game.Pathfind.PathNode`  

```csharp
public Game.Pathfind.PathNode GetPathNode(Unity.Mathematics.int2 index);
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```


