# Game.Rendering.UndergroundPass

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `UnityEngine.Rendering.HighDefinition.CustomPass`  
**Implements:** `UnityEngine.Rendering.HighDefinition.IVersionable<UnityEngine.Rendering.HighDefinition.CustomPass+Version>`  

## Code

```csharp
public class UndergroundPass : UnityEngine.Rendering.HighDefinition.CustomPass, UnityEngine.Rendering.HighDefinition.IVersionable<UnityEngine.Rendering.HighDefinition.CustomPass+Version>
{
    private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
    private UnityEngine.Rendering.ShaderTagId[] m_ShaderTags;
    private UnityEngine.ComputeShader m_ComputeShader;
    private UnityEngine.Material m_ContourMaterial;
    private System.Int32 m_TunnelMask;
    private System.Int32 m_MarkerMask;
    private System.Int32 m_PipelineMask;
    private System.Int32 m_SubPipelineMask;
    private System.Int32 m_CameraColorBuffer;
    private System.Int32 m_UndergroundColorBuffer;
    private System.Int32 m_UndergroundDepthBuffer;
    private System.Int32 m_UndergroundFlags;
    private System.Int32 m_UndergroundPassKernel;
    private System.Int32 m_ContourPassKernel;

    public UndergroundPass();

    protected virtual System.Void AggregateCullingParameters(UnityEngine.Rendering.ScriptableCullingParameters& cullingParameters, UnityEngine.Rendering.HighDefinition.HDCamera hdCamera);
    protected virtual System.Void Cleanup();
    protected virtual System.Void Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx);
    protected virtual System.Void Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd);
}
```


## Fields

- `private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem`  

```csharp
private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem;
```

- `private UnityEngine.Rendering.ShaderTagId[] m_ShaderTags`  

```csharp
private UnityEngine.Rendering.ShaderTagId[] m_ShaderTags;
```

- `private UnityEngine.ComputeShader m_ComputeShader`  

```csharp
private UnityEngine.ComputeShader m_ComputeShader;
```

- `private UnityEngine.Material m_ContourMaterial`  

```csharp
private UnityEngine.Material m_ContourMaterial;
```

- `private System.Int32 m_TunnelMask`  

```csharp
private System.Int32 m_TunnelMask;
```

- `private System.Int32 m_MarkerMask`  

```csharp
private System.Int32 m_MarkerMask;
```

- `private System.Int32 m_PipelineMask`  

```csharp
private System.Int32 m_PipelineMask;
```

- `private System.Int32 m_SubPipelineMask`  

```csharp
private System.Int32 m_SubPipelineMask;
```

- `private System.Int32 m_CameraColorBuffer`  

```csharp
private System.Int32 m_CameraColorBuffer;
```

- `private System.Int32 m_UndergroundColorBuffer`  

```csharp
private System.Int32 m_UndergroundColorBuffer;
```

- `private System.Int32 m_UndergroundDepthBuffer`  

```csharp
private System.Int32 m_UndergroundDepthBuffer;
```

- `private System.Int32 m_UndergroundFlags`  

```csharp
private System.Int32 m_UndergroundFlags;
```

- `private System.Int32 m_UndergroundPassKernel`  

```csharp
private System.Int32 m_UndergroundPassKernel;
```

- `private System.Int32 m_ContourPassKernel`  

```csharp
private System.Int32 m_ContourPassKernel;
```


## Constructors

- `public UndergroundPass()`  

```csharp
public UndergroundPass();
```


## Methods

- `protected virtual AggregateCullingParameters(UnityEngine.Rendering.ScriptableCullingParameters& cullingParameters, UnityEngine.Rendering.HighDefinition.HDCamera hdCamera) : System.Void`  

```csharp
protected override void AggregateCullingParameters(ref ScriptableCullingParameters cullingParameters, HDCamera hdCamera)
	{
		if (m_UndergroundViewSystem == null)
		{
			return;
		}
		if (m_UndergroundViewSystem.tunnelsOn)
		{
			cullingParameters.cullingMask |= (uint)m_TunnelMask;
			if (m_UndergroundViewSystem.markersOn)
			{
				cullingParameters.cullingMask |= (uint)m_MarkerMask;
			}
		}
		if (m_UndergroundViewSystem.pipelinesOn)
		{
			cullingParameters.cullingMask |= (uint)m_PipelineMask;
		}
		if (m_UndergroundViewSystem.subPipelinesOn)
		{
			cullingParameters.cullingMask |= (uint)m_SubPipelineMask;
		}
	}
```

- `protected virtual Cleanup() : System.Void`  

```csharp
protected override void Cleanup()
	{
	}
```

