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
protected override void AggregateCullingParameters(ref ScriptableCullingParameters cullingParameters, HDCamera hdCamera)
	{
		cullingParameters.cullingMask |= (uint)(int)m_OutlineLayer;
	}
```

- `private CheckResource() : System.Void`  

```csharp
private void CheckResource()
	{
		MSAASamples mSAASamples = (SharedSettings.instance?.graphics?.GetQualitySetting<AntiAliasingQualitySettings>())?.outlinesMSAA ?? MSAASamples.None;
		if (mSAASamples < MSAASamples.None)
		{
			mSAASamples = MSAASamples.None;
		}
		if (mSAASamples > MSAASamples.MSAA8x)
		{
			mSAASamples = MSAASamples.MSAA8x;
		}
		if (m_OutlineBuffer == null || m_OutlineBuffer.rt == null || m_OutlineBuffer.rt.antiAliasing != (int)mSAASamples)
		{
			ReleaseResources();
			CreateResources(mSAASamples);
		}
	}
```

- `protected virtual Cleanup() : System.Void`  

```csharp
protected override void Cleanup()
	{
		ReleaseResources();
	}
```

- `private static CreateOpaqueRendererListDesc(UnityEngine.Rendering.CullingResults cull, UnityEngine.Camera camera, UnityEngine.Rendering.ShaderTagId passName, UnityEngine.Rendering.PerObjectData rendererConfiguration = None, System.Nullable<UnityEngine.Rendering.RenderQueueRange> renderQueueRange = null, System.Nullable<UnityEngine.Rendering.RenderStateBlock> stateBlock = null, UnityEngine.Material overrideMaterial = null, System.Boolean excludeObjectMotionVectors = False) : UnityEngine.Rendering.RendererUtils.RendererListDesc`  

```csharp
private static RendererListDesc CreateOpaqueRendererListDesc(CullingResults cull, Camera camera, ShaderTagId passName, PerObjectData rendererConfiguration = PerObjectData.None, RenderQueueRange? renderQueueRange = null, RenderStateBlock? stateBlock = null, Material overrideMaterial = null, bool excludeObjectMotionVectors = false)
	{
		RendererListDesc result = new RendererListDesc(passName, cull, camera);
		result.rendererConfiguration = rendererConfiguration;
		result.renderQueueRange = (renderQueueRange.HasValue ? renderQueueRange.Value : HDRenderQueue.k_RenderQueue_AllOpaque);
		result.sortingCriteria = SortingCriteria.CommonOpaque;
		result.stateBlock = stateBlock;
		result.overrideMaterial = overrideMaterial;
		result.excludeObjectMotionVectors = excludeObjectMotionVectors;
		return result;
	}
```

- `private CreateResources(UnityEngine.Rendering.MSAASamples msaaSamples) : System.Void`  

```csharp
private void CreateResources(MSAASamples msaaSamples)
	{
		m_OutlineBuffer = RTHandles.Alloc(Vector2.one, TextureXR.slices, DepthBits.None, GraphicsFormat.R8G8B8A8_SRGB, FilterMode.Point, TextureWrapMode.Repeat, TextureXR.dimension, enableRandomWrite: false, useMipMap: false, autoGenerateMips: true, isShadowMap: false, 1, 0f, msaaSamples, bindTextureMS: false, useDynamicScale: false, RenderTextureMemoryless.None, VRTextureUsage.None, "Outline Buffer");
	}
```

- `private static CreateTransparentRendererListDesc(UnityEngine.Rendering.CullingResults cull, UnityEngine.Camera camera, UnityEngine.Rendering.ShaderTagId passName, UnityEngine.Rendering.PerObjectData rendererConfiguration = None, System.Nullable<UnityEngine.Rendering.RenderQueueRange> renderQueueRange = null, System.Nullable<UnityEngine.Rendering.RenderStateBlock> stateBlock = null, UnityEngine.Material overrideMaterial = null, System.Boolean excludeObjectMotionVectors = False) : UnityEngine.Rendering.RendererUtils.RendererListDesc`  

```csharp
private static RendererListDesc CreateTransparentRendererListDesc(CullingResults cull, Camera camera, ShaderTagId passName, PerObjectData rendererConfiguration = PerObjectData.None, RenderQueueRange? renderQueueRange = null, RenderStateBlock? stateBlock = null, Material overrideMaterial = null, bool excludeObjectMotionVectors = false)
	{
		RendererListDesc result = new RendererListDesc(passName, cull, camera);
		result.rendererConfiguration = rendererConfiguration;
		result.renderQueueRange = (renderQueueRange.HasValue ? renderQueueRange.Value : HDRenderQueue.k_RenderQueue_AllTransparent);
		result.sortingCriteria = SortingCriteria.CommonTransparent | SortingCriteria.RendererPriority;
		result.stateBlock = stateBlock;
		result.overrideMaterial = overrideMaterial;
		result.excludeObjectMotionVectors = excludeObjectMotionVectors;
		return result;
	}
