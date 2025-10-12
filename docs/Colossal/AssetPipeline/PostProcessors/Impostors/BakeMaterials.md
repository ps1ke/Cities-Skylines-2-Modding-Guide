# Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.PostProcessors.Impostors`  

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
- `private System.Collections.Generic.Dictionary<UnityEngine.Shader, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene+MaterialBinding> m_UserBakingMaterials`  
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
- `private CompleteUserFillInMaterial(Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding[] bindings, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene scene, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings settings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorRenderingSettings renderSettings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets assets, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Rendering.CommandBuffer userCmd = null) : System.Void`  
- `private static CreateFillInMaterial(UnityEngine.Rendering.CommandBuffer cmd, Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding[] bindings, UnityEngine.Material renderingMaterial, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets assets) : System.Void`  
- `private static CreateUserMaterialBindings(Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings settings, Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+TextureBinding[] outputUserTextures) : Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding[]`  
- `private DilateOutputs(UnityEngine.Rendering.CommandBuffer cmd, UnityEngine.RenderTexture[] rts, UnityEngine.RenderTexture maskTexture, System.Int32 dilationWidth = 16) : System.Void`  
- `public Dispose() : System.Void`  
- `public GenerateMaterialImpostor(Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene scene, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+ImpostorSettings settings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorRenderingSettings renderSettings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorPostProcessor+GeneratedAssets generatedAssets, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, UnityEngine.Rendering.CommandBuffer commandBuffer = null) : System.Void`  
- `private GenerateUserImpostor(UnityEngine.Rendering.CommandBuffer cmd, Colossal.AssetPipeline.PostProcessors.Impostors.BakingScene scene, Colossal.AssetPipeline.PostProcessors.Impostors.SphericalShot sphericalShot, Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding[] bindings, System.Collections.Generic.Dictionary<UnityEngine.Shader, UnityEngine.Material> userShaderBindings, Colossal.AssetPipeline.PostProcessors.Impostors.ImpostorRenderingSettings renderSettings, System.Int32 dilateWidth) : System.Void`  
- `public static PrepareRenderTexture(UnityEngine.RenderTexture rt, UnityEngine.Color color) : System.Void`  
- `public static Repack(Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+Packing packing, UnityEngine.RenderTexture input, UnityEngine.RenderTexture output) : System.Void`  
- `private static SetAssetMaterialTexture(UnityEngine.Material material, UnityEngine.Texture2D tex, Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+TextureBinding binding, System.Boolean isSpherical) : System.Void`  

## Nested types

- `Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+TextureBinding`  
- `Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+MaterialBinding`  
- `Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+Packing`  
- `Colossal.AssetPipeline.PostProcessors.Impostors.BakeMaterials+ShaderPass`  

