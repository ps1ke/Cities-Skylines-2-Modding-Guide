# Colossal.IO.AssetDatabase.VirtualTexturing.ReadAndDecompressHandle

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

## Code

```csharp
public sealed struct ReadAndDecompressHandle : System.IDisposable
{
    private Unity.Jobs.JobHandle m_DecompressionHandle;
    private Unity.IO.LowLevel.Unsafe.ReadHandle m_ReadHandle;
    private Unity.Collections.NativeArray<System.Byte> m_CompressedBuffer;
    private Unity.Collections.NativeArray<Colossal.IO.AssetDatabase.VirtualTexturing.LayerBuffer> m_LayerDataPtr;

    public ReadAndDecompressHandle(Unity.IO.LowLevel.Unsafe.ReadHandle mReadHandle, Colossal.IO.AssetDatabase.VirtualTexturing.ReadAndDecompressCommand cmd, Unity.Collections.NativeArray<System.Byte> compressedBuffer);

    public System.Void Complete();
    public System.Void Dispose();
    public System.Boolean IsValid();
    public Unity.IO.LowLevel.Unsafe.ReadStatus Status();
}
```


## Fields

- `private Unity.Jobs.JobHandle m_DecompressionHandle`  

```csharp
private Unity.Jobs.JobHandle m_DecompressionHandle;
```

- `private Unity.IO.LowLevel.Unsafe.ReadHandle m_ReadHandle`  

```csharp
private Unity.IO.LowLevel.Unsafe.ReadHandle m_ReadHandle;
```

- `private Unity.Collections.NativeArray<System.Byte> m_CompressedBuffer`  

```csharp
private Unity.Collections.NativeArray<System.Byte> m_CompressedBuffer;
```

- `private Unity.Collections.NativeArray<Colossal.IO.AssetDatabase.VirtualTexturing.LayerBuffer> m_LayerDataPtr`  

```csharp
private Unity.Collections.NativeArray<Colossal.IO.AssetDatabase.VirtualTexturing.LayerBuffer> m_LayerDataPtr;
```


## Constructors

- `public ReadAndDecompressHandle(Unity.IO.LowLevel.Unsafe.ReadHandle mReadHandle, Colossal.IO.AssetDatabase.VirtualTexturing.ReadAndDecompressCommand cmd, Unity.Collections.NativeArray<System.Byte> compressedBuffer)`  

```csharp
public ReadAndDecompressHandle(Unity.IO.LowLevel.Unsafe.ReadHandle mReadHandle, Colossal.IO.AssetDatabase.VirtualTexturing.ReadAndDecompressCommand cmd, Unity.Collections.NativeArray<System.Byte> compressedBuffer);
```


## Methods

- `public Complete() : System.Void`  

```csharp
public System.Void Complete();
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public IsValid() : System.Boolean`  

```csharp
public System.Boolean IsValid();
```

- `public Status() : Unity.IO.LowLevel.Unsafe.ReadStatus`  

```csharp
public Unity.IO.LowLevel.Unsafe.ReadStatus Status();
```


