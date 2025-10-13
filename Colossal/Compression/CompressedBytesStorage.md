# Colossal.Compression.CompressedBytesStorage

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.Compression`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `System.IDisposable`  

**Attributes:** `IsReadOnly`  

## Code

```csharp
public sealed struct CompressedBytesStorage : System.IDisposable
{
    private readonly Unity.Collections.NativeArray<System.Byte> m_Data;

    public Unity.Collections.NativeArray<System.Byte> data { get; }
    public System.Int32 size { get; }

    public CompressedBytesStorage(Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 sourceDataLength, Unity.Collections.Allocator allocator);

    public System.Void Dispose();
    public System.Void Dispose(Unity.Jobs.JobHandle dependency);
    public Unity.Collections.NativeSlice<System.Byte> GetBytes();
    public System.Byte* GetBytes(System.Int32& length);
    public System.Int32 GetNumBytes();
}
```


## Fields

- `private readonly Unity.Collections.NativeArray<System.Byte> m_Data`  

```csharp
private readonly Unity.Collections.NativeArray<System.Byte> m_Data;
```


## Properties

- `public Unity.Collections.NativeArray<System.Byte> data { get }`  

```csharp
public Unity.Collections.NativeArray<System.Byte> data { get; }
```

- `public System.Int32 size { get }`  

```csharp
public System.Int32 size { get; }
```


## Constructors

- `public CompressedBytesStorage(Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 sourceDataLength, Unity.Collections.Allocator allocator)`  

```csharp
public CompressedBytesStorage(Colossal.AssetPipeline.Native.CompressionFormat format, System.Int32 sourceDataLength, Unity.Collections.Allocator allocator);
```


## Methods

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Dispose(Unity.Jobs.JobHandle dependency) : System.Void`  

```csharp
public System.Void Dispose(Unity.Jobs.JobHandle dependency);
```

- `public GetBytes() : Unity.Collections.NativeSlice<System.Byte>`  

```csharp
public Unity.Collections.NativeSlice<System.Byte> GetBytes();
```

- `public GetBytes(System.Int32& length) : System.Byte*`  

```csharp
public System.Byte* GetBytes(System.Int32& length);
```

- `public GetNumBytes() : System.Int32`  

```csharp
public System.Int32 GetNumBytes();
```


