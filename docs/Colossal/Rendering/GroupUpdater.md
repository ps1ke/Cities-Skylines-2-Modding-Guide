# Colossal.Rendering.NativeBatchGroups`4+GroupUpdater

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `GenerateTestsForBurstCompatibility`  

## Fields

- `internal UnsafeBatches`4* m_BatchData`  
- `internal Unity.Collections.NativeQueue<Colossal.Rendering.GroupUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> m_UpdateQueue`  

## Constructors

- `internal GroupUpdater(UnsafeBatches`4* batchData, Unity.Collections.Allocator allocator)`  

## Methods

- `public AsParallel(System.Int32 maxGroupCount) : Colossal.Rendering.NativeBatchGroups<TCullingData, TGroupData, TBatchData, TInstanceData>`  
- `internal EndUpdate(Unity.Jobs.JobHandle dependency, Colossal.Rendering.NativeBatchGroups<TCullingData, TGroupData, TBatchData, TInstanceData> batchGroups) : Unity.Jobs.JobHandle`  

## Nested types

- `Colossal.Rendering.NativeBatchGroups<TCullingData, TGroupData, TBatchData, TInstanceData>`  

