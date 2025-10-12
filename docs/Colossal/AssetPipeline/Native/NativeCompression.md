# Colossal.AssetPipeline.Native.NativeCompression

**Assembly:** `Colossal.AssetPipeline.Native`  
**Namespace:** `Colossal.AssetPipeline.Native`  

**Type:** class static public  

**Base:** `System.Object`  

## Methods

- `public static CompressCalcBound(System.Int64 srcSize, Colossal.AssetPipeline.Native.CompressionFormat format) : System.Int64`  
- `public static CompressData(System.IntPtr src, System.Int64 srcSize, System.IntPtr dst, System.Int64 dstSize, Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 level) : System.Int64`  
- `public static CompressMeshoptIndexBuffer(System.IntPtr src, System.Int32 indexCount, System.IntPtr dst, System.Int64 dstSize) : System.Int64`  
- `public static CompressMeshoptIndexBufferBound(System.Int32 indexCount, System.Int32 vertexCount) : System.Int64`  
- `public static CompressMeshoptVertexAttr(System.IntPtr src, System.Int32 vertexCount, System.Int32 vertexSize, System.IntPtr dst, System.Int64 dstSize) : System.Int64`  
- `public static CompressMeshoptVertexAttrBound(System.Int32 vertexCount, System.Int32 vertexSize) : System.Int64`  
- `public static DecompressCalcBound(System.IntPtr src, System.Int64 srcSize, Colossal.AssetPipeline.Native.CompressionFormat format) : System.Int64`  
- `public static DecompressData(System.IntPtr src, System.Int64 srcSize, System.IntPtr dst, System.Int64 dstSize, Colossal.AssetPipeline.Native.CompressionFormat format) : System.Int64`  
- `public static DecompressMeshoptIndexBuffer(System.IntPtr src, System.Int64 srcSize, System.Int32 indexCount, System.Int32 indexSize, System.IntPtr dst) : System.Int32`  
- `public static DecompressMeshoptVertexAttr(System.IntPtr src, System.Int64 srcSize, System.Int32 vertexCount, System.Int32 vertexSize, System.IntPtr dst) : System.Int32`  
- `public static FilterDataBeforeWrite(System.IntPtr src, System.IntPtr dst, System.Int64 dataSize, System.Int32 dataStride) : System.Void`  
- `public static UnfilterDataAfterRead(System.IntPtr src, System.IntPtr dst, System.Int64 dataSize, System.Int32 dataStride) : System.Void`  

