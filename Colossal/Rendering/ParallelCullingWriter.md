# Colossal.Rendering.NativeBatchInstances`4+ParallelCullingWriter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `NativeContainerSupportsMinMaxWriteRestriction`, `GenerateTestsForBurstCompatibility`  

## Code

```csharp
public sealed struct ParallelCullingWriter<TCullingData, TGroupData, TBatchData, TInstanceData>
{
    internal UnsafeBatches`4* m_BatchData;
    internal Colossal.Collections.NativeAccumulator<Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData>> m_UploadData;

    internal ParallelCullingWriter(UnsafeBatches`4* batchData, Colossal.Collections.NativeAccumulator<Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData>> uploadData, System.Int32 length);

    public Colossal.Rendering.WriteableCullingAccessor<TCullingData> GetCullingAccessor(System.Int32 activeGroup);
    public System.Int32 GetGroupIndex(System.Int32 activeGroup);
    public Colossal.Rendering.MergeIndexAccessor GetMergeIndexAccessor(System.Int32 groupIndex);
    public Colossal.Rendering.WriteablePropertyAccessor<TCullingData, TGroupData, TBatchData, TInstanceData> GetPropertyAccessor(System.Int32 activeGroup, System.Int32 propertyIndex);
    public System.Void UpdateCulling(System.Int32 activeGroup, Unity.Mathematics.float3 boundsCenter, Unity.Mathematics.float3 boundsExtents, Unity.Mathematics.float3 shadowBoundsCenter, Unity.Mathematics.float3 shadowBoundsExtents, System.Boolean useSecondaryMatrix);
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

- `internal ParallelCullingWriter(UnsafeBatches`4* batchData, Colossal.Collections.NativeAccumulator<Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData>> uploadData, System.Int32 length)`  

```csharp
internal ParallelCullingWriter(UnsafeBatches`4* batchData, Colossal.Collections.NativeAccumulator<Colossal.Rendering.NativeBatchInstances<TCullingData, TGroupData, TBatchData, TInstanceData>> uploadData, System.Int32 length);
```


## Methods

- `public GetCullingAccessor(System.Int32 activeGroup) : Colossal.Rendering.WriteableCullingAccessor<TCullingData>`  

```csharp
public Colossal.Rendering.WriteableCullingAccessor<TCullingData> GetCullingAccessor(System.Int32 activeGroup);
```

- `public GetGroupIndex(System.Int32 activeGroup) : System.Int32`  

```csharp
public System.Int32 GetGroupIndex(System.Int32 activeGroup);
```

- `public GetMergeIndexAccessor(System.Int32 groupIndex) : Colossal.Rendering.MergeIndexAccessor`  

```csharp
public Colossal.Rendering.MergeIndexAccessor GetMergeIndexAccessor(System.Int32 groupIndex);
```

- `public GetPropertyAccessor(System.Int32 activeGroup, System.Int32 propertyIndex) : Colossal.Rendering.WriteablePropertyAccessor<TCullingData, TGroupData, TBatchData, TInstanceData>`  

```csharp
public Colossal.Rendering.WriteablePropertyAccessor<TCullingData, TGroupData, TBatchData, TInstanceData> GetPropertyAccessor(System.Int32 activeGroup, System.Int32 propertyIndex);
```

- `public UpdateCulling(System.Int32 activeGroup, Unity.Mathematics.float3 boundsCenter, Unity.Mathematics.float3 boundsExtents, Unity.Mathematics.float3 shadowBoundsCenter, Unity.Mathematics.float3 shadowBoundsExtents, System.Boolean useSecondaryMatrix = False) : System.Void`  

```csharp
public System.Void UpdateCulling(System.Int32 activeGroup, Unity.Mathematics.float3 boundsCenter, Unity.Mathematics.float3 boundsExtents, Unity.Mathematics.float3 shadowBoundsCenter, Unity.Mathematics.float3 shadowBoundsExtents, System.Boolean useSecondaryMatrix);
```


