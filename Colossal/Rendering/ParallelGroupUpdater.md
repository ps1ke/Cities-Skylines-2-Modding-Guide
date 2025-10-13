# Colossal.Rendering.NativeBatchGroups`4+ParallelGroupUpdater

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `NativeContainerSupportsMinMaxWriteRestriction`, `GenerateTestsForBurstCompatibility`  

## Code

```csharp
public sealed struct ParallelGroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>
{
    internal UnsafeBatches`4* m_BatchData;
    internal Unity.Collections.NativeQueue<Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> m_UpdateQueue;

    internal ParallelGroupUpdater(UnsafeBatches`4* batchData, Unity.Collections.NativeQueue<Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> updateQueue, System.Int32 length);

    public Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData> BeginGroup(System.Int32 groupIndex);
    public System.Void EndGroup(Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData> groupUpdater);
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

- `internal ParallelGroupUpdater(UnsafeBatches`4* batchData, Unity.Collections.NativeQueue<Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> updateQueue, System.Int32 length)`  

```csharp
internal ParallelGroupUpdater(UnsafeBatches`4* batchData, Unity.Collections.NativeQueue<Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> updateQueue, System.Int32 length);
```


## Methods

- `public BeginGroup(System.Int32 groupIndex) : Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>`  

```csharp
public Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData> BeginGroup(System.Int32 groupIndex);
```

- `public EndGroup(Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData> groupUpdater) : System.Void`  

```csharp
public System.Void EndGroup(Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData> groupUpdater);
```


