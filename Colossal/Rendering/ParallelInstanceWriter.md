# Colossal.Rendering.NativeBatchInstances`4+ParallelInstanceWriter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `NativeContainerIsAtomicWriteOnly`, `GenerateTestsForBurstCompatibility`  

## Code

```csharp
public sealed struct ParallelInstanceWriter<TCullingData, TGroupData, TBatchData, TInstanceData>
{
    internal UnsafeBatches`4* m_BatchData;

    internal ParallelInstanceWriter(UnsafeBatches`4* batchData);

    public TCullingData& AccessCullingData(System.Int32 groupIndex, System.Int32 instanceIndex);
    public Colossal.Rendering.WriteableCullingAccessor<TCullingData> GetCullingAccessor(System.Int32 activeGroup);
    public System.Boolean GetPropertyValue<T>(T& value, System.Int32 groupIndex, System.Int32 propertyIndex, System.Int32 instanceIndex);
    public System.Boolean GetTransformValue(System.Int32 groupIndex, System.Int32 instanceIndex, Unity.Mathematics.float3x4& value, Unity.Mathematics.float3x4& secondaryValue);
    public System.Boolean InitializeTransform(System.Int32 groupIndex, System.Int32 instanceIndex, System.Int32 sourceGroupIndex, System.Int32 sourceInstanceIndex);
    public System.Void SetPropertyValue<T>(T value, System.Int32 groupIndex, System.Int32 propertyIndex, System.Int32 instanceIndex);
    public TCullingData& SetTransformValue(Unity.Mathematics.float3x4 value, System.Int32 groupIndex, System.Int32 instanceIndex);
    public TCullingData& SetTransformValue(Unity.Mathematics.float3x4 value, Unity.Mathematics.float3x4 secondaryValue, System.Int32 groupIndex, System.Int32 instanceIndex);
}
```


## Fields

- `internal UnsafeBatches`4* m_BatchData`  

```csharp
internal UnsafeBatches`4* m_BatchData;
```


## Constructors

- `internal ParallelInstanceWriter(UnsafeBatches`4* batchData)`  

```csharp
internal ParallelInstanceWriter(UnsafeBatches`4* batchData);
```


## Methods

- `public AccessCullingData(System.Int32 groupIndex, System.Int32 instanceIndex) : TCullingData&`  

```csharp
public TCullingData& AccessCullingData(System.Int32 groupIndex, System.Int32 instanceIndex);
```

- `public GetCullingAccessor(System.Int32 activeGroup) : Colossal.Rendering.WriteableCullingAccessor<TCullingData>`  

```csharp
public Colossal.Rendering.WriteableCullingAccessor<TCullingData> GetCullingAccessor(System.Int32 activeGroup);
```

- `public GetPropertyValue<T>(T& value, System.Int32 groupIndex, System.Int32 propertyIndex, System.Int32 instanceIndex) : System.Boolean`  

```csharp
public System.Boolean GetPropertyValue<T>(T& value, System.Int32 groupIndex, System.Int32 propertyIndex, System.Int32 instanceIndex);
```

- `public GetTransformValue(System.Int32 groupIndex, System.Int32 instanceIndex, Unity.Mathematics.float3x4& value, Unity.Mathematics.float3x4& secondaryValue) : System.Boolean`  

```csharp
public System.Boolean GetTransformValue(System.Int32 groupIndex, System.Int32 instanceIndex, Unity.Mathematics.float3x4& value, Unity.Mathematics.float3x4& secondaryValue);
```

- `public InitializeTransform(System.Int32 groupIndex, System.Int32 instanceIndex, System.Int32 sourceGroupIndex, System.Int32 sourceInstanceIndex) : System.Boolean`  

```csharp
public System.Boolean InitializeTransform(System.Int32 groupIndex, System.Int32 instanceIndex, System.Int32 sourceGroupIndex, System.Int32 sourceInstanceIndex);
```

- `public SetPropertyValue<T>(T value, System.Int32 groupIndex, System.Int32 propertyIndex, System.Int32 instanceIndex) : System.Void`  

```csharp
public System.Void SetPropertyValue<T>(T value, System.Int32 groupIndex, System.Int32 propertyIndex, System.Int32 instanceIndex);
```

- `public SetTransformValue(Unity.Mathematics.float3x4 value, System.Int32 groupIndex, System.Int32 instanceIndex) : TCullingData&`  

```csharp
public TCullingData& SetTransformValue(Unity.Mathematics.float3x4 value, System.Int32 groupIndex, System.Int32 instanceIndex);
```

- `public SetTransformValue(Unity.Mathematics.float3x4 value, Unity.Mathematics.float3x4 secondaryValue, System.Int32 groupIndex, System.Int32 instanceIndex) : TCullingData&`  

```csharp
public TCullingData& SetTransformValue(Unity.Mathematics.float3x4 value, Unity.Mathematics.float3x4 secondaryValue, System.Int32 groupIndex, System.Int32 instanceIndex);
```


