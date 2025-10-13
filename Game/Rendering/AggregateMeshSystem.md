# Game.Rendering.AggregateMeshSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AggregateMeshSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Unity.Entities.EntityQuery m_CreatedPrefabQuery;
    private Unity.Entities.EntityQuery m_UpdatedLabelQuery;
    private Unity.Entities.EntityQuery m_LabelQuery;
    private Unity.Entities.EntityQuery m_UpdatedArrowQuery;
    private Unity.Entities.EntityQuery m_ArrowQuery;
    private Unity.Entities.EntityQuery m_TempAggregatedQuery;
    private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
    private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.NameSystem m_NameSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> m_LabelData;
    private System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> m_ArrowData;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_CachedLabels;
    private System.Int32 m_FaceColor;
    private System.Boolean m_TunnelSelectOn;
    private System.Boolean m_Loaded;
    private Game.Rendering.AggregateMeshSystem+TypeHandle __TypeHandle;

    public AggregateMeshSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Void ClearMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData);
    private System.Void DestroyMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData);
    private Unity.Jobs.JobHandle FillArrowMeshData(Unity.Jobs.JobHandle inputDeps);
    private Unity.Jobs.JobHandle FillNameMeshData(Unity.Jobs.JobHandle inputDeps);
    public System.Boolean GetArrowMaterial(System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material);
    public System.Int32 GetArrowMaterialCount();
    public System.Boolean GetArrowMesh(System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount);
    private System.Boolean GetLoaded();
    private System.Boolean GetMaterialData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material);
    private System.Boolean GetMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount);
    public System.Boolean GetNameMaterial(System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material);
    public System.Int32 GetNameMaterialCount();
    public System.Boolean GetNameMesh(System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount);
    private System.Void InitializePrefabs();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    private System.Void OnDictionaryChanged();
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void UpdateArrowMaterials(System.Boolean isLoaded);
    private Unity.Jobs.JobHandle UpdateArrowPositions(Unity.Jobs.JobHandle inputDeps, System.Boolean isLoaded);
    private Unity.Jobs.JobHandle UpdateLabelPositions(Unity.Jobs.JobHandle inputDeps, System.Boolean isLoaded);
    private System.Void UpdateLabelVertices(System.Boolean isLoaded);
    private System.Void UpdateUndergroundState(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Boolean undergroundOn);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CreatedPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedLabelQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedLabelQuery;
```

- `private Unity.Entities.EntityQuery m_LabelQuery`  

```csharp
private Unity.Entities.EntityQuery m_LabelQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedArrowQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedArrowQuery;
```

- `private Unity.Entities.EntityQuery m_ArrowQuery`  

```csharp
private Unity.Entities.EntityQuery m_ArrowQuery;
```

- `private Unity.Entities.EntityQuery m_TempAggregatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_TempAggregatedQuery;
```

- `private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem`  

```csharp
private Game.Rendering.OverlayRenderSystem m_OverlayRenderSystem;
```

- `private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem`  

```csharp
private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.NameSystem m_NameSystem`  

```csharp
private Game.UI.NameSystem m_NameSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> m_LabelData`  

```csharp
private System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> m_LabelData;
```

- `private System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> m_ArrowData`  

```csharp
private System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> m_ArrowData;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_CachedLabels`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, System.String> m_CachedLabels;
```

- `private System.Int32 m_FaceColor`  

```csharp
private System.Int32 m_FaceColor;
```

- `private System.Boolean m_TunnelSelectOn`  

```csharp
private System.Boolean m_TunnelSelectOn;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Rendering.AggregateMeshSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.AggregateMeshSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AggregateMeshSystem()`  

