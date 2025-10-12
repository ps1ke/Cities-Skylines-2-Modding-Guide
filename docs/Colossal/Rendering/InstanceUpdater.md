# Colossal.Rendering.NativeBatchInstances`4+InstanceUpdater

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `GenerateTestsForBurstCompatibility`  

## Fields

- `internal UnsafeBatches`4* m_BatchData`  
- `internal Unity.Collections.NativeQueue<Colossal.Rendering.GroupInstanceUpdater<TCullingData, TGroupData, TBatchData, TInstanceData>> m_UpdateQueue`  

## Constructors

- `internal InstanceUpdater(UnsafeBatches`4* batchData, Unity.Collections.Allocator allocator)`  

## Methods

- `public AsParallel(System.Int32 maxGroupCount) : Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData>`  
- `internal EndUpdate(Unity.Jobs.JobHandle dependency, Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData> batchInstances, Colossal.Rendering.NativeSubBatches<TCullingData, TGroupData, TBatchData, TInstanceData> subBatches) : Unity.Jobs.JobHandle`  

## Nested types

- `Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData>`  

