# Colossal.Rendering.ThreadedSparseUploader

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `internal Colossal.Rendering.ThreadedSparseUploaderData* m_Data`  

## Properties

- `public System.Boolean IsValid { get }`  

## Methods

- `public AddMatrixUpload(System.Void* src, System.Int32 numMatrices, System.Int32 offset, Colossal.Rendering.ThreadedSparseUploader+MatrixType srcType, Colossal.Rendering.ThreadedSparseUploader+MatrixType dstType) : System.Void`  
- `public AddMatrixUploadAndInverse(System.Void* src, System.Int32 numMatrices, System.Int32 offset, System.Int32 offsetInverse, Colossal.Rendering.ThreadedSparseUploader+MatrixType srcType, Colossal.Rendering.ThreadedSparseUploader+MatrixType dstType) : System.Void`  
- `public AddStridedUpload(System.Void* src, System.UInt32 elemSize, System.UInt32 srcStride, System.UInt32 count, System.UInt32 dstOffset, System.Int32 dstStride) : System.Void`  
- `public AddUpload(System.Void* src, System.Int32 size, System.Int32 offsetInBytes, System.Int32 repeatCount = 1) : System.Void`  
- `public AddUpload<T>(T val, System.Int32 offsetInBytes, System.Int32 repeatCount = 1) : System.Void`  
- `public AddUpload<T>(Unity.Collections.NativeArray<T> array, System.Int32 offsetInBytes, System.Int32 repeatCount = 1) : System.Void`  
- `private MatrixUploadHelper(System.Void* src, System.Int32 numMatrices, System.Int32 offset, System.Int32 offsetInverse, Colossal.Rendering.ThreadedSparseUploader+MatrixType srcType, Colossal.Rendering.ThreadedSparseUploader+MatrixType dstType) : System.Void`  
- `private TryAlloc(System.Int32 operationSize, System.Int32 dataSize, System.Byte*& ptr, System.Int32& operationOffset, System.Int32& dataOffset) : System.Boolean`  

## Nested types

- `Colossal.Rendering.ThreadedSparseUploader+MatrixType`  

