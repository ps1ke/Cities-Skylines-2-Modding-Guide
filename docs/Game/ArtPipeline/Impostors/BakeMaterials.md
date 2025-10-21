# Game.ArtPipeline.Impostors.BakeMaterials

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Impostors`  

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
    private System.Collections.Generic.Dictionary<UnityEngine.Shader, Game.ArtPipeline.Impostors.BakingScene+MaterialBinding> m_UserBakingMaterials;
    private static readonly System.Int32 m_RawDepthRTId;
    private static readonly System.Int32 m_DilatedColorRTId;
    private static readonly System.Int32 m_DilatedMaskRTId;
    private static readonly System.Int32 m_SaveMaskRTId;
    private static readonly System.Int32 m_MainTexId;
    private static readonly System.Int32 m_MaskTexId;

    public BakeMaterials();

    private System.Void ClearUserBakingMaterials();
    private System.Void CompleteFillInMaterial(Game.ArtPipeline.Impostors.BakeMaterials+SurfaceData[] surfaces, Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] bindings, Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.ImpostorRenderingSettings renderSettings, Game.ArtPipeline.Impostors.GeneratedAssets assets);
    private System.Void CompleteUserFillInMaterial(Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] bindings, Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.ImpostorRenderingSettings renderSettings, Game.ArtPipeline.Impostors.GeneratedAssets assets, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Rendering.CommandBuffer userCmd);
    private static System.Void CreateDefaultMaterialBindings(Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[]& bindings, Game.ArtPipeline.Impostors.BakeMaterials+SurfaceData[]& surfaces);
    private static System.Void CreateFillInMaterial(UnityEngine.Rendering.CommandBuffer cmd, Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] bindings, UnityEngine.Material renderingMaterial, Game.ArtPipeline.Impostors.GeneratedAssets assets);
    private static Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] CreateUserMaterialBindings(Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.BakeMaterials+TextureBinding[] outputUserTextures);
    public System.Void DilateOutput(UnityEngine.RenderTexture rt, UnityEngine.RenderTexture dilated, System.Int32 dilationWidth);
    public System.Void DilateOutputs(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.RenderTexture[] rts, UnityEngine.RenderTexture maskTexture, System.Int32 dilationWidth);
    public System.Void Dispose();
    public System.Void GenerateMaterialImpostor(Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.ImpostorRenderingSettings renderSettings, Game.ArtPipeline.Impostors.GeneratedAssets generatedAssets, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Rendering.CommandBuffer commandBuffer);
    private System.Void GenerateMultiPassImpostor(Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.Sphericalshot sphericalshot, Game.ArtPipeline.Impostors.BakeMaterials+SurfaceData[] surfaces, System.Int32 dilateWidth);
    private System.Void GenerateUserImpostor(UnityEngine.Rendering.CommandBuffer cmd, Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.Sphericalshot sphericalShot, Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] bindings, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, Game.ArtPipeline.Impostors.ImpostorRenderingSettings renderSettings, System.Int32 dilateWidth);
    public static System.Void PrepareRenderTexture(UnityEngine.RenderTexture rt, UnityEngine.Color color);
    public static System.Void Repack(Game.ArtPipeline.Impostors.BakeMaterials+Packing packing, UnityEngine.RenderTexture input, UnityEngine.RenderTexture output);
    private static System.Void SetAssetMaterialTexture(UnityEngine.Material material, UnityEngine.Texture2D tex, Game.ArtPipeline.Impostors.BakeMaterials+TextureBinding binding, System.Boolean isSpherical);
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

- `private System.Collections.Generic.Dictionary<UnityEngine.Shader, Game.ArtPipeline.Impostors.BakingScene+MaterialBinding> m_UserBakingMaterials`  

```csharp
private System.Collections.Generic.Dictionary<UnityEngine.Shader, Game.ArtPipeline.Impostors.BakingScene+MaterialBinding> m_UserBakingMaterials;
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

- `private CompleteFillInMaterial(Game.ArtPipeline.Impostors.BakeMaterials+SurfaceData[] surfaces, Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] bindings, Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.ImpostorRenderingSettings renderSettings, Game.ArtPipeline.Impostors.GeneratedAssets assets) : System.Void`  

```csharp
private System.Void CompleteFillInMaterial(Game.ArtPipeline.Impostors.BakeMaterials+SurfaceData[] surfaces, Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] bindings, Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.ImpostorRenderingSettings renderSettings, Game.ArtPipeline.Impostors.GeneratedAssets assets);
```

- `private CompleteUserFillInMaterial(Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] bindings, Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.ImpostorRenderingSettings renderSettings, Game.ArtPipeline.Impostors.GeneratedAssets assets, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Rendering.CommandBuffer userCmd = null) : System.Void`  

```csharp
private System.Void CompleteUserFillInMaterial(Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] bindings, Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.ImpostorRenderingSettings renderSettings, Game.ArtPipeline.Impostors.GeneratedAssets assets, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Rendering.CommandBuffer userCmd);
```