- `protected virtual Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  

```csharp
protected override void Execute(CustomPassContext ctx)
	{
		if (m_UndergroundViewSystem == null || (!m_UndergroundViewSystem.tunnelsOn && !m_UndergroundViewSystem.pipelinesOn && !m_UndergroundViewSystem.subPipelinesOn && !m_UndergroundViewSystem.contourLinesOn))
		{
			return;
		}
		ComputeFlags computeFlags = (m_UndergroundViewSystem.undergroundOn ? ((ComputeFlags)5) : ((ComputeFlags)0));
		if (m_UndergroundViewSystem.contourLinesOn)
		{
			TerrainSurface validSurface = TerrainSurface.GetValidSurface();
			CBTSubdivisionTerrainEngine cbt = validSurface.cbt;
			if (cbt != null && cbt.IsValid && validSurface.material != null)
			{
				CoreUtils.SetRenderTarget(ctx.cmd, ctx.customColorBuffer.Value, ctx.customDepthBuffer.Value, ClearFlag.All);
				HDRenderPipeline.TerrainRenderingParameters parameters = HDRenderPipeline.PrepareTerrainRenderingParameters(ctx.hdCamera.camera.transform.position, validSurface);
				m_ContourMaterial.CopyPropertiesFromMaterial(validSurface.material);
				parameters.terrainMaterial = m_ContourMaterial;
				HDRenderPipeline.RenderTerrainSurfaceCBT(ctx.cmd, 0, validSurface, ctx.hdCamera.camera, parameters);
				Texture texture = ctx.cameraColorBuffer;
				ctx.cmd.SetComputeTextureParam(m_ComputeShader, m_ContourPassKernel, m_CameraColorBuffer, texture);
				ctx.cmd.SetComputeTextureParam(m_ComputeShader, m_ContourPassKernel, m_UndergroundColorBuffer, ctx.customColorBuffer.Value);
				ctx.cmd.SetComputeTextureParam(m_ComputeShader, m_ContourPassKernel, m_UndergroundDepthBuffer, ctx.customDepthBuffer.Value);
				ctx.cmd.DispatchCompute(m_ComputeShader, m_ContourPassKernel, texture.width + 15 >> 4, texture.height + 15 >> 4, 1);
			}
		}
		if (m_UndergroundViewSystem.tunnelsOn)
		{
			RenderStateBlock value = new RenderStateBlock(RenderStateMask.Depth);
			value.depthState = DepthState.defaultValue;
			value.stencilState = StencilState.defaultValue;
			RendererListDesc rendererListDesc = new RendererListDesc(m_ShaderTags, ctx.cullingResults, ctx.hdCamera.camera);
			rendererListDesc.rendererConfiguration = PerObjectData.LightProbe | PerObjectData.LightProbeProxyVolume | PerObjectData.Lightmaps;
			rendererListDesc.renderQueueRange = RenderQueueRange.all;
			rendererListDesc.sortingCriteria = SortingCriteria.CommonOpaque;
			rendererListDesc.excludeObjectMotionVectors = false;
			rendererListDesc.stateBlock = value;
			rendererListDesc.layerMask = m_TunnelMask;
			RendererListDesc desc = rendererListDesc;
			if (m_UndergroundViewSystem.markersOn)
			{
				desc.layerMask |= m_MarkerMask;
			}
			if (m_UndergroundViewSystem.pipelinesOn && !m_UndergroundViewSystem.subPipelinesOn)
			{
				desc.layerMask |= m_PipelineMask;
			}
			ctx.cmd.EnableShaderKeyword("DECALS_OFF");
			ctx.cmd.DisableShaderKeyword("DECALS_4RT");
			CoreUtils.SetRenderTarget(ctx.cmd, ctx.customColorBuffer.Value, ctx.customDepthBuffer.Value, ClearFlag.All);
			CoreUtils.DrawRendererList(ctx.renderContext, ctx.cmd, ctx.renderContext.CreateRendererList(desc));
			ctx.cmd.EnableShaderKeyword("DECALS_4RT");
			ctx.cmd.DisableShaderKeyword("DECALS_OFF");
			Texture texture2 = ctx.cameraColorBuffer;
			ctx.cmd.SetComputeTextureParam(m_ComputeShader, m_UndergroundPassKernel, m_CameraColorBuffer, texture2);
			ctx.cmd.SetComputeTextureParam(m_ComputeShader, m_UndergroundPassKernel, m_UndergroundColorBuffer, ctx.customColorBuffer.Value);
			ctx.cmd.SetComputeTextureParam(m_ComputeShader, m_UndergroundPassKernel, m_UndergroundDepthBuffer, ctx.customDepthBuffer.Value);
			ctx.cmd.SetComputeIntParam(m_ComputeShader, m_UndergroundFlags, (int)(computeFlags | ComputeFlags.FadeNearSurface));
			ctx.cmd.DispatchCompute(m_ComputeShader, m_UndergroundPassKernel, texture2.width + 15 >> 4, texture2.height + 15 >> 4, 1);
			computeFlags &= (ComputeFlags)(-2);
		}
		if (m_UndergroundViewSystem.subPipelinesOn || (m_UndergroundViewSystem.pipelinesOn && !m_UndergroundViewSystem.tunnelsOn))
		{
			RenderStateBlock value2 = new RenderStateBlock(RenderStateMask.Depth);
			value2.depthState = DepthState.defaultValue;
			value2.stencilState = StencilState.defaultValue;
			RendererListDesc rendererListDesc = new RendererListDesc(m_ShaderTags, ctx.cullingResults, ctx.hdCamera.camera);
			rendererListDesc.rendererConfiguration = PerObjectData.LightProbe | PerObjectData.LightProbeProxyVolume | PerObjectData.Lightmaps;
			rendererListDesc.renderQueueRange = RenderQueueRange.all;
			rendererListDesc.sortingCriteria = SortingCriteria.CommonOpaque;
			rendererListDesc.excludeObjectMotionVectors = false;
			rendererListDesc.stateBlock = value2;
			rendererListDesc.layerMask = (m_UndergroundViewSystem.pipelinesOn ? (m_PipelineMask | m_SubPipelineMask) : m_SubPipelineMask);
			RendererListDesc desc2 = rendererListDesc;
			if (m_UndergroundViewSystem.pipelinesOn)
			{
				desc2.layerMask |= m_PipelineMask;
			}
			if (m_UndergroundViewSystem.subPipelinesOn)
			{
				desc2.layerMask |= m_SubPipelineMask;
			}
			ctx.cmd.EnableShaderKeyword("DECALS_OFF");
			ctx.cmd.DisableShaderKeyword("DECALS_4RT");
			CoreUtils.SetRenderTarget(ctx.cmd, ctx.customColorBuffer.Value, ctx.customDepthBuffer.Value, ClearFlag.All);
			CoreUtils.DrawRendererList(ctx.renderContext, ctx.cmd, ctx.renderContext.CreateRendererList(desc2));
			ctx.cmd.EnableShaderKeyword("DECALS_4RT");
			ctx.cmd.DisableShaderKeyword("DECALS_OFF");
			Texture texture3 = ctx.cameraColorBuffer;
			ctx.cmd.SetComputeTextureParam(m_ComputeShader, m_UndergroundPassKernel, m_CameraColorBuffer, texture3);
			ctx.cmd.SetComputeTextureParam(m_ComputeShader, m_UndergroundPassKernel, m_UndergroundColorBuffer, ctx.customColorBuffer.Value);
			ctx.cmd.SetComputeTextureParam(m_ComputeShader, m_UndergroundPassKernel, m_UndergroundDepthBuffer, ctx.customDepthBuffer.Value);
			ctx.cmd.SetComputeIntParam(m_ComputeShader, m_UndergroundFlags, (int)computeFlags);
			ctx.cmd.DispatchCompute(m_ComputeShader, m_UndergroundPassKernel, texture3.width + 15 >> 4, texture3.height + 15 >> 4, 1);
		}
	}
