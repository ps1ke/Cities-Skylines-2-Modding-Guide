# Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Impostors`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private UnityEngine.GameObject m_RootGameObject`  
- `private UnityEngine.Camera m_Camera`  
- `private System.Int32 m_LayerIndex`  
- `private UnityEngine.MaterialPropertyBlock m_BakingPropertyBlock`  
- `private static readonly System.Int32 m_ImpostorSizeId`  
- `private static readonly UnityEngine.Matrix4x4 m_ScaleMatrix`  

## Properties

- `public UnityEngine.Renderer[] renderers { get }`  

## Constructors

- `public BakingScene(UnityEngine.GameObject rootGameObject, UnityEngine.Renderer[] renderers, UnityEngine.Matrix4x4 matrix, System.Int32 layerIndex = 31)`  

## Methods

- `private static ApplyKeywords(UnityEngine.Material material, System.String[] keywords) : System.Void`  
- `private CopyGameObject(UnityEngine.GameObject rootGameObject, UnityEngine.Transform r) : System.Void`  
- `public Dispose() : System.Void`  
- `private GetBakingMaterial(UnityEngine.Material sourceMaterial, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding materialBinding, UnityEngine.MaterialPropertyBlock& bakingPropertyBlock) : UnityEngine.Material`  
- `private ProcessRenderRequests(UnityEngine.Camera camera, UnityEngine.RenderTexture mask) : System.Void`  
- `public Render(Unity.Mathematics.float3 from, Unity.Mathematics.float3 to, System.Single nearClipPlane, System.Single farClipPlane, System.Single orthographicSize, UnityEngine.RenderTexture mask) : System.Void`  
- `public RenderMultiView(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] worldMatrices, System.Int32 viewCount, System.Single nearClipPlane, System.Single farClipPlane, System.Single orthographicSize, System.Collections.Generic.Dictionary<UnityEngine.Shader, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding> bakingMaterials) : System.Void`  
- `private RenderMultiViewGameObject(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] viewMatrices, UnityEngine.Matrix4x4[] viewsWorldMatrices, System.Int32 viewCount, UnityEngine.GameObject gameObject, System.Collections.Generic.Dictionary<UnityEngine.Shader, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding> bakingMaterials, System.Single farClipPlane) : System.Void`  
- `private RenderMultiViewMesh(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] viewsWorldMatrices, System.Int32 viewCount, UnityEngine.Mesh mesh, UnityEngine.Material material, System.Int32 subMeshIndex, System.Collections.Generic.Dictionary<UnityEngine.Shader, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding> bakingMaterials, System.Single farClipPlane, UnityEngine.Matrix4x4 objectWorldMatrix) : System.Void`  
- `public SetProxyTarget(UnityEngine.RenderTexture proxy) : System.Void`  

## Nested types

- `Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding`  
- `Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+<>c`  
- `Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+<>c__DisplayClass12_0`  

