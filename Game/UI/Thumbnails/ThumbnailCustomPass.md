# Game.UI.Thumbnails.ThumbnailCustomPass

**Assembly:** `Game`  
**Namespace:** `Game.UI.Thumbnails`  

**Type:** class public  

**Base:** `UnityEngine.Rendering.HighDefinition.CustomPass`  
**Implements:** `UnityEngine.Rendering.HighDefinition.IVersionable<UnityEngine.Rendering.HighDefinition.CustomPass+Version>`  

## Code

```csharp
public class ThumbnailCustomPass : UnityEngine.Rendering.HighDefinition.CustomPass, UnityEngine.Rendering.HighDefinition.IVersionable<UnityEngine.Rendering.HighDefinition.CustomPass+Version>
{
    public UnityEngine.LayerMask m_ThumbnailLayer;
    private UnityEngine.Rendering.ShaderTagId[] m_ShaderTags;
    private UnityEngine.Rendering.RTHandle m_ThumbnailBuffer;
    private UnityEngine.Rendering.RTHandle m_ThumbnailDepthBuffer;
    private System.Boolean m_CanRender;

    public ThumbnailCustomPass();

    public System.Void AllocateRTHandles(System.Int32 width, System.Int32 height);
    protected virtual System.Void Cleanup();
    protected virtual System.Void Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx);
    public UnityEngine.RenderTexture GetBuffer();
    public System.Void Release();
    protected virtual System.Void Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd);
}
```


## Fields

- `public UnityEngine.LayerMask m_ThumbnailLayer`  

```csharp
public UnityEngine.LayerMask m_ThumbnailLayer;
```

- `private UnityEngine.Rendering.ShaderTagId[] m_ShaderTags`  

```csharp
private UnityEngine.Rendering.ShaderTagId[] m_ShaderTags;
```

- `private UnityEngine.Rendering.RTHandle m_ThumbnailBuffer`  

```csharp
private UnityEngine.Rendering.RTHandle m_ThumbnailBuffer;
```

- `private UnityEngine.Rendering.RTHandle m_ThumbnailDepthBuffer`  

```csharp
private UnityEngine.Rendering.RTHandle m_ThumbnailDepthBuffer;
```

- `private System.Boolean m_CanRender`  

```csharp
private System.Boolean m_CanRender;
```


## Constructors

- `public ThumbnailCustomPass()`  

```csharp
public ThumbnailCustomPass();
```


## Methods

- `public AllocateRTHandles(System.Int32 width, System.Int32 height) : System.Void`  

```csharp
public void AllocateRTHandles(int width, int height)
	{
		if (m_ThumbnailBuffer != null && m_ThumbnailBuffer.rt != null && (m_ThumbnailBuffer.rt.width != width || m_ThumbnailBuffer.rt.height != height))
		{
			m_ThumbnailBuffer.Release();
			m_ThumbnailBuffer = null;
			if (m_ThumbnailDepthBuffer != null)
			{
				m_ThumbnailDepthBuffer.Release();
				m_ThumbnailDepthBuffer = null;
			}
		}
		QualitySettings.GetRenderPipelineAssetAt(QualitySettings.GetQualityLevel());
		if (m_ThumbnailBuffer == null)
		{
			m_ThumbnailBuffer = RTHandles.Alloc(width, height, 1, DepthBits.None, GraphicsFormat.R8G8B8A8_UNorm, FilterMode.Point, TextureWrapMode.Repeat, TextureDimension.Tex2D, enableRandomWrite: false, useMipMap: false, autoGenerateMips: true, isShadowMap: false, 1, 0f, MSAASamples.None, bindTextureMS: false, useDynamicScale: true, RenderTextureMemoryless.None, VRTextureUsage.None, "Thumbnail Color Buffer");
		}
		if (m_ThumbnailDepthBuffer == null)
		{
			m_ThumbnailDepthBuffer = RTHandles.Alloc(width, height, 1, DepthBits.Depth16, GraphicsFormat.R16_UInt, FilterMode.Point, TextureWrapMode.Repeat, TextureXR.dimension, enableRandomWrite: false, useMipMap: false, autoGenerateMips: true, isShadowMap: false, 1, 0f, MSAASamples.None, bindTextureMS: false, useDynamicScale: false, RenderTextureMemoryless.None, VRTextureUsage.None, "Thumbnail Depth Buffer");
		}
		m_CanRender = true;
	}
```

- `protected virtual Cleanup() : System.Void`  

```csharp
protected override void Cleanup()
	{
		Release();
	}
```

- `protected virtual Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  

```csharp
protected override void Execute(CustomPassContext ctx)
	{
		if (m_CanRender)
		{
			RendererListDesc rendererListDesc = new RendererListDesc(m_ShaderTags, ctx.cullingResults, ctx.hdCamera.camera);
			rendererListDesc.rendererConfiguration = PerObjectData.LightProbe | PerObjectData.LightProbeProxyVolume | PerObjectData.Lightmaps;
			rendererListDesc.renderQueueRange = RenderQueueRange.all;
			rendererListDesc.sortingCriteria = SortingCriteria.BackToFront;
			rendererListDesc.excludeObjectMotionVectors = true;
			rendererListDesc.layerMask = m_ThumbnailLayer;
			rendererListDesc.stateBlock = new RenderStateBlock(RenderStateMask.Depth | RenderStateMask.Stencil)
			{
				depthState = new DepthState(writeEnabled: true, CompareFunction.LessEqual)
			};
			RendererListDesc desc = rendererListDesc;
			int globalInt = Shader.GetGlobalInt("colossal_InfoviewOn");
			ctx.cmd.DisableShaderKeyword("INFOVIEW_ON");
			ctx.cmd.SetGlobalInt("colossal_InfoviewOn", 0);
			CoreUtils.SetRenderTarget(ctx.cmd, m_ThumbnailBuffer, m_ThumbnailDepthBuffer, ClearFlag.All);
			CoreUtils.DrawRendererList(ctx.renderContext, ctx.cmd, ctx.renderContext.CreateRendererList(desc));
			ctx.cmd.SetGlobalInt("colossal_InfoviewOn", globalInt);
		}
	}
```

- `public GetBuffer() : UnityEngine.RenderTexture`  

```csharp
public RenderTexture GetBuffer()
	{
		return m_ThumbnailBuffer.rt;
	}
```

- `public Release() : System.Void`  

```csharp
public void Release()
	{
		if (m_ThumbnailBuffer != null)
		{
			m_ThumbnailBuffer.Release();
		}
		if (m_ThumbnailDepthBuffer != null)
		{
			m_ThumbnailDepthBuffer.Release();
		}
		m_CanRender = false;
	}
```

- `protected virtual Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
protected override void Setup(ScriptableRenderContext renderContext, CommandBuffer cmd)
	{
		m_ShaderTags = new ShaderTagId[3]
		{
			new ShaderTagId("Forward"),
			new ShaderTagId("ForwardOnly"),
			new ShaderTagId("SRPDefaultUnlit")
		};
	}
```