```

- `private DrawAfterDRSObjects(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  

```csharp
private void DrawAfterDRSObjects(CustomPassContext ctx)
	{
		float currentScale = DynamicResolutionHandler.instance.GetCurrentScale();
		ctx.cmd.SetGlobalFloat(ShaderID._DRSScale, currentScale);
		ctx.cmd.SetGlobalFloat(ShaderID._DRSScaleSquared, currentScale * currentScale);
		CoreUtils.DrawRendererList(ctx.renderContext, ctx.cmd, ctx.renderContext.CreateRendererList(CreateOpaqueRendererListDesc(ctx.cameraCullingResults, ctx.hdCamera.camera, HDShaderPassNames.s_ForwardOnlyName, PerObjectData.None, HDRenderQueue.k_RenderQueue_AfterDRSOpaque)));
		CoreUtils.DrawRendererList(ctx.renderContext, ctx.cmd, ctx.renderContext.CreateRendererList(CreateTransparentRendererListDesc(ctx.cameraCullingResults, ctx.hdCamera.camera, HDShaderPassNames.s_ForwardOnlyName, PerObjectData.None, HDRenderQueue.k_RenderQueue_AfterDRSTransparent)));
	}
```

- `private DrawOutlineMeshes(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  

```csharp
private void DrawOutlineMeshes(CustomPassContext ctx)
	{
		RendererListDesc rendererListDesc = new RendererListDesc(m_ShaderTags, ctx.cullingResults, ctx.hdCamera.camera);
		rendererListDesc.rendererConfiguration = PerObjectData.LightProbe | PerObjectData.LightProbeProxyVolume | PerObjectData.Lightmaps;
		rendererListDesc.renderQueueRange = RenderQueueRange.all;
		rendererListDesc.sortingCriteria = SortingCriteria.BackToFront;
		rendererListDesc.excludeObjectMotionVectors = false;
		rendererListDesc.layerMask = m_OutlineLayer;
		RendererListDesc desc = rendererListDesc;
		ctx.cmd.EnableShaderKeyword("SHADERPASS_OUTLINES");
		ctx.cmd.SetGlobalFloat(ShaderID._Outlines_MaxDistance, m_MaxDistance);
		CoreUtils.SetRenderTarget(ctx.cmd, m_OutlineBuffer, ClearFlag.Color);
		CoreUtils.DrawRendererList(ctx.renderContext, ctx.cmd, ctx.renderContext.CreateRendererList(desc));
		ctx.cmd.DisableShaderKeyword("SHADERPASS_OUTLINES");
	}
```

- `protected virtual Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  

```csharp
protected override void Execute(CustomPassContext ctx)
	{
		CheckResource();
		using (new ProfilingScope(ctx.cmd, new ProfilingSampler("Outlines and World UI Pass")))
		{
			DrawOutlineMeshes(ctx);
			CoreUtils.SetRenderTarget(ctx.cmd, ctx.cameraColorBuffer);
			DrawAfterDRSObjects(ctx);
			m_OutlineProperties.SetTexture(ShaderID._OutlineBuffer, m_OutlineBuffer);
			CoreUtils.DrawFullScreen(ctx.cmd, m_FullscreenOutline, m_OutlineProperties);
		}
	}
```

- `private ReleaseResources() : System.Void`  

```csharp
private void ReleaseResources()
	{
		if (m_OutlineBuffer != null)
		{
			m_OutlineBuffer.Release();
		}
	}
```

- `protected virtual Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
protected override void Setup(ScriptableRenderContext renderContext, CommandBuffer cmd)
	{
		m_OutlinesSampler = CustomSampler.Create("Outlines pass");
		m_OutlineProperties = new MaterialPropertyBlock();
		m_ShaderTags = new ShaderTagId[3]
		{
			new ShaderTagId("Forward"),
			new ShaderTagId("ForwardOnly"),
			new ShaderTagId("SRPDefaultUnlit")
		};
	}
```


## Nested types

- `Game.Rendering.OutlinesWorldUIPass+ShaderID`  

