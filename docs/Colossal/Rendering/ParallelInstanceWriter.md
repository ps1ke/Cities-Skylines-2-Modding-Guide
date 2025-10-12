# Colossal.Rendering.NativeBatchInstances`4+ParallelInstanceWriter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

**Attributes:** `NativeContainer`, `NativeContainerIsAtomicWriteOnly`, `GenerateTestsForBurstCompatibility`  

## Fields

- `internal UnsafeBatches`4* m_BatchData`  

## Constructors

- `internal ParallelInstanceWriter(UnsafeBatches`4* batchData)`  

## Methods

- `public AccessCullingData(System.Int32 groupIndex, System.Int32 instanceIndex) : TCullingData&`  
- `public GetCullingAccessor(System.Int32 activeGroup) : Colossal.Rendering.WriteableCullingAccessor<TCullingData>`  
- `public GetPropertyValue<T>(T& value, System.Int32 groupIndex, System.Int32 propertyIndex, System.Int32 instanceIndex) : System.Boolean`  
- `public GetTransformValue(System.Int32 groupIndex, System.Int32 instanceIndex, Unity.Mathematics.float3x4& value, Unity.Mathematics.float3x4& secondaryValue) : System.Boolean`  
- `public InitializeTransform(System.Int32 groupIndex, System.Int32 instanceIndex, System.Int32 sourceGroupIndex, System.Int32 sourceInstanceIndex) : System.Boolean`  
- `public SetPropertyValue<T>(T value, System.Int32 groupIndex, System.Int32 propertyIndex, System.Int32 instanceIndex) : System.Void`  
- `public SetTransformValue(Unity.Mathematics.float3x4 value, System.Int32 groupIndex, System.Int32 instanceIndex) : TCullingData&`  
- `public SetTransformValue(Unity.Mathematics.float3x4 value, Unity.Mathematics.float3x4 secondaryValue, System.Int32 groupIndex, System.Int32 instanceIndex) : TCullingData&`  