```csharp
public AggregateMeshSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `private ClearMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData) : System.Void`  

```csharp
private System.Void ClearMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData);
```

- `private DestroyMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData) : System.Void`  

```csharp
private System.Void DestroyMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData);
```

- `private FillArrowMeshData(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle FillArrowMeshData(Unity.Jobs.JobHandle inputDeps);
```

- `private FillNameMeshData(Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle FillNameMeshData(Unity.Jobs.JobHandle inputDeps);
```

- `public GetArrowMaterial(System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material) : System.Boolean`  

```csharp
public System.Boolean GetArrowMaterial(System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material);
```

- `public GetArrowMaterialCount() : System.Int32`  

```csharp
public System.Int32 GetArrowMaterialCount();
```

- `public GetArrowMesh(System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount) : System.Boolean`  

```csharp
public System.Boolean GetArrowMesh(System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount);
```

- `private GetLoaded() : System.Boolean`  

```csharp
private System.Boolean GetLoaded();
```

- `private GetMaterialData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material) : System.Boolean`  

```csharp
private System.Boolean GetMaterialData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material);
```

- `private GetMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount) : System.Boolean`  

```csharp
private System.Boolean GetMeshData(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount);
```

- `public GetNameMaterial(System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material) : System.Boolean`  

```csharp
public System.Boolean GetNameMaterial(System.Int32 index, System.Int32 subMeshIndex, UnityEngine.Material& material);
```

- `public GetNameMaterialCount() : System.Int32`  

```csharp
public System.Int32 GetNameMaterialCount();
```

- `public GetNameMesh(System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount) : System.Boolean`  

```csharp
public System.Boolean GetNameMesh(System.Int32 index, UnityEngine.Mesh& mesh, System.Int32& subMeshCount);
```

- `private InitializePrefabs() : System.Void`  

```csharp
private System.Void InitializePrefabs();
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

- `private OnDictionaryChanged() : System.Void`  

```csharp
private System.Void OnDictionaryChanged();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private UpdateArrowMaterials(System.Boolean isLoaded) : System.Void`  

```csharp
private System.Void UpdateArrowMaterials(System.Boolean isLoaded);
```

- `private UpdateArrowPositions(Unity.Jobs.JobHandle inputDeps, System.Boolean isLoaded) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle UpdateArrowPositions(Unity.Jobs.JobHandle inputDeps, System.Boolean isLoaded);
```

- `private UpdateLabelPositions(Unity.Jobs.JobHandle inputDeps, System.Boolean isLoaded) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle UpdateLabelPositions(Unity.Jobs.JobHandle inputDeps, System.Boolean isLoaded);
```

- `private UpdateLabelVertices(System.Boolean isLoaded) : System.Void`  

```csharp
private System.Void UpdateLabelVertices(System.Boolean isLoaded);
```

- `private UpdateUndergroundState(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Boolean undergroundOn) : System.Void`  

```csharp
private System.Void UpdateUndergroundState(System.Collections.Generic.List<Game.Rendering.AggregateMeshSystem+MeshData> meshData, System.Boolean undergroundOn);
```


## Nested types

- `Game.Rendering.AggregateMeshSystem+MaterialData`  
- `Game.Rendering.AggregateMeshSystem+MeshData`  
- `Game.Rendering.AggregateMeshSystem+MaterialUpdate`  
- `Game.Rendering.AggregateMeshSystem+UpdateLabelPositionsJob`  
- `Game.Rendering.AggregateMeshSystem+FillTempMapJob`  
- `Game.Rendering.AggregateMeshSystem+TempValue`  
- `Game.Rendering.AggregateMeshSystem+UpdateArrowPositionsJob`  
- `Game.Rendering.AggregateMeshSystem+LabelVertexData`  
- `Game.Rendering.AggregateMeshSystem+SubMeshData`  
- `Game.Rendering.AggregateMeshSystem+FillNameDataJob`  
- `Game.Rendering.AggregateMeshSystem+ArrowVertexData`  
- `Game.Rendering.AggregateMeshSystem+FillArrowDataJob`  
- `Game.Rendering.AggregateMeshSystem+TypeHandle`  