```

- `protected virtual Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
protected override void Setup(ScriptableRenderContext renderContext, CommandBuffer cmd)
	{
		foreach (World item in World.All)
		{
			if (item.IsCreated && (item.Flags & WorldFlags.Simulation) == WorldFlags.Simulation)
			{
				m_UndergroundViewSystem = item.GetExistingSystemManaged<UndergroundViewSystem>();
				if (m_UndergroundViewSystem != null)
				{
					break;
				}
			}
		}
		m_ShaderTags = new ShaderTagId[3]
		{
			HDShaderPassNames.s_ForwardName,
			HDShaderPassNames.s_ForwardOnlyName,
			HDShaderPassNames.s_SRPDefaultUnlitName
		};
		m_ComputeShader = Resources.Load<ComputeShader>("UndergroundPass");
		m_ContourMaterial = new Material(Resources.Load<Shader>("TerrainHeights"));
		m_TunnelMask = (1 << LayerMask.NameToLayer("Tunnel")) | (1 << LayerMask.NameToLayer("Moving"));
		m_MarkerMask = 1 << LayerMask.NameToLayer("Marker");
		m_PipelineMask = 1 << LayerMask.NameToLayer("Pipeline");
		m_SubPipelineMask = 1 << LayerMask.NameToLayer("SubPipeline");
		m_CameraColorBuffer = Shader.PropertyToID("_CameraColorBuffer");
		m_UndergroundColorBuffer = Shader.PropertyToID("_UndergroundColorBuffer");
		m_UndergroundDepthBuffer = Shader.PropertyToID("_UndergroundDepthBuffer");
		m_UndergroundFlags = Shader.PropertyToID("_UndergroundFlags");
		m_UndergroundPassKernel = m_ComputeShader.FindKernel("UndergroundPass");
		m_ContourPassKernel = m_ComputeShader.FindKernel("ContourPass");
	}
```


## Nested types

- `Game.Rendering.UndergroundPass+ComputeFlags`  

