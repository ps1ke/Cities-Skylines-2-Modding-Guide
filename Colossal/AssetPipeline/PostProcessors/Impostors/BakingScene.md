# Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Impostors`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class BakingScene : System.IDisposable
{
    private UnityEngine.GameObject m_RootGameObject;
    private UnityEngine.Camera m_Camera;
    private System.Int32 m_LayerIndex;
    private UnityEngine.MaterialPropertyBlock m_BakingPropertyBlock;
    private static readonly System.Int32 m_ImpostorSizeId;
    private static readonly UnityEngine.Matrix4x4 m_ScaleMatrix;

    public UnityEngine.Renderer[] renderers { get; }

    public BakingScene(UnityEngine.GameObject rootGameObject, UnityEngine.Renderer[] renderers, UnityEngine.Matrix4x4 matrix, System.Int32 layerIndex);

    private static System.Void ApplyKeywords(UnityEngine.Material material, System.String[] keywords);
    private System.Void CopyGameObject(UnityEngine.GameObject rootGameObject, UnityEngine.Transform r);
    public System.Void Dispose();
    private UnityEngine.Material GetBakingMaterial(UnityEngine.Material sourceMaterial, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding materialBinding, UnityEngine.MaterialPropertyBlock& bakingPropertyBlock);
    private System.Void ProcessRenderRequests(UnityEngine.Camera camera, UnityEngine.RenderTexture mask);
    public System.Void Render(Unity.Mathematics.float3 from, Unity.Mathematics.float3 to, System.Single nearClipPlane, System.Single farClipPlane, System.Single orthographicSize, UnityEngine.RenderTexture mask);
    public System.Void RenderMultiView(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] worldMatrices, System.Int32 viewCount, System.Single nearClipPlane, System.Single farClipPlane, System.Single orthographicSize, System.Collections.Generic.Dictionary<UnityEngine.Shader, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding> bakingMaterials);
    private System.Void RenderMultiViewGameObject(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] viewMatrices, UnityEngine.Matrix4x4[] viewsWorldMatrices, System.Int32 viewCount, UnityEngine.GameObject gameObject, System.Collections.Generic.Dictionary<UnityEngine.Shader, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding> bakingMaterials, System.Single farClipPlane);
    private System.Void RenderMultiViewMesh(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] viewsWorldMatrices, System.Int32 viewCount, UnityEngine.Mesh mesh, UnityEngine.Material material, System.Int32 subMeshIndex, System.Collections.Generic.Dictionary<UnityEngine.Shader, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding> bakingMaterials, System.Single farClipPlane, UnityEngine.Matrix4x4 objectWorldMatrix);
    public System.Void SetProxyTarget(UnityEngine.RenderTexture proxy);
}
```


## Fields

- `private UnityEngine.GameObject m_RootGameObject`  

```csharp
private UnityEngine.GameObject m_RootGameObject;
```

- `private UnityEngine.Camera m_Camera`  

```csharp
private UnityEngine.Camera m_Camera;
```

- `private System.Int32 m_LayerIndex`  

```csharp
private System.Int32 m_LayerIndex;
```

- `private UnityEngine.MaterialPropertyBlock m_BakingPropertyBlock`  

```csharp
private UnityEngine.MaterialPropertyBlock m_BakingPropertyBlock;
```

- `private static readonly System.Int32 m_ImpostorSizeId`  

```csharp
private static readonly System.Int32 m_ImpostorSizeId;
```

- `private static readonly UnityEngine.Matrix4x4 m_ScaleMatrix`  

```csharp
private static readonly UnityEngine.Matrix4x4 m_ScaleMatrix;
```


## Properties

- `public UnityEngine.Renderer[] renderers { get }`  

```csharp
public UnityEngine.Renderer[] renderers { get; }
```


## Constructors

- `public BakingScene(UnityEngine.GameObject rootGameObject, UnityEngine.Renderer[] renderers, UnityEngine.Matrix4x4 matrix, System.Int32 layerIndex = 31)`  

```csharp
public BakingScene(UnityEngine.GameObject rootGameObject, UnityEngine.Renderer[] renderers, UnityEngine.Matrix4x4 matrix, System.Int32 layerIndex);
```


## Methods

- `private static ApplyKeywords(UnityEngine.Material material, System.String[] keywords) : System.Void`  

```csharp
private static System.Void ApplyKeywords(UnityEngine.Material material, System.String[] keywords);
```

- `private CopyGameObject(UnityEngine.GameObject rootGameObject, UnityEngine.Transform r) : System.Void`  

```csharp
private System.Void CopyGameObject(UnityEngine.GameObject rootGameObject, UnityEngine.Transform r);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `private GetBakingMaterial(UnityEngine.Material sourceMaterial, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding materialBinding, UnityEngine.MaterialPropertyBlock& bakingPropertyBlock) : UnityEngine.Material`  

