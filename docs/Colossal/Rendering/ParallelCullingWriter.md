# Colossal.Rendering.NativeBatchInstances`4+ParallelCullingWriter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `NativeContainerSupportsMinMaxWriteRestriction`, `GenerateTestsForBurstCompatibility`  

## Fields

- `internal UnsafeBatches`4* m_BatchData`  
- `internal Colossal.Collections.NativeAccumulator<Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData>> m_UploadData`  

## Constructors

- `internal ParallelCullingWriter(UnsafeBatches`4* batchData, Colossal.Collections.NativeAccumulator<Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData>> uploadData, System.Int32 length)`  

## Methods

- `public GetCullingAccessor(System.Int32 activeGroup) : Colossal.Rendering.WriteableCullingAccessor<TCullingData>`  
- `public GetGroupIndex(System.Int32 activeGroup) : System.Int32`  
- `public GetMergeIndexAccessor(System.Int32 groupIndex) : Colossal.Rendering.MergeIndexAccessor`  
- `public GetPropertyAccessor(System.Int32 activeGroup, System.Int32 propertyIndex) : Colossal.Rendering.WriteablePropertyAccessor<TCullingData, TGroupData, TBatchData, TInstanceData>`  
- `public UpdateCulling(System.Int32 activeGroup, Unity.Mathematics.float3 boundsCenter, Unity.Mathematics.float3 boundsExtents, Unity.Mathematics.float3 shadowBoundsCenter, Unity.Mathematics.float3 shadowBoundsExtents, System.Boolean useSecondaryMatrix = False) : System.Void`  

