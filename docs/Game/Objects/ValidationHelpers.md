# Game.Objects.ValidationHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ValidationHelpers
{
    public static const System.Single COLLISION_TOLERANCE;

    private static System.Void CheckSurface(Unity.Entities.Entity entity, Game.Objects.Transform transform, Game.Common.CollisionMask collisionMask, Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Game.Prefabs.PlaceableObjectData placeableObjectData, Game.Tools.ValidationSystem+EntityData data, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    private static System.Boolean ExceedRange(Unity.Mathematics.float3 position, Unity.Mathematics.float3 forward, System.Single width, System.Single length, System.Single roundness, System.Boolean circular, Unity.Mathematics.float2 checkPosition);
    private static Unity.Entities.Entity GetOwner(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Tools.ValidationSystem+EntityData data, Game.Net.Edge& tempNodes, Game.Net.Edge& ownerNodes, Unity.Entities.Entity& attachedParent, Unity.Entities.Entity& assetStamp, Unity.Entities.Entity& edgeOwner, Unity.Entities.Entity& nodeOwner);
    public static System.Boolean Intersect(Colossal.Mathematics.Cylinder3 cylinder1, Colossal.Mathematics.Cylinder3 cylinder2, Unity.Mathematics.float3& pos);
    public static System.Void ValidateNetObject(Unity.Entities.Entity entity, Game.Objects.NetObject netObject, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Objects.Attached attached, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    public static System.Void ValidateObject(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Objects.Attached attached, System.Boolean isOutsideConnection, System.Boolean editorMode, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeList<Game.Tools.ValidationSystem+BoundsData> edgeList, Unity.Collections.NativeList<Game.Tools.ValidationSystem+BoundsData> objectList, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> instanceCounts, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    public static System.Void ValidateOutsideConnection(Unity.Entities.Entity entity, Game.Objects.Transform transform, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    public static System.Void ValidateSubPlacement(Unity.Entities.Entity entity, Game.Common.Owner owner, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    public static System.Void ValidateWaterSource(Unity.Entities.Entity entity, Game.Objects.Transform transform, Game.Simulation.WaterSourceData waterSourceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    public static System.Void ValidateWorldBounds(Unity.Entities.Entity entity, Game.Common.Owner owner, Colossal.Mathematics.Bounds3 bounds, Game.Tools.ValidationSystem+EntityData data, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
}
```


## Fields

- `public static const System.Single COLLISION_TOLERANCE`  

```csharp
public static const System.Single COLLISION_TOLERANCE;
```


## Methods

- `private static CheckSurface(Unity.Entities.Entity entity, Game.Objects.Transform transform, Game.Common.CollisionMask collisionMask, Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Game.Prefabs.PlaceableObjectData placeableObjectData, Game.Tools.ValidationSystem+EntityData data, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
private static System.Void CheckSurface(Unity.Entities.Entity entity, Game.Objects.Transform transform, Game.Common.CollisionMask collisionMask, Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Game.Prefabs.PlaceableObjectData placeableObjectData, Game.Tools.ValidationSystem+EntityData data, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
```

- `private static ExceedRange(Unity.Mathematics.float3 position, Unity.Mathematics.float3 forward, System.Single width, System.Single length, System.Single roundness, System.Boolean circular, Unity.Mathematics.float2 checkPosition) : System.Boolean`  

```csharp
private static System.Boolean ExceedRange(Unity.Mathematics.float3 position, Unity.Mathematics.float3 forward, System.Single width, System.Single length, System.Single roundness, System.Boolean circular, Unity.Mathematics.float2 checkPosition);
```

- `private static GetOwner(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Tools.ValidationSystem+EntityData data, Game.Net.Edge& tempNodes, Game.Net.Edge& ownerNodes, Unity.Entities.Entity& attachedParent, Unity.Entities.Entity& assetStamp, Unity.Entities.Entity& edgeOwner, Unity.Entities.Entity& nodeOwner) : Unity.Entities.Entity`  

```csharp
private static Unity.Entities.Entity GetOwner(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Tools.ValidationSystem+EntityData data, Game.Net.Edge& tempNodes, Game.Net.Edge& ownerNodes, Unity.Entities.Entity& attachedParent, Unity.Entities.Entity& assetStamp, Unity.Entities.Entity& edgeOwner, Unity.Entities.Entity& nodeOwner);
```

- `public static Intersect(Colossal.Mathematics.Cylinder3 cylinder1, Colossal.Mathematics.Cylinder3 cylinder2, Unity.Mathematics.float3& pos) : System.Boolean`  

```csharp
public static System.Boolean Intersect(Colossal.Mathematics.Cylinder3 cylinder1, Colossal.Mathematics.Cylinder3 cylinder2, Unity.Mathematics.float3& pos);
```

- `public static ValidateNetObject(Unity.Entities.Entity entity, Game.Objects.NetObject netObject, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Objects.Attached attached, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static System.Void ValidateNetObject(Unity.Entities.Entity entity, Game.Objects.NetObject netObject, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Objects.Attached attached, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
```

- `public static ValidateObject(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Objects.Attached attached, System.Boolean isOutsideConnection, System.Boolean editorMode, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeList<Game.Tools.ValidationSystem+BoundsData> edgeList, Unity.Collections.NativeList<Game.Tools.ValidationSystem+BoundsData> objectList, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> instanceCounts, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static System.Void ValidateObject(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Objects.Attached attached, System.Boolean isOutsideConnection, System.Boolean editorMode, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeList<Game.Tools.ValidationSystem+BoundsData> edgeList, Unity.Collections.NativeList<Game.Tools.ValidationSystem+BoundsData> objectList, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> objectSearchTree, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> netSearchTree, Colossal.Collections.NativeQuadTree<Game.Areas.AreaSearchItem, Game.Common.QuadTreeBoundsXZ> areaSearchTree, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> instanceCounts, Game.Simulation.WaterSurfaceData waterSurfaceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
```

- `public static ValidateOutsideConnection(Unity.Entities.Entity entity, Game.Objects.Transform transform, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static System.Void ValidateOutsideConnection(Unity.Entities.Entity entity, Game.Objects.Transform transform, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
```

- `public static ValidateSubPlacement(Unity.Entities.Entity entity, Game.Common.Owner owner, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static System.Void ValidateSubPlacement(Unity.Entities.Entity entity, Game.Common.Owner owner, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
```

- `public static ValidateWaterSource(Unity.Entities.Entity entity, Game.Objects.Transform transform, Game.Simulation.WaterSourceData waterSourceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static System.Void ValidateWaterSource(Unity.Entities.Entity entity, Game.Objects.Transform transform, Game.Simulation.WaterSourceData waterSourceData, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
```

- `public static ValidateWorldBounds(Unity.Entities.Entity entity, Game.Common.Owner owner, Colossal.Mathematics.Bounds3 bounds, Game.Tools.ValidationSystem+EntityData data, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static System.Void ValidateWorldBounds(Unity.Entities.Entity entity, Game.Common.Owner owner, Colossal.Mathematics.Bounds3 bounds, Game.Tools.ValidationSystem+EntityData data, Game.Simulation.TerrainHeightData terrainHeightData, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
```


## Nested types

- `Game.Objects.ValidationHelpers+ObjectIterator`  
- `Game.Objects.ValidationHelpers+NetIterator`  
- `Game.Objects.ValidationHelpers+AreaIterator`  

