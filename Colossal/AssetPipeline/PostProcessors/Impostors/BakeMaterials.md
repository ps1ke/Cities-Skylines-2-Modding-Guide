# Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Impostors`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public class BakeMaterials : System.IDisposable
{
    private UnityEngine.Material m_DilateMaterial;
    private UnityEngine.Material m_BlitMaterial;
    private UnityEngine.Material m_BlitAlphaToAlphaMaterial;
    private UnityEngine.Material m_BlitRedToAlphaMaterial;
    private UnityEngine.Material m_BlitAlphaToRedMaterial;
    private UnityEngine.Material m_ConvertDepthMaterial;
    private UnityEngine.Material m_ConvertDepthNormalizedMaterial;
    private UnityEngine.MaterialPropertyBlock m_PropertyBlock;
    private System.Collections.Generic.Dictionary<UnityEngine.Shader, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding> m_UserBakingMaterials;
    private static readonly System.Int32 m_RawDepthRTId;
    private static readonly System.Int32 m_DilatedColorRTId;
    private static readonly System.Int32 m_DilatedMaskRTId;
    private static readonly System.Int32 m_SaveMaskRTId;
    private static readonly System.Int32 m_MainTexId;
    private static readonly System.Int32 m_MaskTexId;

    public BakeMaterials();

    private System.Void ClearUserBakingMaterials();
    private System.Void CompleteUserFillInMaterial(Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding[] bindings, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene scene, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings settings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorRenderingSettings renderSettings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets assets, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Rendering.CommandBuffer userCmd);
    private static System.Void CreateFillInMaterial(UnityEngine.Rendering.CommandBuffer cmd, Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding[] bindings, UnityEngine.Material renderingMaterial, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets assets);
    private static Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding[] CreateUserMaterialBindings(Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings settings, Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+TextureBinding[] outputUserTextures);
    private System.Void DilateOutputs(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.RenderTexture[] rts, UnityEngine.RenderTexture maskTexture, System.Int32 dilationWidth);
    public System.Void Dispose();
    public System.Void GenerateMaterialImpostor(Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene scene, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings settings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorRenderingSettings renderSettings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets generatedAssets, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Rendering.CommandBuffer commandBuffer);
    private System.Void GenerateUserImpostor(UnityEngine.Rendering.CommandBuffer cmd, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene scene, Colossal.AssetPipeline.PostProcessors.Impostors.SphericalShot sphericalShot, Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding[] bindings, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorRenderingSettings renderSettings, System.Int32 dilateWidth);
    public static System.Void PrepareRenderTexture(UnityEngine.RenderTexture rt, UnityEngine.Color color);
    public static System.Void Repack(Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+Packing packing, UnityEngine.RenderTexture input, UnityEngine.RenderTexture output);
    private static System.Void SetAssetMaterialTexture(UnityEngine.Material material, UnityEngine.Texture2D tex, Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+TextureBinding binding, System.Boolean isSpherical);
}
```


## Fields

- `private UnityEngine.Material m_DilateMaterial`  

```csharp
private UnityEngine.Material m_DilateMaterial;
```

- `private UnityEngine.Material m_BlitMaterial`  

```csharp
private UnityEngine.Material m_BlitMaterial;
```

- `private UnityEngine.Material m_BlitAlphaToAlphaMaterial`  

```csharp
private UnityEngine.Material m_BlitAlphaToAlphaMaterial;
```

- `private UnityEngine.Material m_BlitRedToAlphaMaterial`  

```csharp
private UnityEngine.Material m_BlitRedToAlphaMaterial;
```

- `private UnityEngine.Material m_BlitAlphaToRedMaterial`  

```csharp
private UnityEngine.Material m_BlitAlphaToRedMaterial;
```

- `private UnityEngine.Material m_ConvertDepthMaterial`  

```csharp
private UnityEngine.Material m_ConvertDepthMaterial;
```

- `private UnityEngine.Material m_ConvertDepthNormalizedMaterial`  

```csharp
private UnityEngine.Material m_ConvertDepthNormalizedMaterial;
```

- `private UnityEngine.MaterialPropertyBlock m_PropertyBlock`  

```csharp
private UnityEngine.MaterialPropertyBlock m_PropertyBlock;
```

- `private System.Collections.Generic.Dictionary<UnityEngine.Shader, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding> m_UserBakingMaterials`  

```csharp
private System.Collections.Generic.Dictionary<UnityEngine.Shader, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding> m_UserBakingMaterials;
```

- `private static readonly System.Int32 m_RawDepthRTId`  

```csharp
private static readonly System.Int32 m_RawDepthRTId;
```

- `private static readonly System.Int32 m_DilatedColorRTId`  

```csharp
private static readonly System.Int32 m_DilatedColorRTId;
```

- `private static readonly System.Int32 m_DilatedMaskRTId`  

```csharp
private static readonly System.Int32 m_DilatedMaskRTId;
```

- `private static readonly System.Int32 m_SaveMaskRTId`  

```csharp
private static readonly System.Int32 m_SaveMaskRTId;
```

- `private static readonly System.Int32 m_MainTexId`  

```csharp
private static readonly System.Int32 m_MainTexId;
```

- `private static readonly System.Int32 m_MaskTexId`  

```csharp
private static readonly System.Int32 m_MaskTexId;
```


## Constructors

- `public BakeMaterials()`  

```csharp
public BakeMaterials();
```


## Methods

- `private ClearUserBakingMaterials() : System.Void`  

```csharp
private System.Void ClearUserBakingMaterials();
```

- `private CompleteUserFillInMaterial(Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding[] bindings, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene scene, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings settings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorRenderingSettings renderSettings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets assets, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Rendering.CommandBuffer userCmd = null) : System.Void`  

```csharp
private System.Void CompleteUserFillInMaterial(Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding[] bindings, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene scene, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings settings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorRenderingSettings renderSettings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets assets, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Rendering.CommandBuffer userCmd);
```

- `private static CreateFillInMaterial(UnityEngine.Rendering.CommandBuffer cmd, Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding[] bindings, UnityEngine.Material renderingMaterial, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets assets) : System.Void`  

```csharp
private static System.Void CreateFillInMaterial(UnityEngine.Rendering.CommandBuffer cmd, Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding[] bindings, UnityEngine.Material renderingMaterial, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets assets);
```

- `private static CreateUserMaterialBindings(Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings settings, Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+TextureBinding[] outputUserTextures) : Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding[]`  

```csharp
private static Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding[] CreateUserMaterialBindings(Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings settings, Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+TextureBinding[] outputUserTextures);
```

- `private DilateOutputs(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.RenderTexture[] rts, UnityEngine.RenderTexture maskTexture, System.Int32 dilationWidth = 16) : System.Void`  

```csharp
private System.Void DilateOutputs(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.RenderTexture[] rts, UnityEngine.RenderTexture maskTexture, System.Int32 dilationWidth);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GenerateMaterialImpostor(Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene scene, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings settings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorRenderingSettings renderSettings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets generatedAssets, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Rendering.CommandBuffer commandBuffer = null) : System.Void`  

```csharp
public System.Void GenerateMaterialImpostor(Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene scene, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings settings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorRenderingSettings renderSettings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets generatedAssets, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Rendering.CommandBuffer commandBuffer);
```

- `private GenerateUserImpostor(UnityEngine.Rendering.CommandBuffer cmd, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene scene, Colossal.AssetPipeline.PostProcessors.Impostors.SphericalShot sphericalShot, Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding[] bindings, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorRenderingSettings renderSettings, System.Int32 dilateWidth) : System.Void`  

```csharp
private System.Void GenerateUserImpostor(UnityEngine.Rendering.CommandBuffer cmd, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene scene, Colossal.AssetPipeline.PostProcessors.Impostors.SphericalShot sphericalShot, Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding[] bindings, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorRenderingSettings renderSettings, System.Int32 dilateWidth);
```

- `public static PrepareRenderTexture(UnityEngine.RenderTexture rt, UnityEngine.Color color) : System.Void`  

```csharp
public static System.Void PrepareRenderTexture(UnityEngine.RenderTexture rt, UnityEngine.Color color);
```

- `public static Repack(Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+Packing packing, UnityEngine.RenderTexture input, UnityEngine.RenderTexture output) : System.Void`  

```csharp
public static System.Void Repack(Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+Packing packing, UnityEngine.RenderTexture input, UnityEngine.RenderTexture output);
```

- `private static SetAssetMaterialTexture(UnityEngine.Material material, UnityEngine.Texture2D tex, Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+TextureBinding binding, System.Boolean isSpherical) : System.Void`  

```csharp
private static System.Void SetAssetMaterialTexture(UnityEngine.Material material, UnityEngine.Texture2D tex, Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+TextureBinding binding, System.Boolean isSpherical);
```


## Nested types

- `Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+TextureBinding`  
- `Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding`  
- `Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+Packing`  
- `Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+ShaderPass`  

