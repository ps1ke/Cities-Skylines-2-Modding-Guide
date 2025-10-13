# Game.Rendering.ManagedBatchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ManagedBatchSystem : Game.GameSystemBase
{
    private System.Int32 <groupCount>k__BackingField;
    private System.Int32 <batchCount>k__BackingField;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem m_TextureStreamingSystem;
    private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, UnityEngine.Material> m_Materials;
    private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+GroupKey, Unity.Entities.Entity> m_Groups;
    private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MeshKey, Unity.Entities.Entity> m_Meshes;
    private System.Collections.Generic.List<Game.Rendering.ManagedBatchSystem+KeywordData> m_CachedKeywords;
    private System.Collections.Generic.List<Game.Rendering.ManagedBatchSystem+TextureData> m_CachedTextures;
    private Game.Rendering.ManagedBatchSystem+MaterialKey m_CachedMaterialKey;
    private Game.Rendering.ManagedBatchSystem+GroupKey m_CachedGroupKey;
    private Colossal.Rendering.VTTextureRequester m_VTTextureRequester;
    private Unity.Jobs.JobHandle m_VTRequestDependencies;
    private Unity.Entities.EntityQuery m_MeshSettingsQuery;
    private System.Boolean m_VTRequestsUpdated;
    private System.Int32 m_TunnelLayer;
    private System.Int32 m_MovingLayer;
    private System.Int32 m_PipelineLayer;
    private System.Int32 m_SubPipelineLayer;
    private System.Int32 m_WaterwayLayer;
    private System.Int32 m_OutlineLayer;
    private System.Int32 m_MarkerLayer;
    private System.Int32 m_DecalLayerMask;
    private System.Int32 m_AnimationTexture;
    private System.Int32 m_UseStack1;
    private System.Int32 m_ImpostorSize;
    private System.Int32 m_ImpostorOffset;
    private System.Int32 m_WorldspaceAlbedo;
    private System.Int32 m_MaskMap;

    public System.Int32 materialCount { get; }
    public System.Int32 groupCount { get; private set; }
    public System.Int32 batchCount { get; private set; }
    public System.Collections.Generic.IReadOnlyDictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, UnityEngine.Material> materials { get; }
    public Colossal.Rendering.VTTextureRequester VTTextureRequester { get; }

    public ManagedBatchSystem();

    public System.Void AddVTRequestWriter(Unity.Jobs.JobHandle dependencies);
    public System.Void CompleteVTRequests();
    private Game.Rendering.CustomBatch CreateBatch(System.Int32 groupIndex, System.Int32 batchIndex, Unity.Entities.Entity sharedMesh, Game.Rendering.GroupData& groupData, Game.Rendering.BatchData& batchData, Game.Rendering.PropertyData& lodFadeData);
    private UnityEngine.Material CreateMaterial(Colossal.IO.AssetDatabase.SurfaceAsset sourceSurface, UnityEngine.Material sourceMaterial, Game.Rendering.ManagedBatchSystem+MaterialKey materialKey);
    private System.Void DisableKeyword(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.String keyword);
    public System.Void EnabledShadersUpdated();
    private System.Void EnableKeyword(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.String keyword);
    public static UnityEngine.Material GetTemplate(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset);
    public Unity.Jobs.JobHandle GetVTRequestMaxPixels(Unity.Collections.NativeList`1[[System.Single, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& maxPixels0, Unity.Collections.NativeList`1[[System.Single, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& maxPixels1);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void ReloadVT();
    public System.Void RemoveMesh(Unity.Entities.Entity oldMesh, Unity.Entities.Entity newMesh);
    public System.Void ResetSharedMeshes();
    public System.Void ResetVT(System.Int32 desiredMipBias, UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode);
    private System.Void SetTexture(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.Int32 nameID, UnityEngine.Texture texture);
    public System.Void SetupVT(Game.Prefabs.RenderPrefab meshPrefab, UnityEngine.Material material, System.Int32 materialIndex);
}
```


## Fields

- `private System.Int32 <groupCount>k__BackingField`  

```csharp
private System.Int32 <groupCount>k__BackingField;
```

- `private System.Int32 <batchCount>k__BackingField`  

```csharp
private System.Int32 <batchCount>k__BackingField;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.BatchMeshSystem m_BatchMeshSystem`  

```csharp
private Game.Rendering.BatchMeshSystem m_BatchMeshSystem;
```

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem m_TextureStreamingSystem`  

```csharp
private Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem m_TextureStreamingSystem;
```

- `private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, UnityEngine.Material> m_Materials`  

```csharp
private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, UnityEngine.Material> m_Materials;
```

- `private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+GroupKey, Unity.Entities.Entity> m_Groups`  

```csharp
private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+GroupKey, Unity.Entities.Entity> m_Groups;
```

- `private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MeshKey, Unity.Entities.Entity> m_Meshes`  

```csharp
private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MeshKey, Unity.Entities.Entity> m_Meshes;
```

- `private System.Collections.Generic.List<Game.Rendering.ManagedBatchSystem+KeywordData> m_CachedKeywords`  

```csharp
private System.Collections.Generic.List<Game.Rendering.ManagedBatchSystem+KeywordData> m_CachedKeywords;
```

- `private System.Collections.Generic.List<Game.Rendering.ManagedBatchSystem+TextureData> m_CachedTextures`  

```csharp
private System.Collections.Generic.List<Game.Rendering.ManagedBatchSystem+TextureData> m_CachedTextures;
```

- `private Game.Rendering.ManagedBatchSystem+MaterialKey m_CachedMaterialKey`  

```csharp
private Game.Rendering.ManagedBatchSystem+MaterialKey m_CachedMaterialKey;
```

- `private Game.Rendering.ManagedBatchSystem+GroupKey m_CachedGroupKey`  

```csharp
private Game.Rendering.ManagedBatchSystem+GroupKey m_CachedGroupKey;
```

- `private Colossal.Rendering.VTTextureRequester m_VTTextureRequester`  

```csharp
private Colossal.Rendering.VTTextureRequester m_VTTextureRequester;
```

- `private Unity.Jobs.JobHandle m_VTRequestDependencies`  

```csharp
private Unity.Jobs.JobHandle m_VTRequestDependencies;
```

- `private Unity.Entities.EntityQuery m_MeshSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_MeshSettingsQuery;
```

- `private System.Boolean m_VTRequestsUpdated`  

```csharp
private System.Boolean m_VTRequestsUpdated;
```

- `private System.Int32 m_TunnelLayer`  

```csharp
private System.Int32 m_TunnelLayer;
```

- `private System.Int32 m_MovingLayer`  

```csharp
private System.Int32 m_MovingLayer;
```

- `private System.Int32 m_PipelineLayer`  

```csharp
private System.Int32 m_PipelineLayer;
```

- `private System.Int32 m_SubPipelineLayer`  

```csharp
private System.Int32 m_SubPipelineLayer;
```

- `private System.Int32 m_WaterwayLayer`  

```csharp
private System.Int32 m_WaterwayLayer;
```

- `private System.Int32 m_OutlineLayer`  

```csharp
private System.Int32 m_OutlineLayer;
```

- `private System.Int32 m_MarkerLayer`  

```csharp
private System.Int32 m_MarkerLayer;
```

- `private System.Int32 m_DecalLayerMask`  

```csharp
private System.Int32 m_DecalLayerMask;
```

- `private System.Int32 m_AnimationTexture`  

```csharp
private System.Int32 m_AnimationTexture;
```

- `private System.Int32 m_UseStack1`  

```csharp
private System.Int32 m_UseStack1;
```

- `private System.Int32 m_ImpostorSize`  

```csharp
private System.Int32 m_ImpostorSize;
```

- `private System.Int32 m_ImpostorOffset`  

```csharp
private System.Int32 m_ImpostorOffset;
```

- `private System.Int32 m_WorldspaceAlbedo`  

```csharp
private System.Int32 m_WorldspaceAlbedo;
```

- `private System.Int32 m_MaskMap`  

```csharp
private System.Int32 m_MaskMap;
```


## Properties

- `public System.Int32 materialCount { get }`  

```csharp
public System.Int32 materialCount { get; }
```

- `public System.Int32 groupCount { get; private set }`  

```csharp
public System.Int32 groupCount { get; private set; }
```

- `public System.Int32 batchCount { get; private set }`  

```csharp
public System.Int32 batchCount { get; private set; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, UnityEngine.Material> materials { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, UnityEngine.Material> materials { get; }
```

- `public Colossal.Rendering.VTTextureRequester VTTextureRequester { get }`  

```csharp
public Colossal.Rendering.VTTextureRequester VTTextureRequester { get; }
```


## Constructors

- `public ManagedBatchSystem()`  

```csharp
public ManagedBatchSystem();
```


## Methods

- `public AddVTRequestWriter(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public System.Void AddVTRequestWriter(Unity.Jobs.JobHandle dependencies);
```

- `public CompleteVTRequests() : System.Void`  

```csharp
public System.Void CompleteVTRequests();
```

- `private CreateBatch(System.Int32 groupIndex, System.Int32 batchIndex, Unity.Entities.Entity sharedMesh, Game.Rendering.GroupData& groupData, Game.Rendering.BatchData& batchData, Game.Rendering.PropertyData& lodFadeData) : Game.Rendering.CustomBatch`  

```csharp
private Game.Rendering.CustomBatch CreateBatch(System.Int32 groupIndex, System.Int32 batchIndex, Unity.Entities.Entity sharedMesh, Game.Rendering.GroupData& groupData, Game.Rendering.BatchData& batchData, Game.Rendering.PropertyData& lodFadeData);
```

- `private CreateMaterial(Colossal.IO.AssetDatabase.SurfaceAsset sourceSurface, UnityEngine.Material sourceMaterial, Game.Rendering.ManagedBatchSystem+MaterialKey materialKey) : UnityEngine.Material`  

```csharp
private UnityEngine.Material CreateMaterial(Colossal.IO.AssetDatabase.SurfaceAsset sourceSurface, UnityEngine.Material sourceMaterial, Game.Rendering.ManagedBatchSystem+MaterialKey materialKey);
```

- `private DisableKeyword(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.String keyword) : System.Void`  

```csharp
private System.Void DisableKeyword(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.String keyword);
```

- `public EnabledShadersUpdated() : System.Void`  

```csharp
public System.Void EnabledShadersUpdated();
```

- `private EnableKeyword(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.String keyword) : System.Void`  

```csharp
private System.Void EnableKeyword(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.String keyword);
```

- `public static GetTemplate(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset) : UnityEngine.Material`  

```csharp
public static UnityEngine.Material GetTemplate(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset);
```

- `public GetVTRequestMaxPixels(Unity.Collections.NativeList`1[[System.Single, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& maxPixels0, Unity.Collections.NativeList`1[[System.Single, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& maxPixels1) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle GetVTRequestMaxPixels(Unity.Collections.NativeList`1[[System.Single, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& maxPixels0, Unity.Collections.NativeList`1[[System.Single, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& maxPixels1);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public ReloadVT() : System.Void`  

```csharp
public System.Void ReloadVT();
```

- `public RemoveMesh(Unity.Entities.Entity oldMesh, Unity.Entities.Entity newMesh = null) : System.Void`  

```csharp
public System.Void RemoveMesh(Unity.Entities.Entity oldMesh, Unity.Entities.Entity newMesh);
```

- `public ResetSharedMeshes() : System.Void`  

```csharp
public System.Void ResetSharedMeshes();
```

- `public ResetVT(System.Int32 desiredMipBias, UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode) : System.Void`  

```csharp
public System.Void ResetVT(System.Int32 desiredMipBias, UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode);
```

- `private SetTexture(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.Int32 nameID, UnityEngine.Texture texture) : System.Void`  

```csharp
private System.Void SetTexture(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.Int32 nameID, UnityEngine.Texture texture);
```

- `public SetupVT(Game.Prefabs.RenderPrefab meshPrefab, UnityEngine.Material material, System.Int32 materialIndex) : System.Void`  

```csharp
public System.Void SetupVT(Game.Prefabs.RenderPrefab meshPrefab, UnityEngine.Material material, System.Int32 materialIndex);
```


## Nested types

- `Game.Rendering.ManagedBatchSystem+KeywordData`  
- `Game.Rendering.ManagedBatchSystem+TextureData`  
- `Game.Rendering.ManagedBatchSystem+MaterialKey`  
- `Game.Rendering.ManagedBatchSystem+GroupKey`  
- `Game.Rendering.ManagedBatchSystem+MeshKey`  

