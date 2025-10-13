# Colossal.Serialization.Entities.BinaryWriter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IWriter`  

## Code

```csharp
public sealed struct BinaryWriter : Colossal.Serialization.Entities.IWriter
{
    private Unity.Collections.NativeList<System.Byte> m_Buffer;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_EntityTable;
    private Colossal.Serialization.Entities.Context <context>k__BackingField;

    public Colossal.Serialization.Entities.Context context { get; private set; }

    public Colossal.Serialization.Entities.WriterBlock Begin();
    public System.Boolean End(Colossal.Serialization.Entities.WriterBlock block);
    public System.Boolean End(Colossal.Serialization.Entities.WriterBlock block, System.Int32& size);
    public System.Void Initialize(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeList<System.Byte> buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable);
    public System.Void Write(Unity.Collections.NativeArray<Unity.Entities.Entity> value);
    public System.Void Write(Unity.Collections.NativeList<Unity.Entities.Entity> value);
    public System.Void Write(Unity.Collections.NativeArray<System.Int32> value);
    public System.Void Write(Unity.Collections.NativeArray<Unity.Mathematics.int2> value);
    public System.Void Write(Unity.Collections.NativeArray<System.UInt16> value);
    public System.Void Write(Unity.Collections.NativeArray<System.Byte> value);
    public System.Void Write(Unity.Collections.NativeArray<Unity.Mathematics.float4> value);
    public System.Void Write(Unity.Collections.NativeArray<Unity.Mathematics.float2> value);
    public System.Void Write(Unity.Collections.NativeArray<System.Byte> value, System.Int32 stride);
    public System.Void Write(Unity.Collections.NativeList<System.Int32> value);
    public System.Void Write<TSerializable>(Unity.Collections.NativeArray<TSerializable> value);
    public System.Void Write(Unity.Entities.Entity value);
    public System.Void Write(Unity.Entities.Entity value, System.Boolean ignoreVersion);
    public System.Void Write<TSerializable>(TSerializable value);
    public System.Void Write(Colossal.Mathematics.Bezier4x3 curve);
    public System.Void Write(System.String value);
    public System.Void Write(UnityEngine.Color value);
    public System.Void Write(UnityEngine.Color32 value);
    public System.Void Write(Unity.Mathematics.quaternion value);
    public System.Void Write(Unity.Mathematics.float4 value);
    public System.Void Write(Unity.Mathematics.float3 value);
    public System.Void Write(Unity.Mathematics.float2 value);
    public System.Void Write(Unity.Mathematics.int4 value);
    public System.Void Write(Unity.Mathematics.int3 value);
    public System.Void Write(Unity.Mathematics.int2 value);
    public System.Void Write(Unity.Mathematics.bool4 value);
    public System.Void Write(Unity.Mathematics.bool3 value);
    public System.Void Write(Unity.Mathematics.bool2 value);
    public System.Void Write(Unity.Mathematics.uint4 value);
    public System.Void Write(Colossal.Hash128 hash);
    public System.Void Write(System.Char value);
    public System.Void Write(System.Single value);
    public System.Void Write(System.Double value);
    public System.Void Write(System.Int32 value);
    public System.Void Write(System.UInt32 value);
    public System.Void Write(System.Int16 value);
    public System.Void Write(System.UInt16 value);
    public System.Void Write(System.SByte value);
    public System.Void Write(System.Byte value);
    public System.Void Write(System.Int64 value);
    public System.Void Write(System.UInt64 value);
    public System.Void Write(System.Boolean value);
}
```


## Fields

- `private Unity.Collections.NativeList<System.Byte> m_Buffer`  