- `private static CreateDefaultMaterialBindings(Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[]& bindings, Game.ArtPipeline.Impostors.BakeMaterials+SurfaceData[]& surfaces) : System.Void`  

```csharp
private static System.Void CreateDefaultMaterialBindings(Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[]& bindings, Game.ArtPipeline.Impostors.BakeMaterials+SurfaceData[]& surfaces);
```

- `private static CreateFillInMaterial(UnityEngine.Rendering.CommandBuffer cmd, Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] bindings, UnityEngine.Material renderingMaterial, Game.ArtPipeline.Impostors.GeneratedAssets assets) : System.Void`  

```csharp
private static System.Void CreateFillInMaterial(UnityEngine.Rendering.CommandBuffer cmd, Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] bindings, UnityEngine.Material renderingMaterial, Game.ArtPipeline.Impostors.GeneratedAssets assets);
```

- `private static CreateUserMaterialBindings(Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.BakeMaterials+TextureBinding[] outputUserTextures) : Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[]`  

```csharp
private static Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] CreateUserMaterialBindings(Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.BakeMaterials+TextureBinding[] outputUserTextures);
```

- `public DilateOutput(UnityEngine.RenderTexture rt, UnityEngine.RenderTexture dilated, System.Int32 dilationWidth = 16) : System.Void`  

```csharp
public System.Void DilateOutput(UnityEngine.RenderTexture rt, UnityEngine.RenderTexture dilated, System.Int32 dilationWidth);
```

- `public DilateOutputs(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.RenderTexture[] rts, UnityEngine.RenderTexture maskTexture, System.Int32 dilationWidth = 16) : System.Void`  

```csharp
public System.Void DilateOutputs(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.RenderTexture[] rts, UnityEngine.RenderTexture maskTexture, System.Int32 dilationWidth);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public GenerateMaterialImpostor(Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.ImpostorRenderingSettings renderSettings, Game.ArtPipeline.Impostors.GeneratedAssets generatedAssets, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Rendering.CommandBuffer commandBuffer = null) : System.Void`  

```csharp
public System.Void GenerateMaterialImpostor(Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.ImpostorRenderingSettings renderSettings, Game.ArtPipeline.Impostors.GeneratedAssets generatedAssets, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Rendering.CommandBuffer commandBuffer);
```

- `private GenerateMultiPassImpostor(Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.Sphericalshot sphericalshot, Game.ArtPipeline.Impostors.BakeMaterials+SurfaceData[] surfaces, System.Int32 dilateWidth) : System.Void`  

```csharp
private System.Void GenerateMultiPassImpostor(Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.Sphericalshot sphericalshot, Game.ArtPipeline.Impostors.BakeMaterials+SurfaceData[] surfaces, System.Int32 dilateWidth);
```

- `private GenerateUserImpostor(UnityEngine.Rendering.CommandBuffer cmd, Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.Sphericalshot sphericalShot, Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] bindings, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, Game.ArtPipeline.Impostors.ImpostorRenderingSettings renderSettings, System.Int32 dilateWidth) : System.Void`  

```csharp
private System.Void GenerateUserImpostor(UnityEngine.Rendering.CommandBuffer cmd, Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.Sphericalshot sphericalShot, Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] bindings, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, Game.ArtPipeline.Impostors.ImpostorRenderingSettings renderSettings, System.Int32 dilateWidth);
```

- `public static PrepareRenderTexture(UnityEngine.RenderTexture rt, UnityEngine.Color color) : System.Void`  

```csharp
public static System.Void PrepareRenderTexture(UnityEngine.RenderTexture rt, UnityEngine.Color color);
```

- `public static Repack(Game.ArtPipeline.Impostors.BakeMaterials+Packing packing, UnityEngine.RenderTexture input, UnityEngine.RenderTexture output) : System.Void`  

```csharp
public static System.Void Repack(Game.ArtPipeline.Impostors.BakeMaterials+Packing packing, UnityEngine.RenderTexture input, UnityEngine.RenderTexture output);
```

- `private static SetAssetMaterialTexture(UnityEngine.Material material, UnityEngine.Texture2D tex, Game.ArtPipeline.Impostors.BakeMaterials+TextureBinding binding, System.Boolean isSpherical) : System.Void`  

```csharp
private static System.Void SetAssetMaterialTexture(UnityEngine.Material material, UnityEngine.Texture2D tex, Game.ArtPipeline.Impostors.BakeMaterials+TextureBinding binding, System.Boolean isSpherical);
```


## Nested types

- `Game.ArtPipeline.Impostors.BakeMaterials+SurfaceData`  
- `Game.ArtPipeline.Impostors.BakeMaterials+TextureBinding`  
- `Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding`  
- `Game.ArtPipeline.Impostors.BakeMaterials+Packing`  
- `Game.ArtPipeline.Impostors.BakeMaterials+ShaderPass`  

