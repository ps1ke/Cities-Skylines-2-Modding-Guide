# Game.Rendering.UndergroundPass

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `UnityEngine.Rendering.HighDefinition.CustomPass`  
**Implements:** `UnityEngine.Rendering.HighDefinition.IVersionable<UnityEngine.Rendering.HighDefinition.CustomPass+Version>`  

## Fields

- `private Game.Rendering.UndergroundViewSystem m_UndergroundViewSystem`  
- `private UnityEngine.Rendering.ShaderTagId[] m_ShaderTags`  
- `private UnityEngine.ComputeShader m_ComputeShader`  
- `private UnityEngine.Material m_ContourMaterial`  
- `private System.Int32 m_TunnelMask`  
- `private System.Int32 m_MarkerMask`  
- `private System.Int32 m_PipelineMask`  
- `private System.Int32 m_SubPipelineMask`  
- `private System.Int32 m_CameraColorBuffer`  
- `private System.Int32 m_UndergroundColorBuffer`  
- `private System.Int32 m_UndergroundDepthBuffer`  
- `private System.Int32 m_UndergroundFlags`  
- `private System.Int32 m_UndergroundPassKernel`  
- `private System.Int32 m_ContourPassKernel`  

## Constructors

- `public UndergroundPass()`  

## Methods

- `protected virtual AggregateCullingParameters(UnityEngine.Rendering.ScriptableCullingParameters& cullingParameters, UnityEngine.Rendering.HighDefinition.HDCamera hdCamera) : System.Void`  
- `protected virtual Cleanup() : System.Void`  
- `protected virtual Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  
- `protected virtual Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

## Nested types

- `Game.Rendering.UndergroundPass+ComputeFlags`  

