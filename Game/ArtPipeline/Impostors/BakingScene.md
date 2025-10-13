# Game.ArtPipeline.Impostors.BakingScene

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Impostors`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class BakingScene : System.IDisposable
{
    private UnityEngine.GameObject _RootGameObject;
    private UnityEngine.Camera _Camera;
    private System.Int32 _LayerIndex;
    private System.Int32 _RendererCount;
    private UnityEngine.MaterialPropertyBlock m_BakingPropertyBlock;
    private static readonly System.Int32 m_ImpostorSizeId;
    private static readonly UnityEngine.Matrix4x4 m_ScaleMatrix;

    public UnityEngine.Renderer[] renderers { get; }

    public BakingScene(UnityEngine.GameObject rootGameObject, UnityEngine.Renderer[] renderers, UnityEngine.Matrix4x4 matrix, System.Int32 layerIndex);

    private static System.Void ApplyKeywords(UnityEngine.Material material, System.String[] keywords);
    private System.Void CopyGameObject(UnityEngine.GameObject rootGameObject, UnityEngine.Transform r);
    public System.Void Dispose();
    private System.Void FillDebugData(UnityEngine.Rendering.HighDefinition.AOVRequest& debug, Game.ArtPipeline.Impostors.RenderRequestMode m_RequestMode);
    private UnityEngine.Material GetBakingMaterial(UnityEngine.Material sourceMaterial, Game.ArtPipeline.Impostors.BakingScene+MaterialBinding materialBinding, UnityEngine.MaterialPropertyBlock& bakingPropertyBlock);
    private System.Void ProcessRenderRequests(UnityEngine.Camera camera, System.Collections.Generic.List<Game.ArtPipeline.Impostors.RenderRequest> renderRequests);
    public System.Void Render(Unity.Mathematics.float3 from, Unity.Mathematics.float3 to, System.Single nearClipPlane, System.Single farClipPlane, System.Single orthographicSize, System.Collections.Generic.List<Game.ArtPipeline.Impostors.RenderRequest> request);
    public System.Void RenderMultiView(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] worldMatrices, System.Int32 viewCount, System.Single nearClipPlane, System.Single farClipPlane, System.Single orthographicSize, System.Collections.Generic.Dictionary<UnityEngine.Shader, Game.ArtPipeline.Impostors.BakingScene+MaterialBinding> bakingMaterials);
    private System.Void RenderMultiViewGameObject(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] viewMatrices, UnityEngine.Matrix4x4[] viewsWorldMatrices, System.Int32 viewCount, UnityEngine.GameObject gameObject, System.Collections.Generic.Dictionary<UnityEngine.Shader, Game.ArtPipeline.Impostors.BakingScene+MaterialBinding> bakingMaterials, System.Single farClipPlane);
    private System.Void RenderMultiViewMesh(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] viewsWorldMatrices, System.Int32 viewCount, UnityEngine.Mesh mesh, UnityEngine.Material material, System.Int32 subMeshIndex, System.Collections.Generic.Dictionary<UnityEngine.Shader, Game.ArtPipeline.Impostors.BakingScene+MaterialBinding> bakingMaterials, System.Single farClipPlane, UnityEngine.Matrix4x4 objectWorldMatrix);
    public System.Void SetProxyTarget(UnityEngine.RenderTexture proxy);
}
```


## Fields

- `private UnityEngine.GameObject _RootGameObject`  

```csharp
private UnityEngine.GameObject _RootGameObject;
```

- `private UnityEngine.Camera _Camera`  

```csharp
private UnityEngine.Camera _Camera;
```

- `private System.Int32 _LayerIndex`  

```csharp
private System.Int32 _LayerIndex;
```

- `private System.Int32 _RendererCount`  

