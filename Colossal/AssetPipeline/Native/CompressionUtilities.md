# Colossal.AssetPipeline.Native.CompressionUtilities

**Assembly:** `Colossal.AssetPipeline.Native`  
**Namespace:** `Colossal.AssetPipeline.Native`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class CompressionUtilities
{
    public static System.Byte[] Compress(System.Byte[] data, Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 compressionLevel);
    public static Unity.Collections.NativeArray<System.Byte> Compress(Unity.Collections.NativeArray<System.Byte> data, System.Int32 dataSize, Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 compressionLevel, System.Int32& resultSize);
    public static System.Byte[] Decompress(System.Byte[] data, Colossal.AssetPipeline.Native.CompressionFormat format);
    public static Unity.Collections.NativeArray<System.Byte> Decompress(Unity.Collections.NativeArray<System.Byte> data, System.Int32 dataSize, Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32& resultSize);
}
```


## Methods

- `public static Compress(System.Byte[] data, Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 compressionLevel = 3) : System.Byte[]`  

```csharp
public static System.Byte[] Compress(System.Byte[] data, Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 compressionLevel);
```

- `public static Compress(Unity.Collections.NativeArray<System.Byte> data, System.Int32 dataSize, Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 compressionLevel, System.Int32& resultSize) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public static Unity.Collections.NativeArray<System.Byte> Compress(Unity.Collections.NativeArray<System.Byte> data, System.Int32 dataSize, Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 compressionLevel, System.Int32& resultSize);
```

- `public static Decompress(System.Byte[] data, Colossal.AssetPipeline.Native.CompressionFormat format) : System.Byte[]`  

```csharp
public static System.Byte[] Decompress(System.Byte[] data, Colossal.AssetPipeline.Native.CompressionFormat format);
```

- `public static Decompress(Unity.Collections.NativeArray<System.Byte> data, System.Int32 dataSize, Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32& resultSize) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public static Unity.Collections.NativeArray<System.Byte> Decompress(Unity.Collections.NativeArray<System.Byte> data, System.Int32 dataSize, Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32& resultSize);
```


