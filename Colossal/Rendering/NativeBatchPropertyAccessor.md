# Colossal.Rendering.NativeBatchPropertyAccessor

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct NativeBatchPropertyAccessor
{
    internal Unity.Collections.LowLevel.Unsafe.UnsafeParallelHashMap<System.Int32, System.UInt32> m_GlobalOffsets;
    internal Colossal.Rendering.UnsafeGroupProperty* m_GroupPropertyPtr;
    internal Colossal.Rendering.UnsafeBatchProperty* m_BatchPropertyPtr;
    internal System.Int32* m_GroupPropertyIndicesPtr;
    internal System.UInt32 m_ZeroAllocation;
    internal System.UInt32 m_GlobalAllocation;
    internal System.UInt32 m_BatchAllocation;
    internal System.Int32 m_BatchPropertyCount;

    public System.Int32 PropertyCount { get; }

    public UnityEngine.Rendering.MetadataValue GetMetaData(System.Int32 index, System.UInt32& batchPropertySize);
}
```


## Fields

- `internal Unity.Collections.LowLevel.Unsafe.UnsafeParallelHashMap<System.Int32, System.UInt32> m_GlobalOffsets`  

```csharp
internal Unity.Collections.LowLevel.Unsafe.UnsafeParallelHashMap<System.Int32, System.UInt32> m_GlobalOffsets;
```

- `internal Colossal.Rendering.UnsafeGroupProperty* m_GroupPropertyPtr`  

```csharp
internal Colossal.Rendering.UnsafeGroupProperty* m_GroupPropertyPtr;
```

- `internal Colossal.Rendering.UnsafeBatchProperty* m_BatchPropertyPtr`  

```csharp
internal Colossal.Rendering.UnsafeBatchProperty* m_BatchPropertyPtr;
```

- `internal System.Int32* m_GroupPropertyIndicesPtr`  

```csharp
internal System.Int32* m_GroupPropertyIndicesPtr;
```

- `internal System.UInt32 m_ZeroAllocation`  

```csharp
internal System.UInt32 m_ZeroAllocation;
```

- `internal System.UInt32 m_GlobalAllocation`  

```csharp
internal System.UInt32 m_GlobalAllocation;
```

- `internal System.UInt32 m_BatchAllocation`  

```csharp
internal System.UInt32 m_BatchAllocation;
```

- `internal System.Int32 m_BatchPropertyCount`  

```csharp
internal System.Int32 m_BatchPropertyCount;
```


## Properties

- `public System.Int32 PropertyCount { get }`  

```csharp
public System.Int32 PropertyCount { get; }
```


## Methods

- `public GetMetaData(System.Int32 index, System.UInt32& batchPropertySize) : UnityEngine.Rendering.MetadataValue`  

```csharp
public UnityEngine.Rendering.MetadataValue GetMetaData(System.Int32 index, System.UInt32& batchPropertySize);
```


