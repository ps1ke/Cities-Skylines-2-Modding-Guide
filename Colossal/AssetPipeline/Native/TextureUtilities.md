# Colossal.AssetPipeline.Native.TextureUtilities

**Assembly:** `Colossal.AssetPipeline.Native`  
**Namespace:** `Colossal.AssetPipeline.Native`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class TextureUtilities
{
    public static System.Byte[] SaveImage(System.Byte[] pixelData, System.Int32 width, System.Int32 height, System.Int32 channels, System.Int32 bitsPerChannel, Colossal.AssetPipeline.Native.NativeTextures+ImageFileFormat format, System.Int32 compressionLevel);
    public static System.Byte[] SaveImage(System.IntPtr pixelDataPtr, System.Int64 pixelDataSize, System.Int32 width, System.Int32 height, System.Int32 channels, System.Int32 bitsPerChannel, Colossal.AssetPipeline.Native.NativeTextures+ImageFileFormat format, System.Int32 compressionLevel);
}
```


## Methods

- `public static SaveImage(System.Byte[] pixelData, System.Int32 width, System.Int32 height, System.Int32 channels, System.Int32 bitsPerChannel, Colossal.AssetPipeline.Native.NativeTextures+ImageFileFormat format, System.Int32 compressionLevel = 4) : System.Byte[]`  

```csharp
public static System.Byte[] SaveImage(System.Byte[] pixelData, System.Int32 width, System.Int32 height, System.Int32 channels, System.Int32 bitsPerChannel, Colossal.AssetPipeline.Native.NativeTextures+ImageFileFormat format, System.Int32 compressionLevel);
```

- `public static SaveImage(System.IntPtr pixelDataPtr, System.Int64 pixelDataSize, System.Int32 width, System.Int32 height, System.Int32 channels, System.Int32 bitsPerChannel, Colossal.AssetPipeline.Native.NativeTextures+ImageFileFormat format, System.Int32 compressionLevel = 4) : System.Byte[]`  

```csharp
public static System.Byte[] SaveImage(System.IntPtr pixelDataPtr, System.Int64 pixelDataSize, System.Int32 width, System.Int32 height, System.Int32 channels, System.Int32 bitsPerChannel, Colossal.AssetPipeline.Native.NativeTextures+ImageFileFormat format, System.Int32 compressionLevel);
```


