# Colossal.Rendering.NativeBatchInstances`4+CullingWriter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `GenerateTestsForBurstCompatibility`  

## Code

```csharp
public sealed struct CullingWriter<TCullingData, TGroupData, TBatchData, TInstanceData>
{
    internal UnsafeBatches`4* m_BatchData;
    internal Colossal.Collections.NativeAccumulator<Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData>> m_UploadData;

    internal CullingWriter(UnsafeBatches`4* batchData, Unity.Collections.Allocator allocator);

    public Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData> AsParallel();
    internal Unity.Jobs.JobHandle EndCulling(Unity.Jobs.JobHandle dependency, Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData> batchInstances);
}
```


## Fields

- `internal UnsafeBatches`4* m_BatchData`  

```csharp
internal UnsafeBatches`4* m_BatchData;
```

- `internal Colossal.Collections.NativeAccumulator<Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData>> m_UploadData`  

```csharp
internal Colossal.Collections.NativeAccumulator<Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData>> m_UploadData;
```


## Constructors

- `internal CullingWriter(UnsafeBatches`4* batchData, Unity.Collections.Allocator allocator)`  

```csharp
internal CullingWriter(UnsafeBatches`4* batchData, Unity.Collections.Allocator allocator);
```


## Methods

- `public AsParallel() : Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData>`  

```csharp
public Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData> AsParallel();
```

- `internal EndCulling(Unity.Jobs.JobHandle dependency, Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData> batchInstances) : Unity.Jobs.JobHandle`  

```csharp
internal Unity.Jobs.JobHandle EndCulling(Unity.Jobs.JobHandle dependency, Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData> batchInstances);
```


## Nested types

- `Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData>`  

