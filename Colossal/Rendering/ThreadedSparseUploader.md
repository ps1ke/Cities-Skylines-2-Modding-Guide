# Colossal.Rendering.ThreadedSparseUploader

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ThreadedSparseUploader
{
    internal Colossal.Rendering.ThreadedSparseUploaderData* m_Data;

    public System.Boolean IsValid { get; }

    public System.Void AddMatrixUpload(System.Void* src, System.Int32 numMatrices, System.Int32 offset, Colossal.Rendering.ThreadedSparseUploader+MatrixType srcType, Colossal.Rendering.ThreadedSparseUploader+MatrixType dstType);
    public System.Void AddMatrixUploadAndInverse(System.Void* src, System.Int32 numMatrices, System.Int32 offset, System.Int32 offsetInverse, Colossal.Rendering.ThreadedSparseUploader+MatrixType srcType, Colossal.Rendering.ThreadedSparseUploader+MatrixType dstType);
    public System.Void AddStridedUpload(System.Void* src, System.UInt32 elemSize, System.UInt32 srcStride, System.UInt32 count, System.UInt32 dstOffset, System.Int32 dstStride);
    public System.Void AddUpload(System.Void* src, System.Int32 size, System.Int32 offsetInBytes, System.Int32 repeatCount);
    public System.Void AddUpload<T>(T val, System.Int32 offsetInBytes, System.Int32 repeatCount);
    public System.Void AddUpload<T>(Unity.Collections.NativeArray<T> array, System.Int32 offsetInBytes, System.Int32 repeatCount);
    private System.Void MatrixUploadHelper(System.Void* src, System.Int32 numMatrices, System.Int32 offset, System.Int32 offsetInverse, Colossal.Rendering.ThreadedSparseUploader+MatrixType srcType, Colossal.Rendering.ThreadedSparseUploader+MatrixType dstType);
    private System.Boolean TryAlloc(System.Int32 operationSize, System.Int32 dataSize, System.Byte*& ptr, System.Int32& operationOffset, System.Int32& dataOffset);
}
```


## Fields

- `internal Colossal.Rendering.ThreadedSparseUploaderData* m_Data`  

```csharp
internal Colossal.Rendering.ThreadedSparseUploaderData* m_Data;
```


## Properties

- `public System.Boolean IsValid { get }`  

```csharp
public System.Boolean IsValid { get; }
```


## Methods

- `public AddMatrixUpload(System.Void* src, System.Int32 numMatrices, System.Int32 offset, Colossal.Rendering.ThreadedSparseUploader+MatrixType srcType, Colossal.Rendering.ThreadedSparseUploader+MatrixType dstType) : System.Void`  

```csharp
public System.Void AddMatrixUpload(System.Void* src, System.Int32 numMatrices, System.Int32 offset, Colossal.Rendering.ThreadedSparseUploader+MatrixType srcType, Colossal.Rendering.ThreadedSparseUploader+MatrixType dstType);
```

- `public AddMatrixUploadAndInverse(System.Void* src, System.Int32 numMatrices, System.Int32 offset, System.Int32 offsetInverse, Colossal.Rendering.ThreadedSparseUploader+MatrixType srcType, Colossal.Rendering.ThreadedSparseUploader+MatrixType dstType) : System.Void`  

```csharp
public System.Void AddMatrixUploadAndInverse(System.Void* src, System.Int32 numMatrices, System.Int32 offset, System.Int32 offsetInverse, Colossal.Rendering.ThreadedSparseUploader+MatrixType srcType, Colossal.Rendering.ThreadedSparseUploader+MatrixType dstType);
```

- `public AddStridedUpload(System.Void* src, System.UInt32 elemSize, System.UInt32 srcStride, System.UInt32 count, System.UInt32 dstOffset, System.Int32 dstStride) : System.Void`  

```csharp
public System.Void AddStridedUpload(System.Void* src, System.UInt32 elemSize, System.UInt32 srcStride, System.UInt32 count, System.UInt32 dstOffset, System.Int32 dstStride);
```

- `public AddUpload(System.Void* src, System.Int32 size, System.Int32 offsetInBytes, System.Int32 repeatCount = 1) : System.Void`  

```csharp
public System.Void AddUpload(System.Void* src, System.Int32 size, System.Int32 offsetInBytes, System.Int32 repeatCount);
```

- `public AddUpload<T>(T val, System.Int32 offsetInBytes, System.Int32 repeatCount = 1) : System.Void`  

```csharp
public System.Void AddUpload<T>(T val, System.Int32 offsetInBytes, System.Int32 repeatCount);
```

- `public AddUpload<T>(Unity.Collections.NativeArray<T> array, System.Int32 offsetInBytes, System.Int32 repeatCount = 1) : System.Void`  

```csharp
public System.Void AddUpload<T>(Unity.Collections.NativeArray<T> array, System.Int32 offsetInBytes, System.Int32 repeatCount);
```

- `private MatrixUploadHelper(System.Void* src, System.Int32 numMatrices, System.Int32 offset, System.Int32 offsetInverse, Colossal.Rendering.ThreadedSparseUploader+MatrixType srcType, Colossal.Rendering.ThreadedSparseUploader+MatrixType dstType) : System.Void`  

```csharp
private System.Void MatrixUploadHelper(System.Void* src, System.Int32 numMatrices, System.Int32 offset, System.Int32 offsetInverse, Colossal.Rendering.ThreadedSparseUploader+MatrixType srcType, Colossal.Rendering.ThreadedSparseUploader+MatrixType dstType);
```

- `private TryAlloc(System.Int32 operationSize, System.Int32 dataSize, System.Byte*& ptr, System.Int32& operationOffset, System.Int32& dataOffset) : System.Boolean`  

```csharp
private System.Boolean TryAlloc(System.Int32 operationSize, System.Int32 dataSize, System.Byte*& ptr, System.Int32& operationOffset, System.Int32& dataOffset);
```


## Nested types

- `Colossal.Rendering.ThreadedSparseUploader+MatrixType`  

