# Colossal.Compression.CompressionUtils

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.Compression`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `private static const System.Int32 kMagicNumber`  

## Methods

- `public static CalcMaxCompressedSize(Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 length) : System.Int32`  
- `public static Compress(Colossal.AssetPipeline.Native.CompressionFormat format, Unity.Collections.NativeSlice<System.Byte> inData, Colossal.Compression.CompressedBytesStorage outCompressedData, Unity.Jobs.JobHandle jobHandle = null, System.Int32 compressionLevel = 1) : Unity.Jobs.JobHandle`  
- `public static CompressZstdWithMarker(System.Byte[] arr, System.Int32 count) : System.Byte[]`  
- `public static Decompress(Colossal.AssetPipeline.Native.CompressionFormat format, Unity.Collections.NativeSlice<System.Byte> inCompressedData, Unity.Collections.NativeSlice<System.Byte> outData, Unity.Jobs.JobHandle jobHandle = null) : Unity.Jobs.JobHandle`  
- `public static DecompressZstdWithMarker(System.Byte[] arr) : System.Byte[]`  
- `public static DecompressZstdWithMarker(Unity.Collections.NativeArray<System.Byte> dst, Unity.Collections.NativeArray<System.Byte> src) : System.Void`  

## Nested types

- `Colossal.Compression.CompressionUtils+EncodeJob`  
- `Colossal.Compression.CompressionUtils+DecodeJob`  

