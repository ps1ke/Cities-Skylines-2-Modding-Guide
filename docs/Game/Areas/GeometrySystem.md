# Game.Areas.GeometrySystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Unity.Entities.EntityQuery m_UpdatedAreasQuery`  
- `private Unity.Entities.EntityQuery m_AllAreasQuery`  
- `private Unity.Entities.EntityQuery m_CreatedBuildingsQuery`  
- `private System.Boolean m_Loaded`  
- `private Game.Areas.GeometrySystem+TypeHandle __TypeHandle`  

## Constructors

- `public GeometrySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static Area(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes) : System.Single`  
- `public static Area(Unity.Collections.NativeArray<Game.Prefabs.SubAreaNode> nodes) : System.Single`  
- `public static BuildEdgeBounds(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Collections.NativeArray<Unity.Mathematics.float3> expandedNodes, Unity.Collections.NativeArray`1[[Colossal.Mathematics.Bounds2, Colossal.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeBounds, System.Int32& totalDepth) : System.Void`  
- `public static EqualizeTriangles<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles) : System.Void`  
- `private static GetEqualizationValue(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, Game.Areas.Triangle triangle) : System.Single`  
- `private GetLoaded() : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private static Snip(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, Game.Areas.GeometrySystem+Index index0, Game.Areas.GeometrySystem+Index index1, Game.Areas.GeometrySystem+Index index2, System.Int32 nodeCount, System.Int32 totalDepth, Unity.Collections.NativeArray<Colossal.Mathematics.Bounds2> edgeBounds, Unity.Collections.NativeArray<Game.Areas.GeometrySystem+Index> indexBuffer) : System.Boolean`  
- `public TerrainHeightsReadyAfterLoading() : System.Void`  
- `public static Triangulate<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles, Unity.Collections.NativeArray<Colossal.Mathematics.Bounds2> edgeBounds, System.Int32 totalDepth, System.Boolean isCounterClockwise) : System.Void`  
- `private static TurnEdgeIfNeeded<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles, Unity.Collections.NativeParallelHashMap<Unity.Mathematics.int2, Unity.Mathematics.int2> edgeMap, Unity.Mathematics.int2 index1, Unity.Mathematics.int2 index2) : System.Boolean`  

## Nested types

- `Game.Areas.GeometrySystem+TriangulateAreasJob`  
- `Game.Areas.GeometrySystem+Index`  
- `Game.Areas.GeometrySystem+TypeHandle`  

