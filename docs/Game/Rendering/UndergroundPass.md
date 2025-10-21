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
protected virtual System.Void AggregateCullingParameters(UnityEngine.Rendering.ScriptableCullingParameters& cullingParameters, UnityEngine.Rendering.HighDefinition.HDCamera hdCamera);
```

- `protected virtual Cleanup() : System.Void`  

```csharp
protected virtual System.Void Cleanup();
```

- `protected virtual Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx) : System.Void`  

```csharp
protected virtual System.Void Execute(UnityEngine.Rendering.HighDefinition.CustomPassContext ctx);
```

- `protected virtual Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd) : System.Void`  

```csharp
protected virtual System.Void Setup(UnityEngine.Rendering.ScriptableRenderContext renderContext, UnityEngine.Rendering.CommandBuffer cmd);
```


## Nested types

- `Game.Rendering.UndergroundPass+ComputeFlags`  

