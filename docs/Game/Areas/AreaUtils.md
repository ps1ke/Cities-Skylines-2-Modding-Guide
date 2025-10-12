# Game.Areas.AreaUtils

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `public static const System.Single NODE_DISTANCE_TOLERANCE`  

## Methods

- `public static AdjustPosition(Game.Areas.Node node, Game.Simulation.TerrainHeightData& terrainHeightData, Game.Simulation.WaterSurfaceData& waterSurfaceData) : Game.Areas.Node`  
- `public static AdjustPosition(Game.Areas.Node node, Game.Simulation.TerrainHeightData& terrainHeightData) : Game.Areas.Node`  
- `public static ApplyModifier(System.Single& value, Unity.Entities.DynamicBuffer<Game.Areas.DistrictModifier> modifiers, Game.Areas.DistrictModifierType type) : System.Void`  
- `public static CalculateExtractorObjectArea(Game.Areas.Geometry geometry, Game.Areas.Extractor extractor, Game.Prefabs.ExtractorAreaData extractorAreaData) : System.Single`  
- `public static CalculateLabelMatrix(Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 labelPosition, Unity.Mathematics.quaternion labelRotation) : Unity.Mathematics.float4x4`  
- `public static CalculateLabelPosition(Game.Areas.Geometry geometry) : Unity.Mathematics.float3`  
- `public static CalculateLabelRotation(Unity.Mathematics.float3 cameraRight) : Unity.Mathematics.quaternion`  
- `public static CalculateLabelScale(Unity.Mathematics.float3 cameraPosition, Unity.Mathematics.float3 labelPosition) : System.Single`  
- `public static CalculateStorageCapacity(Game.Areas.Geometry geometry, Game.Prefabs.StorageAreaData prefabStorageData) : System.Int32`  
- `public static CalculateStorageObjectArea(Game.Areas.Geometry geometry, Game.Areas.Storage storage, Game.Prefabs.StorageAreaData prefabStorageData) : System.Single`  
- `public static CheckOption(Game.Areas.District district, Game.Areas.DistrictOption option) : System.Boolean`  
- `public static CheckServiceDistrict(Unity.Entities.Entity district, Unity.Entities.Entity service, Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> serviceDistricts) : System.Boolean`  
- `public static CheckServiceDistrict(Unity.Entities.Entity district1, Unity.Entities.Entity district2, Unity.Entities.Entity service, Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> serviceDistricts) : System.Boolean`  
- `public static CheckServiceDistrict(Unity.Entities.Entity building, Unity.Entities.DynamicBuffer<Game.Areas.ServiceDistrict> serviceDistricts, Unity.Entities.ComponentLookup`1[[Game.Areas.CurrentDistrict, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentDistricts) : System.Boolean`  
- `public static FindAreaPath(Unity.Mathematics.Random& random, Unity.Collections.NativeList<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Net.SubLane> lanes, Unity.Entities.Entity startEntity, System.Single startCurvePos, Unity.Entities.Entity endEntity, System.Single endCurvePos, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData) : System.Void`  
- `public static GetBounds(Game.Areas.Triangle triangle, Colossal.Mathematics.Triangle3 triangle3, Game.Prefabs.AreaGeometryData areaData) : Colossal.Mathematics.Bounds3`  
- `public static GetCollisionMask(Game.Prefabs.AreaGeometryData areaGeometryData) : Game.Common.CollisionMask`  
- `public static GetElevations(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle) : Unity.Mathematics.float3`  
- `public static GetExpandedNode(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, System.Int32 index, System.Single expandAmount, System.Boolean isComplete, System.Boolean isCounterClockwise) : Unity.Mathematics.float3`  
- `public static GetExpandedNode(Unity.Collections.NativeArray<Game.Prefabs.SubAreaNode> nodes, System.Int32 index, System.Single expandAmount, System.Boolean isComplete, System.Boolean isCounterClockwise) : Unity.Mathematics.float3`  
- `public static GetExpandedNode<TNodeList>(TNodeList nodes, System.Int32 index, System.Int32 prevIndex, System.Int32 nextIndex, System.Single expandAmount, System.Boolean isCounterClockwise) : Unity.Mathematics.float3`  
- `public static GetMinNodeDistance(Game.Prefabs.AreaGeometryData areaData) : System.Single`  
- `public static GetMinNodeDistance(Game.Areas.AreaType areaType) : System.Single`  
- `public static GetRandomPosition(Unity.Mathematics.Random& random, Game.Areas.Geometry geometry, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles) : Unity.Mathematics.float3`  
- `public static GetRandomRotation(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes) : Unity.Mathematics.quaternion`  
- `public static GetTriangle2(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle) : Colossal.Mathematics.Triangle2`  
- `public static GetTriangle2(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle, System.Single expandAmount, System.Boolean isCounterClockwise) : Colossal.Mathematics.Triangle2`  
- `public static GetTriangle3(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle) : Colossal.Mathematics.Triangle3`  
- `public static GetTypeMask(Game.Areas.AreaType type) : Game.Areas.AreaTypeMask`  
- `public static HasOption(Game.Prefabs.DistrictOptionData optionData, Game.Areas.DistrictOption option) : System.Boolean`  
- `public static IntersectArea(Unity.Mathematics.float3 position, System.Single radius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles) : System.Boolean`  
- `public static IntersectEdges(Unity.Mathematics.float3 position, System.Single radius, System.Single extraRadius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes) : System.Boolean`  
- `public static IntersectObjects(Unity.Mathematics.float3 position, System.Single radius, System.Single extraRadius, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, System.Boolean canOverride = False) : System.Boolean`  
- `public static IsEdge(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Game.Areas.Triangle triangle) : Unity.Mathematics.bool3`  
- `public static SelectAreaPrefab(Unity.Entities.DynamicBuffer<Game.Prefabs.PlaceholderObjectElement> placeholderElements, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableObjectData> spawnableDatas, Unity.Collections.NativeParallelHashMap<Unity.Entities.Entity, System.Int32> selectedSpawnables, Unity.Mathematics.Random& random, Unity.Entities.Entity& result, System.Int32& seed) : System.Boolean`  
- `public static SetCollisionFlags(Game.Prefabs.AreaGeometryData& areaGeometryData, System.Boolean ignoreMarkers) : System.Void`  
- `public static TryFitInside(Unity.Mathematics.float3& position, System.Single radius, System.Single extraRadius, Game.Areas.Area area, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, System.Boolean canOverride = False) : System.Boolean`  
- `public static TryGetRandomObjectLocation(Unity.Mathematics.Random& random, Game.Prefabs.ObjectGeometryData objectGeometryData, Game.Areas.Area area, Game.Areas.Geometry geometry, System.Single extraRadius, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Entities.DynamicBuffer<Game.Areas.Triangle> triangles, Unity.Collections.NativeList<Game.Areas.AreaUtils+ObjectItem> objects, Game.Objects.Transform& transform) : System.Boolean`  

## Nested types

- `Game.Areas.AreaUtils+ObjectItem`  
- `Game.Areas.AreaUtils+FixPathItem`  

