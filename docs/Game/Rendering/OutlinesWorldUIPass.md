# Game.Rendering.OutlinesWorldUIPass

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `UnityEngine.Rendering.HighDefinition.CustomPass`  
**Implements:** `UnityEngine.Rendering.HighDefinition.IVersionable<UnityEngine.Rendering.HighDefinition.CustomPass+Version>`  

## Code

```csharp
public class OutlinesWorldUIPass : UnityEngine.Rendering.HighDefinition.CustomPass, UnityEngine.Rendering.HighDefinition.IVersionable<UnityEngine.Rendering.HighDefinition.CustomPass+Version>
{
    public UnityEngine.LayerMask m_OutlineLayer;
    public UnityEngine.Material m_FullscreenOutline;
    public System.Single m_MaxDistance;
    private UnityEngine.MaterialPropertyBlock m_OutlineProperties;
    private UnityEngine.Rendering.ShaderTagId[] m_ShaderTags;
    private UnityEngine.Rendering.RTHandle m_OutlineBuffer;
    private UnityEngine.Profiling.CustomSampler m_OutlinesSampler;

    public UnityEngine.Rendering.RTHandle outlineBuffer { get; }

    public OutlinesWorldUIPass();

    protected virtual System.Void AggregateCullingParameters(UnityEngine.Rendering.ScriptableCullingParameters& cullingParameters, UnityEngine.Rendering.HighDefinition.HDCamera hdCamera);
    private System.Void CheckResource();
    protected virtual System.Void Cleanup();
    private static UnityEngine.Rendering.RendererUtils.RendererListDesc CreateOpaqueRendererListDesc(UnityEngine.Rendering.CullingResults cull, UnityEngine.Camera camera, UnityEngine.Rendering.ShaderTagId passName, UnityEngine.Rendering.PerObjectData rendererConfiguration, System.Nullable<UnityEngine.Rendering.RenderQueueRange> renderQueueRange, System.Nullable<UnityEngine.Rendering.RenderStateBlock> stateBlock, UnityEngine.Material overrideMaterial, System.Boolean excludeObjectMotionVectors);
    private System.Void CreateResources(UnityEngine.Rendering.MSAASamples msaaSamples);
    private static UnityEngine.Rendering.RendererUtils.RendererListDesc CreateTransparentRendererListDesc(UnityEngine.Rendering.CullingResults cull, UnityEngine.Camera camera, UnityEngine.Rendering.ShaderTagId passName, UnityEngine.Rendering.PerObjectData rendererConfiguration, System.Nullable<UnityEngine.Rendering.RenderQueueRange> renderQueueRange, System.Nullable<UnityEngine.Rendering.RenderStateBlock> stateBlock, UnityEngine.Material overrideMaterial, System.Boolean excludeObjectMotionVectors);
    private System.Void DrawAfterDRSObjects(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx);
    private System.Void DrawOutlineMeshes(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx);
    protected virtual System.Void Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx);
    private System.Void ReleaseResources();
    protected virtual System.Void Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd);
}
```


## Fields

- `public UnityEngine.LayerMask m_OutlineLayer`  

```csharp
public UnityEngine.LayerMask m_OutlineLayer;
```

- `public UnityEngine.Material m_FullscreenOutline`  

```csharp
public UnityEngine.Material m_FullscreenOutline;
```

- `public System.Single m_MaxDistance`  

```csharp
public System.Single m_MaxDistance;
```

- `private UnityEngine.MaterialPropertyBlock m_OutlineProperties`  

```csharp
private UnityEngine.MaterialPropertyBlock m_OutlineProperties;
```

- `private UnityEngine.Rendering.ShaderTagId[] m_ShaderTags`  

```csharp
private UnityEngine.Rendering.ShaderTagId[] m_ShaderTags;
```

- `private UnityEngine.Rendering.RTHandle m_OutlineBuffer`  

```csharp
private UnityEngine.Rendering.RTHandle m_OutlineBuffer;
```

- `private UnityEngine.Profiling.CustomSampler m_OutlinesSampler`  

```csharp
private UnityEngine.Profiling.CustomSampler m_OutlinesSampler;
```


## Properties

