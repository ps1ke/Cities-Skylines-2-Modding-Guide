# Colossal.Rendering.NativeBatchInstances`4+ParallelUploadWriter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `NativeContainerSupportsMinMaxWriteRestriction`, `GenerateTestsForBurstCompatibility`  

## Code

```csharp
public sealed struct ParallelUploadWriter<TCullingData, TGroupData, TBatchData, TInstanceData>
{
    internal UnsafeBatches`4* m_BatchData;

    internal ParallelUploadWriter(UnsafeBatches`4* batchData, System.Int32 length);

    internal Unity.Jobs.JobHandle EndUpload(Unity.Jobs.JobHandle dependency, Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData> batchInstances);
    public System.Int32 GetGroupIndex(System.Int32 activeGroup);
    public System.Void UploadInstances(System.Int32 activeGroup);
}
```


## Fields

- `internal UnsafeBatches`4* m_BatchData`  

```csharp
internal UnsafeBatches`4* m_BatchData;
```


## Constructors

- `internal ParallelUploadWriter(UnsafeBatches`4* batchData, System.Int32 length)`  

```csharp
internal ParallelUploadWriter(UnsafeBatches`4* batchData, System.Int32 length);
```


## Methods

- `internal EndUpload(Unity.Jobs.JobHandle dependency, Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData> batchInstances) : Unity.Jobs.JobHandle`  

```csharp
internal Unity.Jobs.JobHandle EndUpload(Unity.Jobs.JobHandle dependency, Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData> batchInstances);
```

- `public GetGroupIndex(System.Int32 activeGroup) : System.Int32`  

```csharp
public System.Int32 GetGroupIndex(System.Int32 activeGroup);
```

- `public UploadInstances(System.Int32 activeGroup) : System.Void`  

```csharp
public System.Void UploadInstances(System.Int32 activeGroup);
```


## Nested types

- `Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData>`  

