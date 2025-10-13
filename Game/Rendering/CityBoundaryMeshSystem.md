# Game.Rendering.CityBoundaryMeshSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CityBoundaryMeshSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Areas.MapTileSystem m_MapTileSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_MapTileQuery;
    private Unity.Entities.EntityQuery m_SettingsQuery;
    private UnityEngine.Mesh m_BoundaryMesh;
    private UnityEngine.Material m_BoundaryMaterial;
    private Unity.Jobs.JobHandle m_MeshDependencies;
    private Unity.Collections.NativeList<Unity.Mathematics.float3> m_Vertices;
    private Unity.Collections.NativeList<Unity.Mathematics.float2> m_UVs;
    private Unity.Collections.NativeList<UnityEngine.Color32> m_Colors;
    private Unity.Collections.NativeList<System.Int32> m_Indices;
    private Colossal.Collections.NativeValue<Colossal.Mathematics.Bounds3> m_Bounds;
    private System.Boolean m_Loaded;
    private Game.Rendering.CityBoundaryMeshSystem+TypeHandle __TypeHandle;

    public CityBoundaryMeshSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void Clear();
    private System.Void DestroyMesh();
    private System.Void DisposeMeshData();
    public System.Boolean GetBoundaryMesh(UnityEngine.Mesh& mesh, UnityEngine.Material& material);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Areas.MapTileSystem m_MapTileSystem`  

```csharp
private Game.Areas.MapTileSystem m_MapTileSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_MapTileQuery`  

```csharp
private Unity.Entities.EntityQuery m_MapTileQuery;
```

- `private Unity.Entities.EntityQuery m_SettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_SettingsQuery;
```

- `private UnityEngine.Mesh m_BoundaryMesh`  

```csharp
private UnityEngine.Mesh m_BoundaryMesh;
```

- `private UnityEngine.Material m_BoundaryMaterial`  

```csharp
private UnityEngine.Material m_BoundaryMaterial;
```

- `private Unity.Jobs.JobHandle m_MeshDependencies`  

```csharp
private Unity.Jobs.JobHandle m_MeshDependencies;
```

- `private Unity.Collections.NativeList<Unity.Mathematics.float3> m_Vertices`  

```csharp
private Unity.Collections.NativeList<Unity.Mathematics.float3> m_Vertices;
```

- `private Unity.Collections.NativeList<Unity.Mathematics.float2> m_UVs`  

```csharp
private Unity.Collections.NativeList<Unity.Mathematics.float2> m_UVs;
```

- `private Unity.Collections.NativeList<UnityEngine.Color32> m_Colors`  

```csharp
private Unity.Collections.NativeList<UnityEngine.Color32> m_Colors;
```

- `private Unity.Collections.NativeList<System.Int32> m_Indices`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_Indices;
```

- `private Colossal.Collections.NativeValue<Colossal.Mathematics.Bounds3> m_Bounds`  

```csharp
private Colossal.Collections.NativeValue<Colossal.Mathematics.Bounds3> m_Bounds;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Rendering.CityBoundaryMeshSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.CityBoundaryMeshSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CityBoundaryMeshSystem()`  

```csharp
public CityBoundaryMeshSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private Clear() : System.Void`  

```csharp
private System.Void Clear();
```

- `private DestroyMesh() : System.Void`  

```csharp
private System.Void DestroyMesh();
```

- `private DisposeMeshData() : System.Void`  

```csharp
private System.Void DisposeMeshData();
```

- `public GetBoundaryMesh(UnityEngine.Mesh& mesh, UnityEngine.Material& material) : System.Boolean`  

```csharp
public System.Boolean GetBoundaryMesh(UnityEngine.Mesh& mesh, UnityEngine.Material& material);
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

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```


## Nested types

- `Game.Rendering.CityBoundaryMeshSystem+Boundary`  
- `Game.Rendering.CityBoundaryMeshSystem+FillBoundaryQueueJob`  
- `Game.Rendering.CityBoundaryMeshSystem+FillBoundaryMeshDataJob`  
- `Game.Rendering.CityBoundaryMeshSystem+TypeHandle`  