- `public UnityEngine.Rendering.RTHandle outlineBuffer { get }`  

```csharp
public UnityEngine.Rendering.RTHandle outlineBuffer { get; }
```


## Constructors

- `public OutlinesWorldUIPass()`  

```csharp
public OutlinesWorldUIPass();
```


## Methods

- `protected virtual AggregateCullingParameters(UnityEngine.Rendering.ScriptableCullingParameters& cullingParameters, UnityEngine.Rendering.HighDefinition.HDCamera hdCamera) : System.Void`  

```csharp
protected virtual System.Void AggregateCullingParameters(UnityEngine.Rendering.ScriptableCullingParameters& cullingParameters, UnityEngine.Rendering.HighDefinition.HDCamera hdCamera);
```

- `private CheckResource() : System.Void`  

```csharp
private System.Void CheckResource();
```

- `protected virtual Cleanup() : System.Void`  

```csharp
protected virtual System.Void Cleanup();
```

- `private static CreateOpaqueRendererListDesc(UnityEngine.Rendering.CullingResults cull, UnityEngine.Camera camera, UnityEngine.Rendering.ShaderTagId passName, UnityEngine.Rendering.PerObjectData rendererConfiguration = None, System.Nullable<UnityEngine.Rendering.RenderQueueRange> renderQueueRange = null, System.Nullable<UnityEngine.Rendering.RenderStateBlock> stateBlock = null, UnityEngine.Material overrideMaterial = null, System.Boolean excludeObjectMotionVectors = False) : UnityEngine.Rendering.RendererUtils.RendererListDesc`  

```csharp
private static UnityEngine.Rendering.RendererUtils.RendererListDesc CreateOpaqueRendererListDesc(UnityEngine.Rendering.CullingResults cull, UnityEngine.Camera camera, UnityEngine.Rendering.ShaderTagId passName, UnityEngine.Rendering.PerObjectData rendererConfiguration, System.Nullable<UnityEngine.Rendering.RenderQueueRange> renderQueueRange, System.Nullable<UnityEngine.Rendering.RenderStateBlock> stateBlock, UnityEngine.Material overrideMaterial, System.Boolean excludeObjectMotionVectors);
```

- `private CreateResources(UnityEngine.Rendering.MSAASamples msaaSamples) : System.Void`  

```csharp
private System.Void CreateResources(UnityEngine.Rendering.MSAASamples msaaSamples);
```

- `private static CreateTransparentRendererListDesc(UnityEngine.Rendering.CullingResults cull, UnityEngine.Camera camera, UnityEngine.Rendering.ShaderTagId passName, UnityEngine.Rendering.PerObjectData rendererConfiguration = None, System.Nullable<UnityEngine.Rendering.RenderQueueRange> renderQueueRange = null, System.Nullable<UnityEngine.Rendering.RenderStateBlock> stateBlock = null, UnityEngine.Material overrideMaterial = null, System.Boolean excludeObjectMotionVectors = False) : UnityEngine.Rendering.RendererUtils.RendererListDesc`  

```csharp
private static UnityEngine.Rendering.RendererUtils.RendererListDesc CreateTransparentRendererListDesc(UnityEngine.Rendering.CullingResults cull, UnityEngine.Camera camera, UnityEngine.Rendering.ShaderTagId passName, UnityEngine.Rendering.PerObjectData rendererConfiguration, System.Nullable<UnityEngine.Rendering.RenderQueueRange> renderQueueRange, System.Nullable<UnityEngine.Rendering.RenderStateBlock> stateBlock, UnityEngine.Material overrideMaterial, System.Boolean excludeObjectMotionVectors);
```

- `private DrawAfterDRSObjects(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  

```csharp
private System.Void DrawAfterDRSObjects(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx);
```

- `private DrawOutlineMeshes(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  

```csharp
private System.Void DrawOutlineMeshes(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx);
```

- `protected virtual Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  

```csharp
protected virtual System.Void Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx);
```

- `private ReleaseResources() : System.Void`  

```csharp
private System.Void ReleaseResources();
```

- `protected virtual Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
protected virtual System.Void Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd);
```


## Nested types

- `Game.Rendering.OutlinesWorldUIPass+ShaderID`  

