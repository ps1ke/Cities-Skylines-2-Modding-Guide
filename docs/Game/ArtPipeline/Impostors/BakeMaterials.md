# Game.ArtPipeline.Impostors.BakeMaterials

**Assembly:** `Game.ArtPipeline`  
**Namespace:** `Game.ArtPipeline.Impostors`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `System.IDisposable`  

## Fields

- `private UnityEngine.Material m_DilateMaterial`  
- `private UnityEngine.Material m_BlitMaterial`  
- `private UnityEngine.Material m_BlitAlphaToAlphaMaterial`  
- `private UnityEngine.Material m_BlitRedToAlphaMaterial`  
- `private UnityEngine.Material m_BlitAlphaToRedMaterial`  
- `private UnityEngine.Material m_ConvertDepthMaterial`  
- `private UnityEngine.Material m_ConvertDepthNormalizedMaterial`  
- `private UnityEngine.MaterialPropertyBlock m_PropertyBlock`  
- `private System.Collections.Generic.Dictionary<UnityEngine.Shader, Game.ArtPipeline.Impostors.BakingScene+MaterialBinding> m_UserBakingMaterials`  
- `private static readonly System.Int32 m_RawDepthRTId`  
- `private static readonly System.Int32 m_DilatedColorRTId`  
- `private static readonly System.Int32 m_DilatedMaskRTId`  
- `private static readonly System.Int32 m_SaveMaskRTId`  
- `private static readonly System.Int32 m_MainTexId`  
- `private static readonly System.Int32 m_MaskTexId`  

## Constructors

- `public BakeMaterials()`  

## Methods

- `private ClearUserBakingMaterials() : System.Void`  
- `private CompleteFillInMaterial(Game.ArtPipeline.Impostors.BakeMaterials+SurfaceData[] surfaces, Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] bindings, Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.ImpostorRenderingSettings renderSettings, Game.ArtPipeline.Impostors.GeneratedAssets assets) : System.Void`  
- `private CompleteUserFillInMaterial(Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] bindings, Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.ImpostorRenderingSettings renderSettings, Game.ArtPipeline.Impostors.GeneratedAssets assets, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Rendering.CommandBuffer userCmd = null) : System.Void`  
- `private static CreateDefaultMaterialBindings(Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[]& bindings, Game.ArtPipeline.Impostors.BakeMaterials+SurfaceData[]& surfaces) : System.Void`  
- `private static CreateFillInMaterial(UnityEngine.Rendering.CommandBuffer cmd, Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] bindings, UnityEngine.Material renderingMaterial, Game.ArtPipeline.Impostors.GeneratedAssets assets) : System.Void`  
- `private static CreateUserMaterialBindings(Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.BakeMaterials+TextureBinding[] outputUserTextures) : Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[]`  
- `public DilateOutput(UnityEngine.RenderTexture rt, UnityEngine.RenderTexture dilated, System.Int32 dilationWidth = 16) : System.Void`  
- `public DilateOutputs(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.RenderTexture[] rts, UnityEngine.RenderTexture maskTexture, System.Int32 dilationWidth = 16) : System.Void`  
- `public Dispose() : System.Void`  
- `public GenerateMaterialImpostor(Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.ImpostorSettings settings, Game.ArtPipeline.Impostors.ImpostorRenderingSettings renderSettings, Game.ArtPipeline.Impostors.GeneratedAssets generatedAssets, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Rendering.CommandBuffer commandBuffer = null) : System.Void`  
- `private GenerateMultiPassImpostor(Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.Sphericalshot sphericalshot, Game.ArtPipeline.Impostors.BakeMaterials+SurfaceData[] surfaces, System.Int32 dilateWidth) : System.Void`  
- `private GenerateUserImpostor(UnityEngine.Rendering.CommandBuffer cmd, Game.ArtPipeline.Impostors.BakingScene scene, Game.ArtPipeline.Impostors.Sphericalshot sphericalShot, Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding[] bindings, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, Game.ArtPipeline.Impostors.ImpostorRenderingSettings renderSettings, System.Int32 dilateWidth) : System.Void`  
- `public static PrepareRenderTexture(UnityEngine.RenderTexture rt, UnityEngine.Color color) : System.Void`  
- `public static Repack(Game.ArtPipeline.Impostors.BakeMaterials+Packing packing, UnityEngine.RenderTexture input, UnityEngine.RenderTexture output) : System.Void`  
- `private static SetAssetMaterialTexture(UnityEngine.Material material, UnityEngine.Texture2D tex, Game.ArtPipeline.Impostors.BakeMaterials+TextureBinding binding, System.Boolean isSpherical) : System.Void`  

## Nested types

- `Game.ArtPipeline.Impostors.BakeMaterials+SurfaceData`  
- `Game.ArtPipeline.Impostors.BakeMaterials+TextureBinding`  
- `Game.ArtPipeline.Impostors.BakeMaterials+MaterialBinding`  
- `Game.ArtPipeline.Impostors.BakeMaterials+Packing`  
- `Game.ArtPipeline.Impostors.BakeMaterials+ShaderPass`  

