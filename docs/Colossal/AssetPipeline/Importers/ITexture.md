# Colossal.AssetPipeline.Importers.TextureImporter+ITexture

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** interface abstract public  

**Implements:** `System.IDisposable`  

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

## Methods

- `public abstract GetCompressedMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  
- `public abstract GetMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  
- `public abstract GetRawMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  
- `public abstract ToUnityTexture(System.Boolean hideAndDontSave = True) : UnityEngine.Texture`  
- `public abstract ToUnityTextureRaw(System.Boolean hideAndDontSave = True) : UnityEngine.Texture`  

