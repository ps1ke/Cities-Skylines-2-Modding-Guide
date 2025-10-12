# Colossal.Compression.CompressedBytesStorage

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.Compression`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

**Attributes:** `IsReadOnly`  

## Fields

- `private readonly Unity.Collections.NativeArray<System.Byte> m_Data`  

## Properties

- `public Unity.Collections.NativeArray<System.Byte> data { get }`  
- `public System.Int32 size { get }`  

## Constructors

- `public CompressedBytesStorage(Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 sourceDataLength, Unity.Collections.Allocator allocator)`  

## Methods

- `public Dispose() : System.Void`  
- `public Dispose(Unity.Jobs.JobHandle dependency) : System.Void`  
- `public GetBytes() : Unity.Collections.NativeSlice<System.Byte>`  
- `public GetBytes(System.Int32& length) : System.Byte*`  
- `public GetNumBytes() : System.Int32`  

