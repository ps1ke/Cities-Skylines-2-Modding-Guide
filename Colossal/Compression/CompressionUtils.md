# Colossal.Compression.CompressionUtils

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.Compression`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class CompressionUtils
{
    private static const System.Int32 kMagicNumber;

    public static System.Int32 CalcMaxCompressedSize(Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 length);
    public static Unity.Jobs.JobHandle Compress(Colossal.AssetPipeline.Native.CompressionFormat format, Unity.Collections.NativeSlice<System.Byte> inData, Colossal.Compression.CompressedBytesStorage outCompressedData, Unity.Jobs.JobHandle jobHandle, System.Int32 compressionLevel);
    public static System.Byte[] CompressZstdWithMarker(System.Byte[] arr, System.Int32 count);
    public static Unity.Jobs.JobHandle Decompress(Colossal.AssetPipeline.Native.CompressionFormat format, Unity.Collections.NativeSlice<System.Byte> inCompressedData, Unity.Collections.NativeSlice<System.Byte> outData, Unity.Jobs.JobHandle jobHandle);
    public static System.Byte[] DecompressZstdWithMarker(System.Byte[] arr);
    public static System.Void DecompressZstdWithMarker(Unity.Collections.NativeArray<System.Byte> dst, Unity.Collections.NativeArray<System.Byte> src);
}
```


## Fields

- `private static const System.Int32 kMagicNumber`  

```csharp
private static const System.Int32 kMagicNumber;
```


## Methods

- `public static CalcMaxCompressedSize(Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 length) : System.Int32`  

```csharp
public static System.Int32 CalcMaxCompressedSize(Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 length);
```

- `public static Compress(Colossal.AssetPipeline.Native.CompressionFormat format, Unity.Collections.NativeSlice<System.Byte> inData, Colossal.Compression.CompressedBytesStorage outCompressedData, Unity.Jobs.JobHandle jobHandle = null, System.Int32 compressionLevel = 1) : Unity.Jobs.JobHandle`  

```csharp
public static Unity.Jobs.JobHandle Compress(Colossal.AssetPipeline.Native.CompressionFormat format, Unity.Collections.NativeSlice<System.Byte> inData, Colossal.Compression.CompressedBytesStorage outCompressedData, Unity.Jobs.JobHandle jobHandle, System.Int32 compressionLevel);
```

- `public static CompressZstdWithMarker(System.Byte[] arr, System.Int32 count) : System.Byte[]`  

```csharp
public static System.Byte[] CompressZstdWithMarker(System.Byte[] arr, System.Int32 count);
```

- `public static Decompress(Colossal.AssetPipeline.Native.CompressionFormat format, Unity.Collections.NativeSlice<System.Byte> inCompressedData, Unity.Collections.NativeSlice<System.Byte> outData, Unity.Jobs.JobHandle jobHandle = null) : Unity.Jobs.JobHandle`  

```csharp
public static Unity.Jobs.JobHandle Decompress(Colossal.AssetPipeline.Native.CompressionFormat format, Unity.Collections.NativeSlice<System.Byte> inCompressedData, Unity.Collections.NativeSlice<System.Byte> outData, Unity.Jobs.JobHandle jobHandle);
```

- `public static DecompressZstdWithMarker(System.Byte[] arr) : System.Byte[]`  

```csharp
public static System.Byte[] DecompressZstdWithMarker(System.Byte[] arr);
```

- `public static DecompressZstdWithMarker(Unity.Collections.NativeArray<System.Byte> dst, Unity.Collections.NativeArray<System.Byte> src) : System.Void`  

```csharp
public static System.Void DecompressZstdWithMarker(Unity.Collections.NativeArray<System.Byte> dst, Unity.Collections.NativeArray<System.Byte> src);
```


## Nested types

- `Colossal.Compression.CompressionUtils+EncodeJob`  
- `Colossal.Compression.CompressionUtils+DecodeJob`  

