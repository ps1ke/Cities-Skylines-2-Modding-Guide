# Game.Rendering.CameraCollisionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Tools.ToolSystem m_ToolSystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Unity.Mathematics.float3 m_PreviousPosition`  
- `private Unity.Mathematics.quaternion m_Rotation`  
- `private System.Single m_MaxForwardOffset`  
- `private System.Single m_MaxBackwardOffset`  
- `private System.Single m_MinClearDistance`  
- `private System.Single m_NearPlane`  
- `private System.Single m_Smoothing`  
- `private Unity.Mathematics.float2 m_FieldOfView`  
- `private Unity.Collections.NativeReference<Game.Rendering.CameraCollisionSystem+Result> m_Result`  
- `private Game.Rendering.CameraCollisionSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CameraCollisionSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public CheckCollisions(Unity.Mathematics.float3& position, Unity.Mathematics.float3 previousPosition, Unity.Mathematics.quaternion rotation, System.Single maxForwardOffset, System.Single maxBackwardOffset, System.Single minClearDistance, System.Single nearPlane, System.Single smoothing, Unity.Mathematics.float2 fieldOfView) : System.Void`  
- `private static CheckCollisions(Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions, System.Single minClearRange, Unity.Mathematics.float2 limits) : System.Void`  
- `private static CheckMeshIntersect(Game.Rendering.CameraCollisionSystem+Line line, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions) : System.Void`  
- `private static CheckMeshIntersect(Game.Rendering.CameraCollisionSystem+Line line, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions) : System.Void`  
- `private static CheckMeshIntersect(Game.Rendering.CameraCollisionSystem+Line line, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions) : System.Void`  
- `private static CheckMeshIntersect(Game.Rendering.CameraCollisionSystem+Line line, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshVertex> vertices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshIndex> indices, Unity.Entities.DynamicBuffer<Game.Prefabs.MeshNode> nodes, Unity.Entities.DynamicBuffer<Game.Prefabs.ProceduralBone> prefabBones, Unity.Entities.DynamicBuffer<Game.Rendering.Bone> bones, Game.Rendering.Skeleton skeleton, Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions) : System.Void`  
- `private static CheckTriangleIntersect(Game.Rendering.CameraCollisionSystem+Line line, Colossal.Mathematics.Triangle3 triangle, Unity.Collections.NativeList<Game.Rendering.CameraCollisionSystem+Collision> collisions) : System.Void`  
- `private static Intersect(Game.Rendering.CameraCollisionSystem+Line line, Colossal.Mathematics.Bounds3 bounds, Unity.Mathematics.float2& t) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Rendering.CameraCollisionSystem+FindEntitiesFromTreeJob`  
- `Game.Rendering.CameraCollisionSystem+ObjectCollisionJob`  
- `Game.Rendering.CameraCollisionSystem+SelectCameraPositionJob`  
- `Game.Rendering.CameraCollisionSystem+Line`  
- `Game.Rendering.CameraCollisionSystem+Collision`  
- `Game.Rendering.CameraCollisionSystem+Result`  
- `Game.Rendering.CameraCollisionSystem+TypeHandle`  

