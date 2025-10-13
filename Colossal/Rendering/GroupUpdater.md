# Colossal.Rendering.NativeBatchGroups`4+GroupUpdater

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `GenerateTestsForBurstCompatibility`  

## Code

```csharp
public sealed struct GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>
{
    internal UnsafeBatches`4* m_BatchData;
    internal Unity.Collections.NativeQueue<Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> m_UpdateQueue;

    internal GroupUpdater(UnsafeBatches`4* batchData, Unity.Collections.Allocator allocator);

    public Colossal.Rendering.NativeBatchGroups<TCullingData, TGroupData, TBatchData, TInstanceData> AsParallel(System.Int32 maxGroupCount);
    internal Unity.Jobs.JobHandle EndUpdate(Unity.Jobs.JobHandle dependency, Colossal.Rendering.NativeBatchGroups<TCullingData, TGroupData, TBatchData, TInstanceData> batchGroups);
}
```


## Fields

- `internal UnsafeBatches`4* m_BatchData`  

```csharp
internal UnsafeBatches`4* m_BatchData;
```

- `internal Unity.Collections.NativeQueue<Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> m_UpdateQueue`  

```csharp
internal Unity.Collections.NativeQueue<Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> m_UpdateQueue;
```


## Constructors

- `internal GroupUpdater(UnsafeBatches`4* batchData, Unity.Collections.Allocator allocator)`  

```csharp
internal GroupUpdater(UnsafeBatches`4* batchData, Unity.Collections.Allocator allocator);
```


## Methods

- `public AsParallel(System.Int32 maxGroupCount) : Colossal.Rendering.NativeBatchGroups<TCullingData, TGroupData, TBatchData, TInstanceData>`  

```csharp
public Colossal.Rendering.NativeBatchGroups<TCullingData, TGroupData, TBatchData, TInstanceData> AsParallel(System.Int32 maxGroupCount);
```

- `internal EndUpdate(Unity.Jobs.JobHandle dependency, Colossal.Rendering.NativeBatchGroups<TCullingData, TGroupData, TBatchData, TInstanceData> batchGroups) : Unity.Jobs.JobHandle`  

```csharp
internal Unity.Jobs.JobHandle EndUpdate(Unity.Jobs.JobHandle dependency, Colossal.Rendering.NativeBatchGroups<TCullingData, TGroupData, TBatchData, TInstanceData> batchGroups);
```


## Nested types

- `Colossal.Rendering.NativeBatchGroups<TCullingData, TGroupData, TBatchData, TInstanceData>`  

