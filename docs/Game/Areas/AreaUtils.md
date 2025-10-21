# Game.Areas.AreaUtils

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class AreaUtils
{
    public static const System.Single NODE_DISTANCE_TOLERANCE;

    public static Game.Areas.Node AdjustPosition(Game.Areas.Node node, Game.Simulation.TerrainHeightData& terrainHeightData, Game.Simulation.WaterSurfaceData& waterSurfaceData);
    public static Game.Areas.Node AdjustPosition(Game.Areas.Node node, Game.Simulation.TerrainHeightData& terrainHeightData);
    public static System.Void ApplyModifier(System.Single& value, Unity.Entities.DynamicBuffer<Game.Areas.DistrictModifier> modifiers, Game.Areas.DistrictModifierType type);
    public static System.Single CalculateExtractorObjectArea(Game.Areas.Geometry geometry, Game.Areas.Extractor extractor, Game.Prefabs.ExtractorAreaData extractorAreaData);
    public static Unity.Mathematics.float4x4 CalculateLabelMatrix(Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 labelPosition, Unity.Mathematics.quaternion labelRotation);
    public static Unity.Mathematics.float3 CalculateLabelPosition(Game.Areas.Geometry geometry);
    public static Unity.Mathematics.quaternion CalculateLabelRotation(Unity.Mathematics.float3 cameraRight);
    public static System.Single CalculateLabelScale(Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 labelPosition);
    public static System.Int32 CalculateStorageCapacity(Game.Areas.Geometry geometry, Game.Prefabs.StorageAreaData prefabStorageData);
    public static System.Single CalculateStorageObjectArea(Game.Areas.Geometry geometry, Game.Areas.Storage storage, Game.Prefabs.StorageAreaData prefabStorageData);
    public static System.Boolean CheckOption(Game.Areas.District district, Game.Areas.DistrictOption option);
    public static System.Boolean CheckServiceDistrict(Unity.Entities.Entity district, Unity.Entities.Entity service, Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> serviceDistricts);
    public static System.Boolean CheckServiceDistrict(Unity.Entities.Entity district1, Unity.Entities.Entity district2, Unity.Entities.Entity service, Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> serviceDistricts);
    public static System.Boolean CheckServiceDistrict(Unity.Entities.Entity building, Unity.Entities.DynamicBuffer<Game.Areas.ServiceDistrict> serviceDistricts, Unity.Entities.ComponentLookup`1[[Game.Areas.CurrentDistrict, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentDistricts);
    public static System.Void FindAreaPath(Unity.Mathematics.Random& random, Unity.Collections.NativeList<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Net.SubLane> lanes, Unity.Entities.Entity startEntity, System.Single startCurvePos, Unity.Entities.Entity endEntity, System.Single endCurvePos, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData);
    public static Colossal.Mathematics.Bounds3 GetBounds(Game.Areas.Triangle triangle, Colossal.Mathematics.Triangle3 triangle3, Game.Prefabs.AreaGeometryData areaData);
    public static Game.Common.CollisionMask GetCollisionMask(Game.Prefabs.AreaGeometryData areaGeometryData);
    public static Unity.Mathematics.float3 GetElevations(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle);
    public static Unity.Mathematics.float3 GetExpandedNode(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index, System.Single expandAmount, System.Boolean isComplete, System.Boolean isCounterClockwise);
    public static Unity.Mathematics.float3 GetExpandedNode(Unity.Collections.NativeArray<Game.Prefabs.SubAreaNode> nodes, System.Int32 index, System.Single expandAmount, System.Boolean isComplete, System.Boolean isCounterClockwise);
    public static Unity.Mathematics.float3 GetExpandedNode<TNodeList>(TNodeList nodes, System.Int32 index, System.Int32 prevIndex, System.Int32 nextIndex, System.Single expandAmount, System.Boolean isCounterClockwise);
    public static System.Single GetMinNodeDistance(Game.Prefabs.AreaGeometryData areaData);
    public static System.Single GetMinNodeDistance(Game.Areas.AreaType areaType);
    public static Unity.Mathematics.float3 GetRandomPosition(Unity.Mathematics.Random& random, Game.Areas.Geometry geometry, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles);
    public static Unity.Mathematics.quaternion GetRandomRotation(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes);
    public static Colossal.Mathematics.Triangle2 GetTriangle2(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle);
    public static Colossal.Mathematics.Triangle2 GetTriangle2(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle, System.Single expandAmount, System.Boolean isCounterClockwise);
    public static Colossal.Mathematics.Triangle3 GetTriangle3(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle);
    public static Game.Areas.AreaTypeMask GetTypeMask(Game.Areas.AreaType type);
    public static System.Boolean HasOption(Game.Prefabs.DistrictOptionData optionData, Game.Areas.DistrictOption option);
    public static System.Boolean IntersectArea(Unity.Mathematics.float3 position, System.Single radius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles);
    public static System.Boolean IntersectEdges(Unity.Mathematics.float3 position, System.Single radius, System.Single extraRadius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes);
    public static System.Boolean IntersectObjects(Unity.Mathematics.float3 position, System.Single radius, System.Single extraRadius, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, System.Boolean canOverride);
    public static Unity.Mathematics.bool3 IsEdge(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle);
    public static System.Boolean SelectAreaPrefab(Unity.Entities.DynamicBuffer<Game.Prefabs.PlaceholderObjectElement> placeholderElements, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableObjectData> spawnableDatas, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> selectedSpawnables, Unity.Mathematics.Random& random, Unity.Entities.Entity& result, System.Int32& seed);
    public static System.Void SetCollisionFlags(Game.Prefabs.AreaGeometryData& areaGeometryData, System.Boolean ignoreMarkers);
    public static System.Boolean TryFitInside(Unity.Mathematics.float3& position, System.Single radius, System.Single extraRadius, Game.Areas.Area area, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, System.Boolean canOverride);
    public static System.Boolean TryGetRandomObjectLocation(Unity.Mathematics.Random& random, Game.Prefabs.ObjectGeometryData objectGeometryData, Game.Areas.Area area, Game.Areas.Geometry geometry, System.Single extraRadius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, Game.Objects.Transform& transform);
}
```


## Fields

- `public static const System.Single NODE_DISTANCE_TOLERANCE`  

```csharp
public static const System.Single NODE_DISTANCE_TOLERANCE;
```


## Methods

- `public static AdjustPosition(Game.Areas.Node node, Game.Simulation.TerrainHeightData& terrainHeightData, Game.Simulation.WaterSurfaceData& waterSurfaceData) : Game.Areas.Node`  

```csharp
public static Game.Areas.Node AdjustPosition(Game.Areas.Node node, Game.Simulation.TerrainHeightData& terrainHeightData, Game.Simulation.WaterSurfaceData& waterSurfaceData);
```

- `public static AdjustPosition(Game.Areas.Node node, Game.Simulation.TerrainHeightData& terrainHeightData) : Game.Areas.Node`  

```csharp
public static Game.Areas.Node AdjustPosition(Game.Areas.Node node, Game.Simulation.TerrainHeightData& terrainHeightData);
```

- `public static ApplyModifier(System.Single& value, Unity.Entities.DynamicBuffer<Game.Areas.DistrictModifier> modifiers, Game.Areas.DistrictModifierType type) : System.Void`  

```csharp
public static System.Void ApplyModifier(System.Single& value, Unity.Entities.DynamicBuffer<Game.Areas.DistrictModifier> modifiers, Game.Areas.DistrictModifierType type);
```

- `public static CalculateExtractorObjectArea(Game.Areas.Geometry geometry, Game.Areas.Extractor extractor, Game.Prefabs.ExtractorAreaData extractorAreaData) : System.Single`  

```csharp
public static System.Single CalculateExtractorObjectArea(Game.Areas.Geometry geometry, Game.Areas.Extractor extractor, Game.Prefabs.ExtractorAreaData extractorAreaData);
```

- `public static CalculateLabelMatrix(Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 labelPosition, Unity.Mathematics.quaternion labelRotation) : Unity.Mathematics.float4x4`  

```csharp
public static Unity.Mathematics.float4x4 CalculateLabelMatrix(Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 labelPosition, Unity.Mathematics.quaternion labelRotation);
```

- `public static CalculateLabelPosition(Game.Areas.Geometry geometry) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 CalculateLabelPosition(Game.Areas.Geometry geometry);
```

- `public static CalculateLabelRotation(Unity.Mathematics.float3 cameraRight) : Unity.Mathematics.quaternion`  

```csharp
public static Unity.Mathematics.quaternion CalculateLabelRotation(Unity.Mathematics.float3 cameraRight);
```

- `public static CalculateLabelScale(Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 labelPosition) : System.Single`  

```csharp
public static System.Single CalculateLabelScale(Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 labelPosition);
```

- `public static CalculateStorageCapacity(Game.Areas.Geometry geometry, Game.Prefabs.StorageAreaData prefabStorageData) : System.Int32`  

```csharp
public static System.Int32 CalculateStorageCapacity(Game.Areas.Geometry geometry, Game.Prefabs.StorageAreaData prefabStorageData);
```

- `public static CalculateStorageObjectArea(Game.Areas.Geometry geometry, Game.Areas.Storage storage, Game.Prefabs.StorageAreaData prefabStorageData) : System.Single`  

```csharp
public static System.Single CalculateStorageObjectArea(Game.Areas.Geometry geometry, Game.Areas.Storage storage, Game.Prefabs.StorageAreaData prefabStorageData);
```

- `public static CheckOption(Game.Areas.District district, Game.Areas.DistrictOption option) : System.Boolean`  

```csharp
public static System.Boolean CheckOption(Game.Areas.District district, Game.Areas.DistrictOption option);
```

- `public static CheckServiceDistrict(Unity.Entities.Entity district, Unity.Entities.Entity service, Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> serviceDistricts) : System.Boolean`  

```csharp
public static System.Boolean CheckServiceDistrict(Unity.Entities.Entity district, Unity.Entities.Entity service, Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> serviceDistricts);
```

- `public static CheckServiceDistrict(Unity.Entities.Entity district1, Unity.Entities.Entity district2, Unity.Entities.Entity service, Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> serviceDistricts) : System.Boolean`  

```csharp
public static System.Boolean CheckServiceDistrict(Unity.Entities.Entity district1, Unity.Entities.Entity district2, Unity.Entities.Entity service, Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> serviceDistricts);
```

- `public static CheckServiceDistrict(Unity.Entities.Entity building, Unity.Entities.DynamicBuffer<Game.Areas.ServiceDistrict> serviceDistricts, Unity.Entities.ComponentLookup`1[[Game.Areas.CurrentDistrict, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentDistricts) : System.Boolean`  

```csharp
public static System.Boolean CheckServiceDistrict(Unity.Entities.Entity building, Unity.Entities.DynamicBuffer<Game.Areas.ServiceDistrict> serviceDistricts, Unity.Entities.ComponentLookup`1[[Game.Areas.CurrentDistrict, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentDistricts);
```

- `public static FindAreaPath(Unity.Mathematics.Random& random, Unity.Collections.NativeList<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Net.SubLane> lanes, Unity.Entities.Entity startEntity, System.Single startCurvePos, Unity.Entities.Entity endEntity, System.Single endCurvePos, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData) : System.Void`  

```csharp
public static System.Void FindAreaPath(Unity.Mathematics.Random& random, Unity.Collections.NativeList<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Net.SubLane> lanes, Unity.Entities.Entity startEntity, System.Single startCurvePos, Unity.Entities.Entity endEntity, System.Single endCurvePos, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData);
```

- `public static GetBounds(Game.Areas.Triangle triangle, Colossal.Mathematics.Triangle3 triangle3, Game.Prefabs.AreaGeometryData areaData) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 GetBounds(Game.Areas.Triangle triangle, Colossal.Mathematics.Triangle3 triangle3, Game.Prefabs.AreaGeometryData areaData);
```

- `public static GetCollisionMask(Game.Prefabs.AreaGeometryData areaGeometryData) : Game.Common.CollisionMask`  

```csharp
public static Game.Common.CollisionMask GetCollisionMask(Game.Prefabs.AreaGeometryData areaGeometryData);
```

- `public static GetElevations(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetElevations(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle);
```

- `public static GetExpandedNode(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index, System.Single expandAmount, System.Boolean isComplete, System.Boolean isCounterClockwise) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetExpandedNode(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index, System.Single expandAmount, System.Boolean isComplete, System.Boolean isCounterClockwise);
```

- `public static GetExpandedNode(Unity.Collections.NativeArray<Game.Prefabs.SubAreaNode> nodes, System.Int32 index, System.Single expandAmount, System.Boolean isComplete, System.Boolean isCounterClockwise) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetExpandedNode(Unity.Collections.NativeArray<Game.Prefabs.SubAreaNode> nodes, System.Int32 index, System.Single expandAmount, System.Boolean isComplete, System.Boolean isCounterClockwise);
```

- `public static GetExpandedNode<TNodeList>(TNodeList nodes, System.Int32 index, System.Int32 prevIndex, System.Int32 nextIndex, System.Single expandAmount, System.Boolean isCounterClockwise) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetExpandedNode<TNodeList>(TNodeList nodes, System.Int32 index, System.Int32 prevIndex, System.Int32 nextIndex, System.Single expandAmount, System.Boolean isCounterClockwise);
```

- `public static GetMinNodeDistance(Game.Prefabs.AreaGeometryData areaData) : System.Single`  

```csharp
public static System.Single GetMinNodeDistance(Game.Prefabs.AreaGeometryData areaData);
```

- `public static GetMinNodeDistance(Game.Areas.AreaType areaType) : System.Single`  

```csharp
public static System.Single GetMinNodeDistance(Game.Areas.AreaType areaType);
```

- `public static GetRandomPosition(Unity.Mathematics.Random& random, Game.Areas.Geometry geometry, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetRandomPosition(Unity.Mathematics.Random& random, Game.Areas.Geometry geometry, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles);
```

- `public static GetRandomRotation(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes) : Unity.Mathematics.quaternion`  

```csharp
public static Unity.Mathematics.quaternion GetRandomRotation(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes);
```

- `public static GetTriangle2(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle) : Colossal.Mathematics.Triangle2`  

```csharp
public static Colossal.Mathematics.Triangle2 GetTriangle2(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle);
```

- `public static GetTriangle2(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle, System.Single expandAmount, System.Boolean isCounterClockwise) : Colossal.Mathematics.Triangle2`  

```csharp
public static Colossal.Mathematics.Triangle2 GetTriangle2(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle, System.Single expandAmount, System.Boolean isCounterClockwise);
```

- `public static GetTriangle3(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle) : Colossal.Mathematics.Triangle3`  

```csharp
public static Colossal.Mathematics.Triangle3 GetTriangle3(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle);
```

- `public static GetTypeMask(Game.Areas.AreaType type) : Game.Areas.AreaTypeMask`  

```csharp
public static Game.Areas.AreaTypeMask GetTypeMask(Game.Areas.AreaType type);
```

- `public static HasOption(Game.Prefabs.DistrictOptionData optionData, Game.Areas.DistrictOption option) : System.Boolean`  

```csharp
public static System.Boolean HasOption(Game.Prefabs.DistrictOptionData optionData, Game.Areas.DistrictOption option);
```

- `public static IntersectArea(Unity.Mathematics.float3 position, System.Single radius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles) : System.Boolean`  

```csharp
public static System.Boolean IntersectArea(Unity.Mathematics.float3 position, System.Single radius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles);
```

- `public static IntersectEdges(Unity.Mathematics.float3 position, System.Single radius, System.Single extraRadius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes) : System.Boolean`  

```csharp
public static System.Boolean IntersectEdges(Unity.Mathematics.float3 position, System.Single radius, System.Single extraRadius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes);
```

- `public static IntersectObjects(Unity.Mathematics.float3 position, System.Single radius, System.Single extraRadius, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, System.Boolean canOverride = False) : System.Boolean`  

```csharp
public static System.Boolean IntersectObjects(Unity.Mathematics.float3 position, System.Single radius, System.Single extraRadius, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, System.Boolean canOverride);
```

- `public static IsEdge(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle) : Unity.Mathematics.bool3`  

```csharp
public static Unity.Mathematics.bool3 IsEdge(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle);
```

- `public static SelectAreaPrefab(Unity.Entities.DynamicBuffer<Game.Prefabs.PlaceholderObjectElement> placeholderElements, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableObjectData> spawnableDatas, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> selectedSpawnables, Unity.Mathematics.Random& random, Unity.Entities.Entity& result, System.Int32& seed) : System.Boolean`  

```csharp
public static System.Boolean SelectAreaPrefab(Unity.Entities.DynamicBuffer<Game.Prefabs.PlaceholderObjectElement> placeholderElements, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableObjectData> spawnableDatas, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> selectedSpawnables, Unity.Mathematics.Random& random, Unity.Entities.Entity& result, System.Int32& seed);
```

- `public static SetCollisionFlags(Game.Prefabs.AreaGeometryData& areaGeometryData, System.Boolean ignoreMarkers) : System.Void`  

```csharp
public static System.Void SetCollisionFlags(Game.Prefabs.AreaGeometryData& areaGeometryData, System.Boolean ignoreMarkers);
```

- `public static TryFitInside(Unity.Mathematics.float3& position, System.Single radius, System.Single extraRadius, Game.Areas.Area area, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, System.Boolean canOverride = False) : System.Boolean`  

```csharp
public static System.Boolean TryFitInside(Unity.Mathematics.float3& position, System.Single radius, System.Single extraRadius, Game.Areas.Area area, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, System.Boolean canOverride);
```

- `public static TryGetRandomObjectLocation(Unity.Mathematics.Random& random, Game.Prefabs.ObjectGeometryData objectGeometryData, Game.Areas.Area area, Game.Areas.Geometry geometry, System.Single extraRadius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, Game.Objects.Transform& transform) : System.Boolean`  

```csharp
public static System.Boolean TryGetRandomObjectLocation(Unity.Mathematics.Random& random, Game.Prefabs.ObjectGeometryData objectGeometryData, Game.Areas.Area area, Game.Areas.Geometry geometry, System.Single extraRadius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, Game.Objects.Transform& transform);
```


## Nested types

- `Game.Areas.AreaUtils+ObjectItem`  
- `Game.Areas.AreaUtils+FixPathItem`  

