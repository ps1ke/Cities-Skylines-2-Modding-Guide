# Colossal.Rendering.NativeBatchInstances`4+ParallelUploadWriter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `NativeContainerSupportsMinMaxWriteRestriction`, `GenerateTestsForBurstCompatibility`  

## Fields

- `internal UnsafeBatches`4* m_BatchData`  

## Constructors

- `internal ParallelUploadWriter(UnsafeBatches`4* batchData, System.Int32 length)`  

## Methods

- `internal EndUpload(Unity.Jobs.JobHandle dependency, Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData> batchInstances) : Unity.Jobs.JobHandle`  
- `public GetGroupIndex(System.Int32 activeGroup) : System.Int32`  
- `public UploadInstances(System.Int32 activeGroup) : System.Void`  

## Nested types

- `Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData>`  

