# Game.Objects.ObjectUtils

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `public static const System.Single MAX_SPAWN_LOCATION_CONNECTION_DISTANCE`  
- `public static const System.Single MIN_TREE_WOOD_RESOURCE`  
- `public static const System.Single MAX_TREE_AGE`  
- `public static const System.Single TREE_AGE_PHASE_CHILD`  
- `public static const System.Single TREE_AGE_PHASE_TEEN`  
- `public static const System.Single TREE_AGE_PHASE_ADULT`  
- `public static const System.Single TREE_AGE_PHASE_ELDERLY`  
- `public static const System.Single TREE_AGE_PHASE_DEAD`  
- `public static const System.Single TREE_WOOD_GROWTH_CHILD`  
- `public static const System.Single TREE_WOOD_GROWTH_TEEN`  
- `public static const System.Single TREE_WOOD_GROWTH_ADULT`  

## Methods

- `public static AdjustPosition(Game.Objects.Transform transform, Game.Objects.Elevation& elevation, Unity.Entities.Entity prefab, System.Boolean& angledSample, Game.Simulation.TerrainHeightData& terrainHeightData, Game.Simulation.WaterSurfaceData& waterSurfaceData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PlaceableObjectData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& placeableObjectDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectGeometryDatas) : Game.Objects.Transform`  
- `private static ApplyRootMotion(Game.Objects.Transform& transform, Game.Objects.TransformFrame& newFrameData, Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationMotion> motions, Game.Rendering.BlendWeights weights, Unity.Mathematics.int2 motionRange, Unity.Mathematics.float3 deltaRange) : System.Void`  
- `private static ApplyRootMotion(Game.Objects.Transform& transform, Unity.Mathematics.float3& targetPosition, Unity.Mathematics.float3& targetDirection, Unity.Mathematics.float3 rootOffset, Unity.Mathematics.quaternion rootRotation) : System.Void`  
- `public static CalculateBaseCorners(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Colossal.Mathematics.Bounds3 bounds) : Colossal.Mathematics.Quad3`  
- `public static CalculateBaseCorners(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Unity.Mathematics.float2 size) : Colossal.Mathematics.Quad3`  
- `public static CalculateBounds(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Game.Prefabs.ObjectGeometryData geometryData) : Colossal.Mathematics.Bounds3`  
- `public static CalculateBounds(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Game.Objects.Stack stack, Game.Prefabs.ObjectGeometryData geometryData, Game.Prefabs.StackData stackData) : Colossal.Mathematics.Bounds3`  
- `public static CalculateBounds(Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation, Colossal.Mathematics.Bounds3 bounds) : Colossal.Mathematics.Bounds3`  
- `public static CalculateBounds(Colossal.Mathematics.Line3+Segment positionRange, Unity.Mathematics.quaternion rotation, Colossal.Mathematics.Bounds3 bounds) : Colossal.Mathematics.Bounds3`  
- `public static CalculateGrowthRate(Game.Objects.Tree tree, Game.Objects.Plant plant, Game.Prefabs.TreeData treeData) : System.Single`  
- `public static CalculateMomentOfInertia(Unity.Mathematics.quaternion rotation, Unity.Mathematics.float3 size) : Unity.Mathematics.float3`  
- `public static CalculatePointVelocity(Unity.Mathematics.float3 offset, Game.Objects.Moving moving) : Unity.Mathematics.float3`  
- `public static CalculateWoodAmount(Game.Objects.Tree tree, Game.Objects.Plant plant, Game.Objects.Damaged damaged, Game.Prefabs.TreeData treeData) : System.Single`  
- `public static GetActivityStartPosition(Unity.Entities.Entity prefab, Unity.Entities.DynamicBuffer<Game.Rendering.MeshGroup> meshGroups, Game.Objects.Transform activityTransform, Game.Objects.TransformState state, Game.Prefabs.ActivityType activityType, Game.Rendering.AnimatedPropID propID, Game.Prefabs.ActivityCondition conditions, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMeshGroup, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshGroupBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.CharacterElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& characterElementBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationClip, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationClipBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationMotionBuffers, Game.Objects.ObjectUtils+ActivityStartPositionCache& cache) : Game.Objects.Transform`  
- `public static GetBounds(Game.Prefabs.ObjectGeometryData geometryData) : Colossal.Mathematics.Bounds3`  
- `public static GetBounds(Game.Objects.Stack stack, Game.Prefabs.ObjectGeometryData geometryData, Game.Prefabs.StackData stackData) : Colossal.Mathematics.Bounds3`  
- `public static GetCollisionMask(Game.Prefabs.ObjectGeometryData geometryData, Game.Objects.Elevation elevation, System.Boolean ignoreMarkers) : Game.Common.CollisionMask`  
- `public static GetCollisionMask(Game.Prefabs.ObjectGeometryData geometryData, System.Boolean ignoreMarkers) : Game.Common.CollisionMask`  
- `public static GetContructionCost(System.Int32 constructionCost, Game.Objects.Tree tree, Game.Prefabs.EconomyParameterData& economyParameterData) : System.Int32`  
- `private static GetParentActivity(System.Byte activity) : System.Byte`  
- `public static GetRebuildCost(System.Int32 constructionCost) : System.Int32`  
- `public static GetRebuildCost(System.Int32 constructionCost, Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData) : System.Int32`  
- `public static GetRefundAmount(Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData) : System.Int32`  
- `public static GetRelocationCost(System.Int32 constructionCost, Game.Prefabs.EconomyParameterData economyParameterData) : System.Int32`  
- `public static GetRelocationCost(System.Int32 constructionCost, Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData) : System.Int32`  
- `public static GetRemainingConstructionFrames(Game.Objects.UnderConstruction underConstruction) : System.UInt32`  
- `public static GetRootMotion(Unity.Entities.DynamicBuffer<Game.Prefabs.AnimationMotion> motions, Unity.Mathematics.int2 range, Game.Rendering.BlendWeights weights, System.Single t, Unity.Mathematics.float3& rootOffset, Unity.Mathematics.float3& rootVelocity, Unity.Mathematics.quaternion& rootRotation) : System.Void`  
- `private static GetRootMotion(Game.Prefabs.AnimationMotion motion, System.Single t, Unity.Mathematics.float3& rootOffset, Unity.Mathematics.float3& rootVelocity, Unity.Mathematics.quaternion& rootRotation) : System.Void`  
- `public static GetSize(Colossal.Mathematics.Bounds3 bounds) : Unity.Mathematics.float3`  
- `public static GetStandingLegCount(Game.Prefabs.ObjectGeometryData objectGeometryData, System.Int32& legCount) : System.Boolean`  
- `public static GetStandingLegOffset(Game.Prefabs.ObjectGeometryData objectGeometryData, System.Int32 legIndex) : Unity.Mathematics.float3`  
- `public static GetStandingLegPosition(Game.Prefabs.ObjectGeometryData objectGeometryData, Game.Objects.Transform transform, System.Int32 legIndex) : Unity.Mathematics.float3`  
- `private static GetStateDuration(Unity.Entities.Entity prefab, Game.Objects.TransformState state, System.Byte activity, Game.Rendering.AnimatedPropID propID, Game.Prefabs.ActivityCondition conditions, Unity.Entities.DynamicBuffer<Game.Rendering.MeshGroup> meshGroups, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMeshGroup, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshGroupBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.CharacterElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& characterElementBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationClip, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationClipBuffers, Game.Prefabs.CharacterElement& characterElement, Game.Prefabs.AnimationClip& animationClip, System.Boolean& crossFade) : System.Single`  
- `public static GetSubParentMesh(Game.Objects.ElevationFlags elevationFlags) : System.Int32`  
- `public static GetTerrainSmoothingWidth(Game.Prefabs.ObjectGeometryData objectGeometryData) : System.Single`  
- `public static GetTerrainSmoothingWidth(Unity.Mathematics.float2 size) : System.Single`  
- `public static GetTotalDamage(Game.Objects.Damaged damaged) : System.Single`  
- `public static GetTripDelayFrames(Game.Objects.UnderConstruction underConstruction, Game.Pathfind.PathInformation pathInformation) : System.UInt32`  
- `public static GetUpgradeCost(System.Int32 constructionCost, System.Int32 originalCost) : System.Int32`  
- `public static GetUpgradeCost(System.Int32 constructionCost, System.Int32 originalCost, Game.Tools.Recent recent, System.UInt32 simulationFrame, Game.Prefabs.EconomyParameterData economyParameterData) : System.Int32`  
- `public static InitializeTreeState(System.Single age) : Game.Objects.Tree`  
- `public static InverseTransform(Game.Objects.Transform transform) : Game.Objects.Transform`  
- `public static LocalToWorld(Game.Objects.Transform transform, Unity.Mathematics.float3 position) : Unity.Mathematics.float3`  
- `public static LocalToWorld(Unity.Mathematics.float3 transformPosition, Unity.Mathematics.quaternion transformRotation, Unity.Mathematics.float3 position) : Unity.Mathematics.float3`  
- `public static LocalToWorld(Unity.Mathematics.float3 transformPosition, Unity.Mathematics.quaternion transformRotation, Colossal.Mathematics.Bezier4x3 curve) : Colossal.Mathematics.Bezier4x3`  
- `public static LocalToWorld(Game.Objects.Transform transform, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation) : Game.Objects.Transform`  
- `public static LocalToWorld(Game.Rendering.InterpolatedTransform transform, Unity.Mathematics.float3 position, Unity.Mathematics.quaternion rotation) : Game.Rendering.InterpolatedTransform`  
- `public static LocalToWorld(Game.Objects.Transform parentTransform, Game.Objects.Transform transform) : Game.Objects.Transform`  
- `public static UpdateAnimation(Unity.Entities.Entity prefab, System.Single timeStep, Unity.Entities.DynamicBuffer<Game.Rendering.MeshGroup> meshGroups, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMeshGroup, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshGroupBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.CharacterElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& characterElementBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationClip, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationClipBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationMotionBuffers, Game.Rendering.AnimatedPropID oldPropID, Game.Rendering.AnimatedPropID newPropID, Game.Prefabs.ActivityCondition conditions, System.Single& maxSpeed, System.Byte& activity, Unity.Mathematics.float3& targetPosition, Unity.Mathematics.float3& targetDirection, Game.Objects.Transform& transform, Game.Objects.TransformFrame& oldFrameData, Game.Objects.TransformFrame& newFrameData) : System.Void`  
- `public static UpdateResourcesDamage(Unity.Entities.Entity entity, System.Single totalDamage, Unity.Entities.BufferLookup`1[[Game.Buildings.Renter, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& renterData, Unity.Entities.BufferLookup`1[[Game.Economy.Resources, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& resourcesData) : System.Void`  
- `public static WorldToLocal(Game.Objects.Transform inverseParentTransform, Game.Objects.Transform transform) : Game.Objects.Transform`  
- `public static WorldToLocal(Game.Objects.Transform inverseParentTransform, Unity.Mathematics.float3 position) : Unity.Mathematics.float3`  

## Nested types

- `Game.Objects.ObjectUtils+ActivityStartPositionCache`  

