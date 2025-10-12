# Colossal.IO.AssetDatabase.VirtualTexturing.ReadAndDecompressHandle

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Fields

- `private Unity.Jobs.JobHandle m_DecompressionHandle`  
- `private Unity.IO.LowLevel.Unsafe.ReadHandle m_ReadHandle`  
- `private Unity.Collections.NativeArray<System.Byte> m_CompressedBuffer`  
- `private Unity.Collections.NativeArray<Colossal.IO.AssetDatabase.VirtualTexturing.LayerBuffer> m_LayerDataPtr`  

## Constructors

- `public ReadAndDecompressHandle(Unity.IO.LowLevel.Unsafe.ReadHandle mReadHandle, Colossal.IO.AssetDatabase.VirtualTexturing.ReadAndDecompressCommand cmd, Unity.Collections.NativeArray<System.Byte> compressedBuffer)`  

## Methods

- `public Complete() : System.Void`  
- `public Dispose() : System.Void`  
- `public IsValid() : System.Boolean`  
- `public Status() : Unity.IO.LowLevel.Unsafe.ReadStatus`  

