# Colossal.AssetPipeline.Native.NativeCompression

**Assembly:** `Colossal.AssetPipeline.Native`  
**Namespace:** `Colossal.AssetPipeline.Native`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class NativeCompression
{
    public static System.Int64 CompressCalcBound(System.Int64 srcSize, Colossal.AssetPipeline.Native.CompressionFormat format);
    public static System.Int64 CompressData(System.IntPtr src, System.Int64 srcSize, System.IntPtr dst, System.Int64 dstSize, Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 level);
    public static System.Int64 CompressMeshoptIndexBuffer(System.IntPtr src, System.Int32 indexCount, System.IntPtr dst, System.Int64 dstSize);
    public static System.Int64 CompressMeshoptIndexBufferBound(System.Int32 indexCount, System.Int32 vertexCount);
    public static System.Int64 CompressMeshoptVertexAttr(System.IntPtr src, System.Int32 vertexCount, System.Int32 vertexSize, System.IntPtr dst, System.Int64 dstSize);
    public static System.Int64 CompressMeshoptVertexAttrBound(System.Int32 vertexCount, System.Int32 vertexSize);
    public static System.Int64 DecompressCalcBound(System.IntPtr src, System.Int64 srcSize, Colossal.AssetPipeline.Native.CompressionFormat format);
    public static System.Int64 DecompressData(System.IntPtr src, System.Int64 srcSize, System.IntPtr dst, System.Int64 dstSize, Colossal.AssetPipeline.Native.CompressionFormat format);
    public static System.Int32 DecompressMeshoptIndexBuffer(System.IntPtr src, System.Int64 srcSize, System.Int32 indexCount, System.Int32 indexSize, System.IntPtr dst);
    public static System.Int32 DecompressMeshoptVertexAttr(System.IntPtr src, System.Int64 srcSize, System.Int32 vertexCount, System.Int32 vertexSize, System.IntPtr dst);
    public static System.Void FilterDataBeforeWrite(System.IntPtr src, System.IntPtr dst, System.Int64 dataSize, System.Int32 dataStride);
    public static System.Void UnfilterDataAfterRead(System.IntPtr src, System.IntPtr dst, System.Int64 dataSize, System.Int32 dataStride);
}
```


## Methods

- `public static CompressCalcBound(System.Int64 srcSize, Colossal.AssetPipeline.Native.CompressionFormat format) : System.Int64`  

```csharp
public static System.Int64 CompressCalcBound(System.Int64 srcSize, Colossal.AssetPipeline.Native.CompressionFormat format);
```

- `public static CompressData(System.IntPtr src, System.Int64 srcSize, System.IntPtr dst, System.Int64 dstSize, Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 level) : System.Int64`  

```csharp
public static System.Int64 CompressData(System.IntPtr src, System.Int64 srcSize, System.IntPtr dst, System.Int64 dstSize, Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 level);
```

- `public static CompressMeshoptIndexBuffer(System.IntPtr src, System.Int32 indexCount, System.IntPtr dst, System.Int64 dstSize) : System.Int64`  

```csharp
public static System.Int64 CompressMeshoptIndexBuffer(System.IntPtr src, System.Int32 indexCount, System.IntPtr dst, System.Int64 dstSize);
```

- `public static CompressMeshoptIndexBufferBound(System.Int32 indexCount, System.Int32 vertexCount) : System.Int64`  

```csharp
public static System.Int64 CompressMeshoptIndexBufferBound(System.Int32 indexCount, System.Int32 vertexCount);
```

- `public static CompressMeshoptVertexAttr(System.IntPtr src, System.Int32 vertexCount, System.Int32 vertexSize, System.IntPtr dst, System.Int64 dstSize) : System.Int64`  

```csharp
public static System.Int64 CompressMeshoptVertexAttr(System.IntPtr src, System.Int32 vertexCount, System.Int32 vertexSize, System.IntPtr dst, System.Int64 dstSize);
```

- `public static CompressMeshoptVertexAttrBound(System.Int32 vertexCount, System.Int32 vertexSize) : System.Int64`  

```csharp
public static System.Int64 CompressMeshoptVertexAttrBound(System.Int32 vertexCount, System.Int32 vertexSize);
```

- `public static DecompressCalcBound(System.IntPtr src, System.Int64 srcSize, Colossal.AssetPipeline.Native.CompressionFormat format) : System.Int64`  

```csharp
public static System.Int64 DecompressCalcBound(System.IntPtr src, System.Int64 srcSize, Colossal.AssetPipeline.Native.CompressionFormat format);
```

- `public static DecompressData(System.IntPtr src, System.Int64 srcSize, System.IntPtr dst, System.Int64 dstSize, Colossal.AssetPipeline.Native.CompressionFormat format) : System.Int64`  

```csharp
public static System.Int64 DecompressData(System.IntPtr src, System.Int64 srcSize, System.IntPtr dst, System.Int64 dstSize, Colossal.AssetPipeline.Native.CompressionFormat format);
```

- `public static DecompressMeshoptIndexBuffer(System.IntPtr src, System.Int64 srcSize, System.Int32 indexCount, System.Int32 indexSize, System.IntPtr dst) : System.Int32`  

```csharp
public static System.Int32 DecompressMeshoptIndexBuffer(System.IntPtr src, System.Int64 srcSize, System.Int32 indexCount, System.Int32 indexSize, System.IntPtr dst);
```

- `public static DecompressMeshoptVertexAttr(System.IntPtr src, System.Int64 srcSize, System.Int32 vertexCount, System.Int32 vertexSize, System.IntPtr dst) : System.Int32`  

```csharp
public static System.Int32 DecompressMeshoptVertexAttr(System.IntPtr src, System.Int64 srcSize, System.Int32 vertexCount, System.Int32 vertexSize, System.IntPtr dst);
```

- `public static FilterDataBeforeWrite(System.IntPtr src, System.IntPtr dst, System.Int64 dataSize, System.Int32 dataStride) : System.Void`  

```csharp
public static System.Void FilterDataBeforeWrite(System.IntPtr src, System.IntPtr dst, System.Int64 dataSize, System.Int32 dataStride);
```

- `public static UnfilterDataAfterRead(System.IntPtr src, System.IntPtr dst, System.Int64 dataSize, System.Int32 dataStride) : System.Void`  

```csharp
public static System.Void UnfilterDataAfterRead(System.IntPtr src, System.IntPtr dst, System.Int64 dataSize, System.Int32 dataStride);
```