```csharp
private UnityEngine.Material GetBakingMaterial(UnityEngine.Material sourceMaterial, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding materialBinding, UnityEngine.MaterialPropertyBlock& bakingPropertyBlock);
```

- `private ProcessRenderRequests(UnityEngine.Camera camera, UnityEngine.RenderTexture mask) : System.Void`  

```csharp
private System.Void ProcessRenderRequests(UnityEngine.Camera camera, UnityEngine.RenderTexture mask);
```

- `public Render(Unity.Mathematics.float3 from, Unity.Mathematics.float3 to, System.Single nearClipPlane, System.Single farClipPlane, System.Single orthographicSize, UnityEngine.RenderTexture mask) : System.Void`  

```csharp
public System.Void Render(Unity.Mathematics.float3 from, Unity.Mathematics.float3 to, System.Single nearClipPlane, System.Single farClipPlane, System.Single orthographicSize, UnityEngine.RenderTexture mask);
```

- `public RenderMultiView(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] worldMatrices, System.Int32 viewCount, System.Single nearClipPlane, System.Single farClipPlane, System.Single orthographicSize, System.Collections.Generic.Dictionary<UnityEngine.Shader, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding> bakingMaterials) : System.Void`  

```csharp
public System.Void RenderMultiView(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] worldMatrices, System.Int32 viewCount, System.Single nearClipPlane, System.Single farClipPlane, System.Single orthographicSize, System.Collections.Generic.Dictionary<UnityEngine.Shader, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding> bakingMaterials);
```

- `private RenderMultiViewGameObject(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] viewMatrices, UnityEngine.Matrix4x4[] viewsWorldMatrices, System.Int32 viewCount, UnityEngine.GameObject gameObject, System.Collections.Generic.Dictionary<UnityEngine.Shader, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding> bakingMaterials, System.Single farClipPlane) : System.Void`  

```csharp
private System.Void RenderMultiViewGameObject(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] viewMatrices, UnityEngine.Matrix4x4[] viewsWorldMatrices, System.Int32 viewCount, UnityEngine.GameObject gameObject, System.Collections.Generic.Dictionary<UnityEngine.Shader, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding> bakingMaterials, System.Single farClipPlane);
```

- `private RenderMultiViewMesh(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] viewsWorldMatrices, System.Int32 viewCount, UnityEngine.Mesh mesh, UnityEngine.Material material, System.Int32 subMeshIndex, System.Collections.Generic.Dictionary<UnityEngine.Shader, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding> bakingMaterials, System.Single farClipPlane, UnityEngine.Matrix4x4 objectWorldMatrix) : System.Void`  

```csharp
private System.Void RenderMultiViewMesh(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] viewsWorldMatrices, System.Int32 viewCount, UnityEngine.Mesh mesh, UnityEngine.Material material, System.Int32 subMeshIndex, System.Collections.Generic.Dictionary<UnityEngine.Shader, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding> bakingMaterials, System.Single farClipPlane, UnityEngine.Matrix4x4 objectWorldMatrix);
```

- `public SetProxyTarget(UnityEngine.RenderTexture proxy) : System.Void`  

```csharp
public System.Void SetProxyTarget(UnityEngine.RenderTexture proxy);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding`  
- `Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+<>c`  
- `Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+<>c__DisplayClass12_0`  