```csharp
private System.Int32 _RendererCount;
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

- `private FillDebugData(UnityEngine.Rendering.HighDefinition.AOVRequest& debug, Game.ArtPipeline.Impostors.RenderRequestMode m_RequestMode) : System.Void`  

```csharp
private System.Void FillDebugData(UnityEngine.Rendering.HighDefinition.AOVRequest& debug, Game.ArtPipeline.Impostors.RenderRequestMode m_RequestMode);
```

- `private GetBakingMaterial(UnityEngine.Material sourceMaterial, Game.ArtPipeline.Impostors.BakingScene+MaterialBinding materialBinding, UnityEngine.MaterialPropertyBlock& bakingPropertyBlock) : UnityEngine.Material`  

```csharp
private UnityEngine.Material GetBakingMaterial(UnityEngine.Material sourceMaterial, Game.ArtPipeline.Impostors.BakingScene+MaterialBinding materialBinding, UnityEngine.MaterialPropertyBlock& bakingPropertyBlock);
```

- `private ProcessRenderRequests(UnityEngine.Camera camera, System.Collections.Generic.List<Game.ArtPipeline.Impostors.RenderRequest> renderRequests) : System.Void`  

```csharp
private System.Void ProcessRenderRequests(UnityEngine.Camera camera, System.Collections.Generic.List<Game.ArtPipeline.Impostors.RenderRequest> renderRequests);
```

- `public Render(Unity.Mathematics.float3 from, Unity.Mathematics.float3 to, System.Single nearClipPlane, System.Single farClipPlane, System.Single orthographicSize, System.Collections.Generic.List<Game.ArtPipeline.Impostors.RenderRequest> request) : System.Void`  

```csharp
public System.Void Render(Unity.Mathematics.float3 from, Unity.Mathematics.float3 to, System.Single nearClipPlane, System.Single farClipPlane, System.Single orthographicSize, System.Collections.Generic.List<Game.ArtPipeline.Impostors.RenderRequest> request);
```

- `public RenderMultiView(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] worldMatrices, System.Int32 viewCount, System.Single nearClipPlane, System.Single farClipPlane, System.Single orthographicSize, System.Collections.Generic.Dictionary<UnityEngine.Shader, Game.ArtPipeline.Impostors.BakingScene+MaterialBinding> bakingMaterials) : System.Void`  

```csharp
public System.Void RenderMultiView(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] worldMatrices, System.Int32 viewCount, System.Single nearClipPlane, System.Single farClipPlane, System.Single orthographicSize, System.Collections.Generic.Dictionary<UnityEngine.Shader, Game.ArtPipeline.Impostors.BakingScene+MaterialBinding> bakingMaterials);
```

- `private RenderMultiViewGameObject(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] viewMatrices, UnityEngine.Matrix4x4[] viewsWorldMatrices, System.Int32 viewCount, UnityEngine.GameObject gameObject, System.Collections.Generic.Dictionary<UnityEngine.Shader, Game.ArtPipeline.Impostors.BakingScene+MaterialBinding> bakingMaterials, System.Single farClipPlane) : System.Void`  

```csharp
private System.Void RenderMultiViewGameObject(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] viewMatrices, UnityEngine.Matrix4x4[] viewsWorldMatrices, System.Int32 viewCount, UnityEngine.GameObject gameObject, System.Collections.Generic.Dictionary<UnityEngine.Shader, Game.ArtPipeline.Impostors.BakingScene+MaterialBinding> bakingMaterials, System.Single farClipPlane);
```

- `private RenderMultiViewMesh(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] viewsWorldMatrices, System.Int32 viewCount, UnityEngine.Mesh mesh, UnityEngine.Material material, System.Int32 subMeshIndex, System.Collections.Generic.Dictionary<UnityEngine.Shader, Game.ArtPipeline.Impostors.BakingScene+MaterialBinding> bakingMaterials, System.Single farClipPlane, UnityEngine.Matrix4x4 objectWorldMatrix) : System.Void`  

```csharp
private System.Void RenderMultiViewMesh(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.Matrix4x4[] viewsWorldMatrices, System.Int32 viewCount, UnityEngine.Mesh mesh, UnityEngine.Material material, System.Int32 subMeshIndex, System.Collections.Generic.Dictionary<UnityEngine.Shader, Game.ArtPipeline.Impostors.BakingScene+MaterialBinding> bakingMaterials, System.Single farClipPlane, UnityEngine.Matrix4x4 objectWorldMatrix);
```

- `public SetProxyTarget(UnityEngine.RenderTexture proxy) : System.Void`  

```csharp
public System.Void SetProxyTarget(UnityEngine.RenderTexture proxy);
```


## Nested types

- `Game.ArtPipeline.Impostors.BakingScene+MaterialBinding`  
- `Game.ArtPipeline.Impostors.BakingScene+<>c`  
- `Game.ArtPipeline.Impostors.BakingScene+<>c__DisplayClass13_0`  

