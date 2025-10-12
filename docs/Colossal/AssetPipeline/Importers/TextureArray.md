# Colossal.AssetPipeline.Importers.TextureImporter+TextureArray

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.Importers.TextureImporter+ITexture`, `System.IDisposable`  

## Fields

- `private System.Collections.Generic.List<Colossal.AssetPipeline.Importers.TextureImporter+Texture> m_Textures`  
- `private UnityEngine.Texture2DArray m_CachedObject`  

## Properties

- `public System.String name { get }`  
- `public System.Int32 width { get }`  
- `public System.Int32 height { get }`  
- `public System.Int32 mipsCount { get }`  
- `public System.Int32 rawMipsCount { get }`  
- `public System.Int32 compressedMipsCount { get }`  
- `public UnityEngine.Experimental.Rendering.GraphicsFormat format { get }`  
- `public UnityEngine.Experimental.Rendering.GraphicsFormat rawFormat { get }`  
- `public UnityEngine.Experimental.Rendering.GraphicsFormat compressedFormat { get }`  
- `public UnityEngine.Rendering.TextureDimension dimension { get }`  
- `public System.Int32 depth { get }`  
- `public UnityEngine.FilterMode filterMode { get; set }`  
- `public UnityEngine.TextureWrapMode wrapMode { get; set }`  
- `public System.Int32 anisoLevel { get }`  
- `public Colossal.AssetPipeline.IAsset sourceAsset { get }`  

## Constructors

- `public TextureArray(System.Collections.Generic.IEnumerable<Colossal.AssetPipeline.Importers.TextureImporter+Texture> textures)`  
- `public TextureArray()`  

## Methods

- `public AddSlice(Colossal.AssetPipeline.Importers.TextureImporter+Texture texture) : System.Boolean`  
- `private CheckTextureSize(Colossal.AssetPipeline.Importers.TextureImporter+Texture texture) : System.Boolean`  
- `public Dispose() : System.Void`  
- `public GetCompressedMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  
- `public GetMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  
- `public GetRawMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  
- `public ToUnityTexture(System.Boolean hideAndDontSave = True) : UnityEngine.Texture`  
- `public ToUnityTextureRaw(System.Boolean hideAndDontSave = True) : UnityEngine.Texture`  

