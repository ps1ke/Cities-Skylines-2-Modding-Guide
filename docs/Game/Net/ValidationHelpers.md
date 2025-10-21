# Game.Net.ValidationHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ValidationHelpers
{
    private static System.Boolean CheckGeometryShape(Game.Net.EdgeGeometry geometry, Colossal.Mathematics.Bounds3& errorBounds);
    private static System.Boolean CheckGeometryShape(Game.Net.EdgeNodeGeometry geometry, Colossal.Mathematics.Bounds3& errorBounds);
    private static System.Boolean CheckSegmentShape(Game.Net.Segment segment, Colossal.Mathematics.Bounds3& errorBounds);
    private static System.Boolean CheckSurface(Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Game.Prefabs.PlaceableNetData placeableNetData, Game.Prefabs.NetCompositionData compositionData, Game.Net.Segment segment, Colossal.Mathematics.Bounds3& errorBounds);
    private static System.Boolean FindConnectedLane(Unity.Entities.Entity owner, Unity.Entities.Entity ignore, Game.Pathfind.PathNode node, Game.Tools.ValidationSystem+EntityData data);
    private static System.Boolean FindConnectedLane(Unity.Entities.Entity owner, Game.Pathfind.PathNode node, Game.Tools.ValidationSystem+EntityData data);
    private static Unity.Entities.Entity GetNetNode(Unity.Entities.Entity entity, Game.Tools.ValidationSystem+EntityData data);
    private static Unity.Entities.Entity GetOwner(Unity.Entities.Entity entity, Game.Tools.ValidationSystem+EntityData data, Unity.Entities.Entity& assetStamp, Unity.Entities.Entity& edge);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Colossal.Mathematics.Triangle2 triangle2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Colossal.Mathematics.Triangle3 triangle2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds1 heightRange2, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Colossal.Mathematics.Line2+Segment line2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Colossal.Mathematics.Triangle2 triangle2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Colossal.Mathematics.Triangle3 triangle2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds1 heightRange2, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Colossal.Mathematics.Line2+Segment line2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Colossal.Mathematics.Triangle2 triangle2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Colossal.Mathematics.Line2+Segment line2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Game.Net.Edge edge2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeGeometry edgeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Game.Net.Edge edge2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeGeometry edgeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Game.Net.Edge originalEdge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Entities.Entity node2, Unity.Entities.Entity originalNode2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Game.Net.Edge originalEdge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Entities.Entity node2, Unity.Entities.Entity originalNode2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity originalNode1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes2, Game.Net.EdgeNodeGeometry nodeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity originalNode1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes2, Game.Net.EdgeNodeGeometry nodeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Colossal.Mathematics.Triangle3 triangle2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds1 heightRange2, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Game.Net.Segment segment2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection);
    public static System.Boolean Intersect(Game.Net.Segment segment1, Game.Net.Segment segment2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection);
    private static System.Boolean IsIgnored(Unity.Entities.Entity edge, Unity.Entities.Entity node, Game.Tools.ValidationSystem+EntityData data, Game.Net.TrackTypes trackTypes, System.Boolean isSource, System.Boolean isTarget);
    private static System.Boolean IsInternal(Unity.Entities.Entity topLevelEntity, Unity.Entities.Entity node, Unity.Entities.DynamicBuffer<Game.Net.ConnectedEdge> connectedEdges, Game.Tools.ValidationSystem+EntityData data);
    public static System.Boolean QuadCylinderIntersect(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean QuadCylinderIntersectHelper(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds1 height2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean QuadCylinderIntersectHelper(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Line3 line2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    public static System.Boolean QuadIntersect(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Quad3 quad2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean QuadIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Quad3 quad2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean QuadIntersectHelper(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Quad3 quad2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    public static System.Boolean QuadTriangleIntersect(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Triangle3 triangle2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean QuadTriangleIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Triangle3 triangle2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean QuadTriangleIntersectHelper(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Triangle3 triangle2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    public static Colossal.Mathematics.Bounds3 SetHeightRange(Colossal.Mathematics.Bounds3 bounds, Colossal.Mathematics.Bounds1 heightRange);
    public static System.Boolean TriangleCylinderIntersect(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    private static System.Boolean TriangleCylinderIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Line3 line2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
    public static System.Void ValidateEdge(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Net.Fixed _fixed, Game.Net.Edge edge, Game.Net.EdgeGeometry edgeGeometry, Game.Net.StartNodeGeometry startNodeGeometry, Game.Net.EndNodeGeometry endNodeGeometry, Game.Net.Composition composition, Game.Prefabs.PrefabRef prefabRef, System.Boolean editorMode, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeList<Game.Tools.ValidationSystem+BoundsData> edgeList, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue, Unity.Collections.NativeList<Game.Net.ConnectedNode> tempNodes);
    public static System.Void ValidateLane(Unity.Entities.Entity entity, Game.Common.Owner owner, Game.Net.Lane lane, Game.Net.TrackLane trackLane, Game.Net.Curve curve, Game.Net.EdgeLane edgeLane, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
}
```


## Methods

- `private static CheckGeometryShape(Game.Net.EdgeGeometry geometry, Colossal.Mathematics.Bounds3& errorBounds) : System.Boolean`  

```csharp
private static System.Boolean CheckGeometryShape(Game.Net.EdgeGeometry geometry, Colossal.Mathematics.Bounds3& errorBounds);
```

- `private static CheckGeometryShape(Game.Net.EdgeNodeGeometry geometry, Colossal.Mathematics.Bounds3& errorBounds) : System.Boolean`  

```csharp
private static System.Boolean CheckGeometryShape(Game.Net.EdgeNodeGeometry geometry, Colossal.Mathematics.Bounds3& errorBounds);
```

- `private static CheckSegmentShape(Game.Net.Segment segment, Colossal.Mathematics.Bounds3& errorBounds) : System.Boolean`  

```csharp
private static System.Boolean CheckSegmentShape(Game.Net.Segment segment, Colossal.Mathematics.Bounds3& errorBounds);
```

- `private static CheckSurface(Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Game.Prefabs.PlaceableNetData placeableNetData, Game.Prefabs.NetCompositionData compositionData, Game.Net.Segment segment, Colossal.Mathematics.Bounds3& errorBounds) : System.Boolean`  

```csharp
private static System.Boolean CheckSurface(Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Game.Prefabs.PlaceableNetData placeableNetData, Game.Prefabs.NetCompositionData compositionData, Game.Net.Segment segment, Colossal.Mathematics.Bounds3& errorBounds);
```

- `private static FindConnectedLane(Unity.Entities.Entity owner, Unity.Entities.Entity ignore, Game.Pathfind.PathNode node, Game.Tools.ValidationSystem+EntityData data) : System.Boolean`  

```csharp
private static System.Boolean FindConnectedLane(Unity.Entities.Entity owner, Unity.Entities.Entity ignore, Game.Pathfind.PathNode node, Game.Tools.ValidationSystem+EntityData data);
```

- `private static FindConnectedLane(Unity.Entities.Entity owner, Game.Pathfind.PathNode node, Game.Tools.ValidationSystem+EntityData data) : System.Boolean`  

```csharp
private static System.Boolean FindConnectedLane(Unity.Entities.Entity owner, Game.Pathfind.PathNode node, Game.Tools.ValidationSystem+EntityData data);
```

- `private static GetNetNode(Unity.Entities.Entity entity, Game.Tools.ValidationSystem+EntityData data) : Unity.Entities.Entity`  

```csharp
private static Unity.Entities.Entity GetNetNode(Unity.Entities.Entity entity, Game.Tools.ValidationSystem+EntityData data);
```

- `private static GetOwner(Unity.Entities.Entity entity, Game.Tools.ValidationSystem+EntityData data, Unity.Entities.Entity& assetStamp, Unity.Entities.Entity& edge) : Unity.Entities.Entity`  

```csharp
private static Unity.Entities.Entity GetOwner(Unity.Entities.Entity entity, Game.Tools.ValidationSystem+EntityData data, Unity.Entities.Entity& assetStamp, Unity.Entities.Entity& edge);
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
```

- `public static Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Box3 box2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Quad2 quad2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Colossal.Mathematics.Triangle2 triangle2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Colossal.Mathematics.Triangle2 triangle2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Colossal.Mathematics.Triangle3 triangle2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds1 heightRange2, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Colossal.Mathematics.Triangle3 triangle2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds1 heightRange2, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Colossal.Mathematics.Line2+Segment line2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Colossal.Mathematics.Line2+Segment line2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Colossal.Mathematics.Triangle2 triangle2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Colossal.Mathematics.Triangle2 triangle2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Colossal.Mathematics.Triangle3 triangle2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds1 heightRange2, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Colossal.Mathematics.Triangle3 triangle2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds1 heightRange2, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Colossal.Mathematics.Line2+Segment line2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Colossal.Mathematics.Line2+Segment line2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Colossal.Mathematics.Triangle2 triangle2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Colossal.Mathematics.Triangle2 triangle2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Colossal.Mathematics.Line2+Segment line2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Colossal.Mathematics.Line2+Segment line2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity node2, Game.Net.EdgeNodeGeometry nodeGeometry1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
```

- `public static Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float3 offset1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Unity.Mathematics.float2 offset1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds2 bounds2, Game.Prefabs.NetCompositionData prefabCompositionData1, Unity.Entities.DynamicBuffer<Game.Prefabs.NetCompositionArea> areas1, Colossal.Mathematics.Bounds2& intersection);
```

- `public static Intersect(Game.Net.Edge edge1, Game.Net.Edge edge2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeGeometry edgeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Edge edge1, Game.Net.Edge edge2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeGeometry edgeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Game.Net.Edge edge1, Game.Net.Edge edge2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeGeometry edgeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Edge edge1, Game.Net.Edge edge2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeGeometry edgeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection);
```

- `public static Intersect(Game.Net.Edge edge1, Game.Net.Edge originalEdge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Edge edge1, Game.Net.Edge originalEdge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Entities.Entity node2, Unity.Entities.Entity originalNode2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Entities.Entity node2, Unity.Entities.Entity originalNode2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Game.Net.Edge edge1, Game.Net.Edge originalEdge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Edge edge1, Game.Net.Edge originalEdge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection);
```

- `public static Intersect(Game.Net.Edge edge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Entities.Entity node2, Unity.Entities.Entity originalNode2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Edge edge1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Entities.Entity node2, Unity.Entities.Entity originalNode2, Game.Net.EdgeGeometry edgeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection);
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity originalNode1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes2, Game.Net.EdgeNodeGeometry nodeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity originalNode1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes2, Game.Net.EdgeNodeGeometry nodeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity originalNode1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes2, Game.Net.EdgeNodeGeometry nodeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Unity.Entities.Entity node1, Unity.Entities.Entity originalNode1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes1, Unity.Collections.NativeArray<Game.Net.ConnectedNode> originalNodes1, Unity.Entities.Entity node2, Unity.Collections.NativeArray<Game.Net.ConnectedNode> nodes2, Game.Net.EdgeNodeGeometry nodeGeometry1, Game.Net.EdgeNodeGeometry nodeGeometry2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection);
```

- `public static Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Colossal.Mathematics.Triangle3 triangle2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds1 heightRange2, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Segment segment1, Unity.Mathematics.float2 segmentSide1, Colossal.Mathematics.Triangle3 triangle2, Game.Prefabs.NetCompositionData prefabCompositionData1, Colossal.Mathematics.Bounds1 heightRange2, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Game.Net.Segment segment1, Game.Net.Segment segment2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Segment segment1, Game.Net.Segment segment2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds3& intersection);
```

- `public static Intersect(Game.Net.Segment segment1, Game.Net.Segment segment2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Game.Net.Segment segment1, Game.Net.Segment segment2, Game.Prefabs.NetCompositionData prefabCompositionData1, Game.Prefabs.NetCompositionData prefabCompositionData2, Colossal.Mathematics.Bounds2& intersection);
```

- `private static IsIgnored(Unity.Entities.Entity edge, Unity.Entities.Entity node, Game.Tools.ValidationSystem+EntityData data, Game.Net.TrackTypes trackTypes, System.Boolean isSource, System.Boolean isTarget) : System.Boolean`  

```csharp
private static System.Boolean IsIgnored(Unity.Entities.Entity edge, Unity.Entities.Entity node, Game.Tools.ValidationSystem+EntityData data, Game.Net.TrackTypes trackTypes, System.Boolean isSource, System.Boolean isTarget);
```

- `private static IsInternal(Unity.Entities.Entity topLevelEntity, Unity.Entities.Entity node, Unity.Entities.DynamicBuffer<Game.Net.ConnectedEdge> connectedEdges, Game.Tools.ValidationSystem+EntityData data) : System.Boolean`  

```csharp
private static System.Boolean IsInternal(Unity.Entities.Entity topLevelEntity, Unity.Entities.Entity node, Unity.Entities.DynamicBuffer<Game.Net.ConnectedEdge> connectedEdges, Game.Tools.ValidationSystem+EntityData data);
```

- `public static QuadCylinderIntersect(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
public static System.Boolean QuadCylinderIntersect(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `private static QuadCylinderIntersectHelper(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds1 height2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static System.Boolean QuadCylinderIntersectHelper(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Circle2 circle2, Colossal.Mathematics.Bounds1 height2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `private static QuadCylinderIntersectHelper(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Line3 line2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static System.Boolean QuadCylinderIntersectHelper(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Line3 line2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `public static QuadIntersect(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Quad3 quad2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
public static System.Boolean QuadIntersect(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Quad3 quad2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `private static QuadIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Quad3 quad2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static System.Boolean QuadIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Quad3 quad2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `private static QuadIntersectHelper(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Quad3 quad2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static System.Boolean QuadIntersectHelper(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Quad3 quad2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `public static QuadTriangleIntersect(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Triangle3 triangle2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
public static System.Boolean QuadTriangleIntersect(Colossal.Mathematics.Quad3 quad1, Colossal.Mathematics.Triangle3 triangle2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `private static QuadTriangleIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Triangle3 triangle2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static System.Boolean QuadTriangleIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Triangle3 triangle2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `private static QuadTriangleIntersectHelper(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Triangle3 triangle2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static System.Boolean QuadTriangleIntersectHelper(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Triangle3 triangle2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `public static SetHeightRange(Colossal.Mathematics.Bounds3 bounds, Colossal.Mathematics.Bounds1 heightRange) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 SetHeightRange(Colossal.Mathematics.Bounds3 bounds, Colossal.Mathematics.Bounds1 heightRange);
```

- `public static TriangleCylinderIntersect(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
public static System.Boolean TriangleCylinderIntersect(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Cylinder3 cylinder2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `private static TriangleCylinderIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Line3 line2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2) : System.Boolean`  

```csharp
private static System.Boolean TriangleCylinderIntersectHelper(Colossal.Mathematics.Triangle3 triangle1, Colossal.Mathematics.Line3 line2, Colossal.Mathematics.Bounds3& intersection1, Colossal.Mathematics.Bounds3& intersection2);
```

- `public static ValidateEdge(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Net.Fixed _fixed, Game.Net.Edge edge, Game.Net.EdgeGeometry edgeGeometry, Game.Net.StartNodeGeometry startNodeGeometry, Game.Net.EndNodeGeometry endNodeGeometry, Game.Net.Composition composition, Game.Prefabs.PrefabRef prefabRef, System.Boolean editorMode, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeList<Game.Tools.ValidationSystem+BoundsData> edgeList, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue, Unity.Collections.NativeList<Game.Net.ConnectedNode> tempNodes) : System.Void`  

```csharp
public static System.Void ValidateEdge(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Net.Fixed _fixed, Game.Net.Edge edge, Game.Net.EdgeGeometry edgeGeometry, Game.Net.StartNodeGeometry startNodeGeometry, Game.Net.EndNodeGeometry endNodeGeometry, Game.Net.Composition composition, Game.Prefabs.PrefabRef prefabRef, System.Boolean editorMode, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeList<Game.Tools.ValidationSystem+BoundsData> edgeList, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue, Unity.Collections.NativeList<Game.Net.ConnectedNode> tempNodes);
```

- `public static ValidateLane(Unity.Entities.Entity entity, Game.Common.Owner owner, Game.Net.Lane lane, Game.Net.TrackLane trackLane, Game.Net.Curve curve, Game.Net.EdgeLane edgeLane, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static System.Void ValidateLane(Unity.Entities.Entity entity, Game.Common.Owner owner, Game.Net.Lane lane, Game.Net.TrackLane trackLane, Game.Net.Curve curve, Game.Net.EdgeLane edgeLane, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
```


## Nested types

- `Game.Net.ValidationHelpers+NetIterator`  
- `Game.Net.ValidationHelpers+ObjectIterator`  
- `Game.Net.ValidationHelpers+AreaIterator`  

