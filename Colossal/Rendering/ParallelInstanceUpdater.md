# Colossal.Rendering.NativeBatchInstances`4+ParallelInstanceUpdater

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `NativeContainerSupportsMinMaxWriteRestriction`, `GenerateTestsForBurstCompatibility`  

## Code

```csharp
public sealed struct ParallelInstanceUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>
{
    internal UnsafeBatches`4* m_BatchData;
    internal Unity.Collections.NativeQueue<Colossal.Rendering.GroupInstanceUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> m_UpdateQueue;

    internal ParallelInstanceUpdater(UnsafeBatches`4* batchData, Unity.Collections.NativeQueue<Colossal.Rendering.GroupInstanceUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> updateQueue, System.Int32 length);

    public Colossal.Rendering.GroupInstanceUpdater<TCullingData, TGroupData, TBatchData, TInstanceData> BeginGroup(System.Int32 groupIndex);
    public System.Void EndGroup(Colossal.Rendering.GroupInstanceUpdater<TCullingData, TGroupData, TBatchData, TInstanceData> groupInstanceUpdater);
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

- `internal ParallelInstanceUpdater(UnsafeBatches`4* batchData, Unity.Collections.NativeQueue<Colossal.Rendering.GroupInstanceUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> updateQueue, System.Int32 length)`  

```csharp
internal ParallelInstanceUpdater(UnsafeBatches`4* batchData, Unity.Collections.NativeQueue<Colossal.Rendering.GroupInstanceUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> updateQueue, System.Int32 length);
```


## Methods

- `public BeginGroup(System.Int32 groupIndex) : Colossal.Rendering.GroupInstanceUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>`  

```csharp
public Colossal.Rendering.GroupInstanceUpdater<TCullingData, TGroupData, TBatchData, TInstanceData> BeginGroup(System.Int32 groupIndex);
```

- `public EndGroup(Colossal.Rendering.GroupInstanceUpdater<TCullingData, TGroupData, TBatchData, TInstanceData> groupInstanceUpdater) : System.Void`  

```csharp
public System.Void EndGroup(Colossal.Rendering.GroupInstanceUpdater<TCullingData, TGroupData, TBatchData, TInstanceData> groupInstanceUpdater);
```


