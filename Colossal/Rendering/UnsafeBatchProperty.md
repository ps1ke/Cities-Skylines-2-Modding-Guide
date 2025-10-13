# Colossal.Rendering.UnsafeBatchProperty

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Rendering`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct UnsafeBatchProperty
{
    public System.Int32 m_NameID;
    public System.Int32 m_SizeBytesGPU;
    public System.Int32 m_DefaultOffset;
    public System.Boolean m_BuiltinProperty;
    public System.Boolean m_OverriddenInBatch;
    public System.Boolean m_GlobalValue;
    public static const System.UInt32 GPU_ALLOCATION_ALIGN;

    public static System.UInt32 GPUAligned(System.UInt32 value);
}
```


## Fields

- `public System.Int32 m_NameID`  

```csharp
public System.Int32 m_NameID;
```

- `public System.Int32 m_SizeBytesGPU`  

```csharp
public System.Int32 m_SizeBytesGPU;
```

- `public System.Int32 m_DefaultOffset`  

```csharp
public System.Int32 m_DefaultOffset;
```

- `public System.Boolean m_BuiltinProperty`  

```csharp
public System.Boolean m_BuiltinProperty;
```

- `public System.Boolean m_OverriddenInBatch`  

```csharp
public System.Boolean m_OverriddenInBatch;
```

- `public System.Boolean m_GlobalValue`  

```csharp
public System.Boolean m_GlobalValue;
```

- `public static const System.UInt32 GPU_ALLOCATION_ALIGN`  

```csharp
public static const System.UInt32 GPU_ALLOCATION_ALIGN;
```


## Methods

- `public static GPUAligned(System.UInt32 value) : System.UInt32`  

```csharp
public static System.UInt32 GPUAligned(System.UInt32 value);
```


