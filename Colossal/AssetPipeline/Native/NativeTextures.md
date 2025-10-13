# Colossal.AssetPipeline.Native.NativeTextures

**Assembly:** `Colossal.AssetPipeline.Native`  
**Namespace:** `Colossal.AssetPipeline.Native`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class NativeTextures
{
    public NativeTextures();

    public static System.Int32 BlockCompress(System.IntPtr src, System.Int32 srcWidth, System.Int32 srcHeight, System.IntPtr dst, Colossal.AssetPipeline.Native.NativeTextures+BlockCompressionFormat format, Colossal.AssetPipeline.Native.NativeTextures+BlockCompressionFlags flags, System.Int32 effort);
    public static System.Void FileFree(System.IntPtr ptr);
    public static System.Int32 FileGetInfo(System.IntPtr data, System.Int64 dataSize, Colossal.AssetPipeline.Native.NativeTextures+ImageFileInfo& info);
    public static System.Int64 FileLoad(System.IntPtr data, System.Int64 dataSize, Colossal.AssetPipeline.Native.NativeTextures+LoadFlags flags, System.IntPtr dst, System.Int64 dstSize);
    public static System.IntPtr FileSave(System.IntPtr data, System.Int64 dataSize, Colossal.AssetPipeline.Native.NativeTextures+ImageFileInfo& info, System.Int64& r_size);
    public static System.Void ImageResize(System.IntPtr src, System.Int32 srcWidth, System.Int32 srcHeight, System.IntPtr dst, System.Int32 dstWidth, System.Int32 dstHeight, System.Int32 channels, System.Int32 bitsPerChannel, System.Int32 srgb, System.Int32 clamp, System.Int32 alphaIsTransparency);
}
```


## Constructors

- `public NativeTextures()`  

```csharp
public NativeTextures();
```


## Methods

- `public static BlockCompress(System.IntPtr src, System.Int32 srcWidth, System.Int32 srcHeight, System.IntPtr dst, Colossal.AssetPipeline.Native.NativeTextures+BlockCompressionFormat format, Colossal.AssetPipeline.Native.NativeTextures+BlockCompressionFlags flags, System.Int32 effort) : System.Int32`  

```csharp
public static System.Int32 BlockCompress(System.IntPtr src, System.Int32 srcWidth, System.Int32 srcHeight, System.IntPtr dst, Colossal.AssetPipeline.Native.NativeTextures+BlockCompressionFormat format, Colossal.AssetPipeline.Native.NativeTextures+BlockCompressionFlags flags, System.Int32 effort);
```

- `public static FileFree(System.IntPtr ptr) : System.Void`  

```csharp
public static System.Void FileFree(System.IntPtr ptr);
```

- `public static FileGetInfo(System.IntPtr data, System.Int64 dataSize, Colossal.AssetPipeline.Native.NativeTextures+ImageFileInfo& info) : System.Int32`  

```csharp
public static System.Int32 FileGetInfo(System.IntPtr data, System.Int64 dataSize, Colossal.AssetPipeline.Native.NativeTextures+ImageFileInfo& info);
```

- `public static FileLoad(System.IntPtr data, System.Int64 dataSize, Colossal.AssetPipeline.Native.NativeTextures+LoadFlags flags, System.IntPtr dst, System.Int64 dstSize) : System.Int64`  

```csharp
public static System.Int64 FileLoad(System.IntPtr data, System.Int64 dataSize, Colossal.AssetPipeline.Native.NativeTextures+LoadFlags flags, System.IntPtr dst, System.Int64 dstSize);
```

- `public static FileSave(System.IntPtr data, System.Int64 dataSize, Colossal.AssetPipeline.Native.NativeTextures+ImageFileInfo& info, System.Int64& r_size) : System.IntPtr`  

```csharp
public static System.IntPtr FileSave(System.IntPtr data, System.Int64 dataSize, Colossal.AssetPipeline.Native.NativeTextures+ImageFileInfo& info, System.Int64& r_size);
```

- `public static ImageResize(System.IntPtr src, System.Int32 srcWidth, System.Int32 srcHeight, System.IntPtr dst, System.Int32 dstWidth, System.Int32 dstHeight, System.Int32 channels, System.Int32 bitsPerChannel, System.Int32 srgb, System.Int32 clamp, System.Int32 alphaIsTransparency) : System.Void`  

```csharp
public static System.Void ImageResize(System.IntPtr src, System.Int32 srcWidth, System.Int32 srcHeight, System.IntPtr dst, System.Int32 dstWidth, System.Int32 dstHeight, System.Int32 channels, System.Int32 bitsPerChannel, System.Int32 srgb, System.Int32 clamp, System.Int32 alphaIsTransparency);
```


## Nested types

- `Colossal.AssetPipeline.Native.NativeTextures+ImageFileFormat`  
- `Colossal.AssetPipeline.Native.NativeTextures+ImageFileInfo`  
- `Colossal.AssetPipeline.Native.NativeTextures+LoadFlags`  
- `Colossal.AssetPipeline.Native.NativeTextures+BlockCompressionFormat`  
- `Colossal.AssetPipeline.Native.NativeTextures+BlockCompressionFlags`  

