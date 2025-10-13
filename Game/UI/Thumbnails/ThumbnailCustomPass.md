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
public System.Void AllocateRTHandles(System.Int32 width, System.Int32 height);
```

- `protected virtual Cleanup() : System.Void`  

```csharp
protected virtual System.Void Cleanup();
```

- `protected virtual Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  

```csharp
protected virtual System.Void Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx);
```

- `public GetBuffer() : UnityEngine.RenderTexture`  

```csharp
public UnityEngine.RenderTexture GetBuffer();
```

- `public Release() : System.Void`  

```csharp
public System.Void Release();
```

- `protected virtual Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
protected virtual System.Void Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd);
```


