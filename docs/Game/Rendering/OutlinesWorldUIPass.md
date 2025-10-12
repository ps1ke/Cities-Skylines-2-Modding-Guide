# Game.Rendering.OutlinesWorldUIPass

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `UnityEngine.Rendering.HighDefinition.CustomPass`  
**Implements:** `UnityEngine.Rendering.HighDefinition.IVersionable<UnityEngine.Rendering.HighDefinition.CustomPass+Version>`  

## Fields

- `public UnityEngine.LayerMask m_OutlineLayer`  
- `public UnityEngine.Material m_FullscreenOutline`  
- `public System.Single m_MaxDistance`  
- `private UnityEngine.MaterialPropertyBlock m_OutlineProperties`  
- `private UnityEngine.Rendering.ShaderTagId[] m_ShaderTags`  
- `private UnityEngine.Rendering.RTHandle m_OutlineBuffer`  
- `private UnityEngine.Profiling.CustomSampler m_OutlinesSampler`  

## Properties

- `public UnityEngine.Rendering.RTHandle outlineBuffer { get }`  

## Constructors

- `public OutlinesWorldUIPass()`  

## Methods

- `protected virtual AggregateCullingParameters(UnityEngine.Rendering.ScriptableCullingParameters& cullingParameters, UnityEngine.Rendering.HighDefinition.HDCamera hdCamera) : System.Void`  
- `private CheckResource() : System.Void`  
- `protected virtual Cleanup() : System.Void`  
- `private static CreateOpaqueRendererListDesc(UnityEngine.Rendering.CullingResults cull, UnityEngine.Camera camera, UnityEngine.Rendering.ShaderTagId passName, UnityEngine.Rendering.PerObjectData rendererConfiguration = None, System.Nullable<UnityEngine.Rendering.RenderQueueRange> renderQueueRange = null, System.Nullable<UnityEngine.Rendering.RenderStateBlock> stateBlock = null, UnityEngine.Material overrideMaterial = null, System.Boolean excludeObjectMotionVectors = False) : UnityEngine.Rendering.RendererUtils.RendererListDesc`  
- `private CreateResources(UnityEngine.Rendering.MSAASamples msaaSamples) : System.Void`  
- `private static CreateTransparentRendererListDesc(UnityEngine.Rendering.CullingResults cull, UnityEngine.Camera camera, UnityEngine.Rendering.ShaderTagId passName, UnityEngine.Rendering.PerObjectData rendererConfiguration = None, System.Nullable<UnityEngine.Rendering.RenderQueueRange> renderQueueRange = null, System.Nullable<UnityEngine.Rendering.RenderStateBlock> stateBlock = null, UnityEngine.Material overrideMaterial = null, System.Boolean excludeObjectMotionVectors = False) : UnityEngine.Rendering.RendererUtils.RendererListDesc`  
- `private DrawAfterDRSObjects(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  
- `private DrawOutlineMeshes(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  
- `protected virtual Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  
- `private ReleaseResources() : System.Void`  
- `protected virtual Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

## Nested types

- `Game.Rendering.OutlinesWorldUIPass+ShaderID`  

