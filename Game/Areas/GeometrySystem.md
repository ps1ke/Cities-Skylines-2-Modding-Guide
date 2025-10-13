# Game.Areas.GeometrySystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GeometrySystem : Game.GameSystemBase
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Unity.Entities.EntityQuery m_UpdatedAreasQuery;
    private Unity.Entities.EntityQuery m_AllAreasQuery;
    private Unity.Entities.EntityQuery m_CreatedBuildingsQuery;
    private System.Boolean m_Loaded;
    private Game.Areas.GeometrySystem+TypeHandle __TypeHandle;

    public GeometrySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public static System.Single Area(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes);
    public static System.Single Area(Unity.Collections.NativeArray<Game.Prefabs.SubAreaNode> nodes);
    public static System.Void BuildEdgeBounds(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Collections.NativeArray<Unity.Mathematics.float3> expandedNodes, Unity.Collections.NativeArray`1[[Colossal.Mathematics.Bounds2, Colossal.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeBounds, System.Int32& totalDepth);
    public static System.Void EqualizeTriangles<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles);
    private static System.Single GetEqualizationValue(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, Game.Areas.Triangle triangle);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnUpdate();
    private static System.Boolean Snip(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, Game.Areas.GeometrySystem+Index index0, Game.Areas.GeometrySystem+Index index1, Game.Areas.GeometrySystem+Index index2, System.Int32 nodeCount, System.Int32 totalDepth, Unity.Collections.NativeArray<Colossal.Mathematics.Bounds2> edgeBounds, Unity.Collections.NativeArray<Game.Areas.GeometrySystem+Index> indexBuffer);
    public System.Void TerrainHeightsReadyAfterLoading();
    public static System.Void Triangulate<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles, Unity.Collections.NativeArray<Colossal.Mathematics.Bounds2> edgeBounds, System.Int32 totalDepth, System.Boolean isCounterClockwise);
    private static System.Boolean TurnEdgeIfNeeded<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles, Unity.Collections.NativeParallelHashMap<Unity.Mathematics.int2, Unity.Mathematics.int2> edgeMap, Unity.Mathematics.int2 index1, Unity.Mathematics.int2 index2);
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedAreasQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedAreasQuery;
```

- `private Unity.Entities.EntityQuery m_AllAreasQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllAreasQuery;
```

- `private Unity.Entities.EntityQuery m_CreatedBuildingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedBuildingsQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Areas.GeometrySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.GeometrySystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GeometrySystem()`  

```csharp
public GeometrySystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public static Area(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes) : System.Single`  

```csharp
public static System.Single Area(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes);
```

- `public static Area(Unity.Collections.NativeArray<Game.Prefabs.SubAreaNode> nodes) : System.Single`  

```csharp
public static System.Single Area(Unity.Collections.NativeArray<Game.Prefabs.SubAreaNode> nodes);
```

- `public static BuildEdgeBounds(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Collections.NativeArray<Unity.Mathematics.float3> expandedNodes, Unity.Collections.NativeArray`1[[Colossal.Mathematics.Bounds2, Colossal.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeBounds, System.Int32& totalDepth) : System.Void`  

```csharp
public static System.Void BuildEdgeBounds(Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Collections.NativeArray<Unity.Mathematics.float3> expandedNodes, Unity.Collections.NativeArray`1[[Colossal.Mathematics.Bounds2, Colossal.Mathematics, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeBounds, System.Int32& totalDepth);
```

- `public static EqualizeTriangles<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles) : System.Void`  

```csharp
public static System.Void EqualizeTriangles<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles);
```

- `private static GetEqualizationValue(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, Game.Areas.Triangle triangle) : System.Single`  

```csharp
private static System.Single GetEqualizationValue(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, Game.Areas.Triangle triangle);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private static Snip(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, Game.Areas.GeometrySystem+Index index0, Game.Areas.GeometrySystem+Index index1, Game.Areas.GeometrySystem+Index index2, System.Int32 nodeCount, System.Int32 totalDepth, Unity.Collections.NativeArray<Colossal.Mathematics.Bounds2> edgeBounds, Unity.Collections.NativeArray<Game.Areas.GeometrySystem+Index> indexBuffer) : System.Boolean`  

```csharp
private static System.Boolean Snip(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, Game.Areas.GeometrySystem+Index index0, Game.Areas.GeometrySystem+Index index1, Game.Areas.GeometrySystem+Index index2, System.Int32 nodeCount, System.Int32 totalDepth, Unity.Collections.NativeArray<Colossal.Mathematics.Bounds2> edgeBounds, Unity.Collections.NativeArray<Game.Areas.GeometrySystem+Index> indexBuffer);
```

- `public TerrainHeightsReadyAfterLoading() : System.Void`  

```csharp
public System.Void TerrainHeightsReadyAfterLoading();
```

- `public static Triangulate<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles, Unity.Collections.NativeArray<Colossal.Mathematics.Bounds2> edgeBounds, System.Int32 totalDepth, System.Boolean isCounterClockwise) : System.Void`  

```csharp
public static System.Void Triangulate<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles, Unity.Collections.NativeArray<Colossal.Mathematics.Bounds2> edgeBounds, System.Int32 totalDepth, System.Boolean isCounterClockwise);
```

- `private static TurnEdgeIfNeeded<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles, Unity.Collections.NativeParallelHashMap<Unity.Mathematics.int2, Unity.Mathematics.int2> edgeMap, Unity.Mathematics.int2 index1, Unity.Mathematics.int2 index2) : System.Boolean`  

```csharp
private static System.Boolean TurnEdgeIfNeeded<T>(Unity.Collections.NativeArray<Unity.Mathematics.float3> nodes, T triangles, Unity.Collections.NativeParallelHashMap<Unity.Mathematics.int2, Unity.Mathematics.int2> edgeMap, Unity.Mathematics.int2 index1, Unity.Mathematics.int2 index2);
```


## Nested types

- `Game.Areas.GeometrySystem+TriangulateAreasJob`  
- `Game.Areas.GeometrySystem+Index`  
- `Game.Areas.GeometrySystem+TypeHandle`  

