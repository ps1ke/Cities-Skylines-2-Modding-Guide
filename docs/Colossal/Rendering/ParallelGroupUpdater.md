# Colossal.Rendering.NativeBatchGroups`4+ParallelGroupUpdater

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `NativeContainerSupportsMinMaxWriteRestriction`, `GenerateTestsForBurstCompatibility`  

## Fields

- `internal UnsafeBatches`4* m_BatchData`  
- `internal Unity.Collections.NativeQueue<Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> m_UpdateQueue`  

## Constructors

- `internal ParallelGroupUpdater(UnsafeBatches`4* batchData, Unity.Collections.NativeQueue<Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> updateQueue, System.Int32 length)`  

## Methods

- `public BeginGroup(System.Int32 groupIndex) : Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>`  
- `public EndGroup(Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData> groupUpdater) : System.Void`  

