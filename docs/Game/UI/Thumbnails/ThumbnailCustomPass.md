# Game.UI.Thumbnails.ThumbnailCustomPass

**Assembly:** `Game`  
**Namespace:** `Game.UI.Thumbnails`  

**Type:** class public  

**Base:** `UnityEngine.Rendering.HighDefinition.CustomPass`  
**Implements:** `UnityEngine.Rendering.HighDefinition.IVersionable<UnityEngine.Rendering.HighDefinition.CustomPass+Version>`  

## Fields

- `public UnityEngine.LayerMask m_ThumbnailLayer`  
- `private UnityEngine.Rendering.ShaderTagId[] m_ShaderTags`  
- `private UnityEngine.Rendering.RTHandle m_ThumbnailBuffer`  
- `private UnityEngine.Rendering.RTHandle m_ThumbnailDepthBuffer`  
- `private System.Boolean m_CanRender`  

## Constructors

- `public ThumbnailCustomPass()`  

## Methods

- `public AllocateRTHandles(System.Int32 width, System.Int32 height) : System.Void`  
- `protected virtual Cleanup() : System.Void`  
- `protected virtual Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  
- `public GetBuffer() : UnityEngine.RenderTexture`  
- `public Release() : System.Void`  
- `protected virtual Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

