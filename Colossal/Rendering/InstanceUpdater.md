# Colossal.Rendering.NativeBatchInstances`4+InstanceUpdater

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `GenerateTestsForBurstCompatibility`  

## Code

```csharp
public sealed struct InstanceUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>
{
    internal UnsafeBatches`4* m_BatchData;
    internal Unity.Collections.NativeQueue<Colossal.Rendering.GroupInstanceUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> m_UpdateQueue;

    internal InstanceUpdater(UnsafeBatches`4* batchData, Unity.Collections.Allocator allocator);

    public Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData> AsParallel(System.Int32 maxGroupCount);
    internal Unity.Jobs.JobHandle EndUpdate(Unity.Jobs.JobHandle dependency, Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData> batchInstances, Colossal.Rendering.NativeSubBatches<TCullingData, TGroupData, TBatchData, TInstanceData> subBatches);
}
```


## Fields

- `internal UnsafeBatches`4* m_BatchData`  

```csharp
internal UnsafeBatches`4* m_BatchData;
```

- `internal Unity.Collections.NativeQueue<Colossal.Rendering.GroupInstanceUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> m_UpdateQueue`  

```csharp
internal Unity.Collections.NativeQueue<Colossal.Rendering.GroupInstanceUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> m_UpdateQueue;
```


## Constructors

- `internal InstanceUpdater(UnsafeBatches`4* batchData, Unity.Collections.Allocator allocator)`  

```csharp
internal InstanceUpdater(UnsafeBatches`4* batchData, Unity.Collections.Allocator allocator);
```


## Methods

- `public AsParallel(System.Int32 maxGroupCount) : Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData>`  

```csharp
public Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData> AsParallel(System.Int32 maxGroupCount);
```

- `internal EndUpdate(Unity.Jobs.JobHandle dependency, Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData> batchInstances, Colossal.Rendering.NativeSubBatches<TCullingData, TGroupData, TBatchData, TInstanceData> subBatches) : Unity.Jobs.JobHandle`  

```csharp
internal Unity.Jobs.JobHandle EndUpdate(Unity.Jobs.JobHandle dependency, Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData> batchInstances, Colossal.Rendering.NativeSubBatches<TCullingData, TGroupData, TBatchData, TInstanceData> subBatches);
```


## Nested types

- `Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData>`  

