# Game.Rendering.ManagedBatchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Int32 <groupCount>k__BackingField`  
- `private System.Int32 <batchCount>k__BackingField`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.Rendering.BatchMeshSystem m_BatchMeshSystem`  
- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  
- `private Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem m_TextureStreamingSystem`  
- `private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, UnityEngine.Material> m_Materials`  
- `private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+GroupKey, Unity.Entities.Entity> m_Groups`  
- `private System.Collections.Generic.Dictionary<Game.Rendering.ManagedBatchSystem+MeshKey, Unity.Entities.Entity> m_Meshes`  
- `private System.Collections.Generic.List<Game.Rendering.ManagedBatchSystem+KeywordData> m_CachedKeywords`  
- `private System.Collections.Generic.List<Game.Rendering.ManagedBatchSystem+TextureData> m_CachedTextures`  
- `private Game.Rendering.ManagedBatchSystem+MaterialKey m_CachedMaterialKey`  
- `private Game.Rendering.ManagedBatchSystem+GroupKey m_CachedGroupKey`  
- `private Colossal.Rendering.VTTextureRequester m_VTTextureRequester`  
- `private Unity.Jobs.JobHandle m_VTRequestDependencies`  
- `private Unity.Entities.EntityQuery m_MeshSettingsQuery`  
- `private System.Boolean m_VTRequestsUpdated`  
- `private System.Int32 m_TunnelLayer`  
- `private System.Int32 m_MovingLayer`  
- `private System.Int32 m_PipelineLayer`  
- `private System.Int32 m_SubPipelineLayer`  
- `private System.Int32 m_WaterwayLayer`  
- `private System.Int32 m_OutlineLayer`  
- `private System.Int32 m_MarkerLayer`  
- `private System.Int32 m_DecalLayerMask`  
- `private System.Int32 m_AnimationTexture`  
- `private System.Int32 m_UseStack1`  
- `private System.Int32 m_ImpostorSize`  
- `private System.Int32 m_ImpostorOffset`  
- `private System.Int32 m_WorldspaceAlbedo`  
- `private System.Int32 m_MaskMap`  

## Properties

- `public System.Int32 materialCount { get }`  
- `public System.Int32 groupCount { get; private set }`  
- `public System.Int32 batchCount { get; private set }`  
- `public System.Collections.Generic.IReadOnlyDictionary<Game.Rendering.ManagedBatchSystem+MaterialKey, UnityEngine.Material> materials { get }`  
- `public Colossal.Rendering.VTTextureRequester VTTextureRequester { get }`  

## Constructors

- `public ManagedBatchSystem()`  

## Methods

- `public AddVTRequestWriter(Unity.Jobs.JobHandle dependencies) : System.Void`  
- `public CompleteVTRequests() : System.Void`  
- `private CreateBatch(System.Int32 groupIndex, System.Int32 batchIndex, Unity.Entities.Entity sharedMesh, Game.Rendering.GroupData& groupData, Game.Rendering.BatchData& batchData, Game.Rendering.PropertyData& lodFadeData) : Game.Rendering.CustomBatch`  
- `private CreateMaterial(Colossal.IO.AssetDatabase.SurfaceAsset sourceSurface, UnityEngine.Material sourceMaterial, Game.Rendering.ManagedBatchSystem+MaterialKey materialKey) : UnityEngine.Material`  
- `private DisableKeyword(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.String keyword) : System.Void`  
- `public EnabledShadersUpdated() : System.Void`  
- `private EnableKeyword(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.String keyword) : System.Void`  
- `public static GetTemplate(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset) : UnityEngine.Material`  
- `public GetVTRequestMaxPixels(Unity.Collections.NativeList`1[[System.Single, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& maxPixels0, Unity.Collections.NativeList`1[[System.Single, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& maxPixels1) : Unity.Jobs.JobHandle`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public ReloadVT() : System.Void`  
- `public RemoveMesh(Unity.Entities.Entity oldMesh, Unity.Entities.Entity newMesh = null) : System.Void`  
- `public ResetSharedMeshes() : System.Void`  
- `public ResetVT(System.Int32 desiredMipBias, UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode) : System.Void`  
- `private SetTexture(Game.Rendering.ManagedBatchSystem+MaterialKey materialKey, System.Int32 nameID, UnityEngine.Texture texture) : System.Void`  
- `public SetupVT(Game.Prefabs.RenderPrefab meshPrefab, UnityEngine.Material material, System.Int32 materialIndex) : System.Void`  

## Nested types

- `Game.Rendering.ManagedBatchSystem+KeywordData`  
- `Game.Rendering.ManagedBatchSystem+TextureData`  
- `Game.Rendering.ManagedBatchSystem+MaterialKey`  
- `Game.Rendering.ManagedBatchSystem+GroupKey`  
- `Game.Rendering.ManagedBatchSystem+MeshKey`  

