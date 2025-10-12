# Game.Net.AirwayHelpers+AirwayMap

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Fields

- `private Unity.Mathematics.int2 m_GridSize`  
- `private System.Single m_CellSize`  
- `private System.Single m_PathHeight`  
- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_Entities`  

## Properties

- `public Unity.Collections.NativeArray<Unity.Entities.Entity> entities { get }`  

## Constructors

- `public AirwayMap(Unity.Mathematics.int2 gridSize, System.Single cellSize, System.Single pathHeight, Unity.Collections.Allocator allocator)`  

## Methods

- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `public Dispose() : System.Void`  
- `public FindClosestLane(Unity.Mathematics.float3 position, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.Entity& lane, System.Single& curvePos, System.Single& distance) : System.Void`  
- `private FindClosestLaneImpl(Unity.Mathematics.float3 position, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.Entity& bestLane, System.Single& bestCurvePos, System.Single& bestDistance, System.Int32 entityIndex) : System.Void`  
- `public GetCellIndex(System.Int32 entityIndex, Game.Net.AirwayHelpers+LaneDirection& direction) : Unity.Mathematics.int2`  
- `public GetCellIndex(Unity.Mathematics.float3 position) : Unity.Mathematics.int2`  
- `public GetEntityIndex(Unity.Mathematics.int2 nodeIndex, Game.Net.AirwayHelpers+LaneDirection direction) : System.Int32`  
- `public GetNodePosition(Unity.Mathematics.int2 nodeIndex) : Unity.Mathematics.float3`  
- `public GetPathNode(Unity.Mathematics.int2 index) : Game.Pathfind.PathNode`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

