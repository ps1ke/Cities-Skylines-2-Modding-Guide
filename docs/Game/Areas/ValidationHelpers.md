# Game.Areas.ValidationHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ValidationHelpers
{
    private static System.Boolean CheckShape(Colossal.Mathematics.Line3+Segment line1, Unity.Mathematics.float3 node2, Unity.Entities.Entity entity, System.Single minNodeDistance, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    private static System.Boolean CheckShape(Colossal.Mathematics.Line3+Segment line1, Unity.Mathematics.float3 node2, Unity.Entities.Entity entity, System.Single minNodeDistance, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index1, System.Int32 index2, System.Boolean isComplete, System.Boolean isCounterClockwise);
    private static System.Boolean CheckShape(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Line3+Segment line2, Unity.Entities.Entity entity, System.Single minNodeDistance, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index1, System.Int32 index2, System.Boolean isComplete, System.Boolean isCounterClockwise);
    private static Colossal.Mathematics.Line2+Segment GetEdgeLine(System.Single minNodeDistance, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index, System.Boolean isComplete, System.Boolean isCounterClockwise);
    private static Colossal.Mathematics.Quad2 GetEdgeQuad(System.Single minNodeDistance, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index, System.Boolean isComplete, System.Boolean isCounterClockwise);
    public static System.Void ValidateArea(System.Boolean editorMode, Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Areas.Area area, Game.Areas.Geometry geometry, Game.Areas.Storage storage, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    public static System.Void ValidateTriangle(System.Boolean editorMode, System.Boolean noErrors, System.Boolean isCounterClockwise, Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Areas.Triangle triangle, Game.Tools.ValidationSystem+EntityData data, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
}
```


## Methods

- `private static CheckShape(Colossal.Mathematics.Line3+Segment line1, Unity.Mathematics.float3 node2, Unity.Entities.Entity entity, System.Single minNodeDistance, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Boolean`  

```csharp
private static System.Boolean CheckShape(Colossal.Mathematics.Line3+Segment line1, Unity.Mathematics.float3 node2, Unity.Entities.Entity entity, System.Single minNodeDistance, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
```

- `private static CheckShape(Colossal.Mathematics.Line3+Segment line1, Unity.Mathematics.float3 node2, Unity.Entities.Entity entity, System.Single minNodeDistance, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index1, System.Int32 index2, System.Boolean isComplete, System.Boolean isCounterClockwise) : System.Boolean`  

```csharp
private static System.Boolean CheckShape(Colossal.Mathematics.Line3+Segment line1, Unity.Mathematics.float3 node2, Unity.Entities.Entity entity, System.Single minNodeDistance, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index1, System.Int32 index2, System.Boolean isComplete, System.Boolean isCounterClockwise);
```

- `private static CheckShape(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Line3+Segment line2, Unity.Entities.Entity entity, System.Single minNodeDistance, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index1, System.Int32 index2, System.Boolean isComplete, System.Boolean isCounterClockwise) : System.Boolean`  

```csharp
private static System.Boolean CheckShape(Colossal.Mathematics.Line3+Segment line1, Colossal.Mathematics.Line3+Segment line2, Unity.Entities.Entity entity, System.Single minNodeDistance, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index1, System.Int32 index2, System.Boolean isComplete, System.Boolean isCounterClockwise);
```

- `private static GetEdgeLine(System.Single minNodeDistance, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index, System.Boolean isComplete, System.Boolean isCounterClockwise) : Colossal.Mathematics.Line2+Segment`  

```csharp
private static Colossal.Mathematics.Line2+Segment GetEdgeLine(System.Single minNodeDistance, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index, System.Boolean isComplete, System.Boolean isCounterClockwise);
```

- `private static GetEdgeQuad(System.Single minNodeDistance, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index, System.Boolean isComplete, System.Boolean isCounterClockwise) : Colossal.Mathematics.Quad2`  

```csharp
private static Colossal.Mathematics.Quad2 GetEdgeQuad(System.Single minNodeDistance, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index, System.Boolean isComplete, System.Boolean isCounterClockwise);
```

- `public static ValidateArea(System.Boolean editorMode, Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Areas.Area area, Game.Areas.Geometry geometry, Game.Areas.Storage storage, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static System.Void ValidateArea(System.Boolean editorMode, Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Areas.Area area, Game.Areas.Geometry geometry, Game.Areas.Storage storage, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Prefabs.PrefabRef prefabRef, Game.Tools.ValidationSystem+EntityData data, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
```

- `public static ValidateTriangle(System.Boolean editorMode, System.Boolean noErrors, System.Boolean isCounterClockwise, Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Areas.Triangle triangle, Game.Tools.ValidationSystem+EntityData data, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static System.Void ValidateTriangle(System.Boolean editorMode, System.Boolean noErrors, System.Boolean isCounterClockwise, Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Areas.Triangle triangle, Game.Tools.ValidationSystem+EntityData data, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
```


## Nested types

- `Game.Areas.ValidationHelpers+OriginalAreaIterator`  
- `Game.Areas.ValidationHelpers+ObjectIterator`  
- `Game.Areas.ValidationHelpers+NetIterator`  
- `Game.Areas.ValidationHelpers+AreaIterator`  
- `Game.Areas.ValidationHelpers+BrushAreaIterator`  