```csharp
private Unity.Collections.NativeList<System.Byte> m_Buffer;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_EntityTable`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_EntityTable;
```

- `private Colossal.Serialization.Entities.Context <context>k__BackingField`  

```csharp
private Colossal.Serialization.Entities.Context <context>k__BackingField;
```


## Properties

- `public Colossal.Serialization.Entities.Context context { get; private set }`  

```csharp
public Colossal.Serialization.Entities.Context context { get; private set; }
```


## Methods

- `public Begin() : Colossal.Serialization.Entities.WriterBlock`  

```csharp
public Colossal.Serialization.Entities.WriterBlock Begin();
```

- `public End(Colossal.Serialization.Entities.WriterBlock block) : System.Boolean`  

```csharp
public System.Boolean End(Colossal.Serialization.Entities.WriterBlock block);
```

- `public End(Colossal.Serialization.Entities.WriterBlock block, System.Int32& size) : System.Boolean`  

```csharp
public System.Boolean End(Colossal.Serialization.Entities.WriterBlock block, System.Int32& size);
```

- `public Initialize(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeList<System.Byte> buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable) : System.Void`  

```csharp
public System.Void Initialize(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeList<System.Byte> buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable);
```

- `public Write(Unity.Collections.NativeArray<Unity.Entities.Entity> value) : System.Void`  

```csharp
public System.Void Write(Unity.Collections.NativeArray<Unity.Entities.Entity> value);
```

- `public Write(Unity.Collections.NativeList<Unity.Entities.Entity> value) : System.Void`  

```csharp
public System.Void Write(Unity.Collections.NativeList<Unity.Entities.Entity> value);
```

- `public Write(Unity.Collections.NativeArray<System.Int32> value) : System.Void`  

```csharp
public System.Void Write(Unity.Collections.NativeArray<System.Int32> value);
```

- `public Write(Unity.Collections.NativeArray<Unity.Mathematics.int2> value) : System.Void`  

```csharp
public System.Void Write(Unity.Collections.NativeArray<Unity.Mathematics.int2> value);
```

- `public Write(Unity.Collections.NativeArray<System.UInt16> value) : System.Void`  

```csharp
public System.Void Write(Unity.Collections.NativeArray<System.UInt16> value);
```

- `public Write(Unity.Collections.NativeArray<System.Byte> value) : System.Void`  

```csharp
public System.Void Write(Unity.Collections.NativeArray<System.Byte> value);
```

- `public Write(Unity.Collections.NativeArray<Unity.Mathematics.float4> value) : System.Void`  

```csharp
public System.Void Write(Unity.Collections.NativeArray<Unity.Mathematics.float4> value);
```

- `public Write(Unity.Collections.NativeArray<Unity.Mathematics.float2> value) : System.Void`  

```csharp
public System.Void Write(Unity.Collections.NativeArray<Unity.Mathematics.float2> value);
```

- `public Write(Unity.Collections.NativeArray<System.Byte> value, System.Int32 stride) : System.Void`  

```csharp
public System.Void Write(Unity.Collections.NativeArray<System.Byte> value, System.Int32 stride);
```

- `public Write(Unity.Collections.NativeList<System.Int32> value) : System.Void`  

```csharp
public System.Void Write(Unity.Collections.NativeList<System.Int32> value);
```

- `public Write<TSerializable>(Unity.Collections.NativeArray<TSerializable> value) : System.Void`  

```csharp
public System.Void Write<TSerializable>(Unity.Collections.NativeArray<TSerializable> value);
```

- `public Write(Unity.Entities.Entity value) : System.Void`  

```csharp
public System.Void Write(Unity.Entities.Entity value);
```

- `public Write(Unity.Entities.Entity value, System.Boolean ignoreVersion) : System.Void`  

```csharp
public System.Void Write(Unity.Entities.Entity value, System.Boolean ignoreVersion);
```

- `public Write<TSerializable>(TSerializable value) : System.Void`  

```csharp
public System.Void Write<TSerializable>(TSerializable value);
```

- `public Write(Colossal.Mathematics.Bezier4x3 curve) : System.Void`  

```csharp
public System.Void Write(Colossal.Mathematics.Bezier4x3 curve);
```

- `public Write(System.String value) : System.Void`  

```csharp
public System.Void Write(System.String value);
```

- `public Write(UnityEngine.Color value) : System.Void`  

```csharp
public System.Void Write(UnityEngine.Color value);
```

- `public Write(UnityEngine.Color32 value) : System.Void`  

```csharp
public System.Void Write(UnityEngine.Color32 value);
```

- `public Write(Unity.Mathematics.quaternion value) : System.Void`  

```csharp
public System.Void Write(Unity.Mathematics.quaternion value);
```

- `public Write(Unity.Mathematics.float4 value) : System.Void`  

```csharp
public System.Void Write(Unity.Mathematics.float4 value);
```

- `public Write(Unity.Mathematics.float3 value) : System.Void`  

```csharp
public System.Void Write(Unity.Mathematics.float3 value);
```

- `public Write(Unity.Mathematics.float2 value) : System.Void`  

```csharp
public System.Void Write(Unity.Mathematics.float2 value);
```

- `public Write(Unity.Mathematics.int4 value) : System.Void`  

```csharp
public System.Void Write(Unity.Mathematics.int4 value);
```

- `public Write(Unity.Mathematics.int3 value) : System.Void`  

```csharp
public System.Void Write(Unity.Mathematics.int3 value);
```

- `public Write(Unity.Mathematics.int2 value) : System.Void`  

```csharp
public System.Void Write(Unity.Mathematics.int2 value);
```

- `public Write(Unity.Mathematics.bool4 value) : System.Void`  

```csharp
public System.Void Write(Unity.Mathematics.bool4 value);
```

- `public Write(Unity.Mathematics.bool3 value) : System.Void`  

```csharp
public System.Void Write(Unity.Mathematics.bool3 value);
```

- `public Write(Unity.Mathematics.bool2 value) : System.Void`  

```csharp
public System.Void Write(Unity.Mathematics.bool2 value);
```

- `public Write(Unity.Mathematics.uint4 value) : System.Void`  

```csharp
public System.Void Write(Unity.Mathematics.uint4 value);
```

- `public Write(Colossal.Hash128 hash) : System.Void`  

```csharp
public System.Void Write(Colossal.Hash128 hash);
```

- `public Write(System.Char value) : System.Void`  

```csharp
public System.Void Write(System.Char value);
```

- `public Write(System.Single value) : System.Void`  

```csharp
public System.Void Write(System.Single value);
```

- `public Write(System.Double value) : System.Void`  

```csharp
public System.Void Write(System.Double value);
```

- `public Write(System.Int32 value) : System.Void`  

```csharp
public System.Void Write(System.Int32 value);
```

- `public Write(System.UInt32 value) : System.Void`  

```csharp
public System.Void Write(System.UInt32 value);
```

- `public Write(System.Int16 value) : System.Void`  

```csharp
public System.Void Write(System.Int16 value);
```

- `public Write(System.UInt16 value) : System.Void`  

```csharp
public System.Void Write(System.UInt16 value);
```

- `public Write(System.SByte value) : System.Void`  

```csharp
public System.Void Write(System.SByte value);
```

- `public Write(System.Byte value) : System.Void`  

```csharp
public System.Void Write(System.Byte value);
```

- `public Write(System.Int64 value) : System.Void`  

```csharp
public System.Void Write(System.Int64 value);
```

- `public Write(System.UInt64 value) : System.Void`  

```csharp
public System.Void Write(System.UInt64 value);
```

- `public Write(System.Boolean value) : System.Void`  

```csharp
public System.Void Write(System.Boolean value);
```


