# Colossal.Serialization.Entities.IWriter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IWriter
{
    public Colossal.Serialization.Entities.Context context { get; }

    public abstract Colossal.Serialization.Entities.WriterBlock Begin();
    public abstract System.Boolean End(Colossal.Serialization.Entities.WriterBlock block);
    public abstract System.Boolean End(Colossal.Serialization.Entities.WriterBlock block, System.Int32& size);
    public abstract System.Void Initialize(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeList<System.Byte> buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable);
    public abstract System.Void Write(Unity.Collections.NativeArray<Unity.Entities.Entity> value);
    public abstract System.Void Write(Unity.Collections.NativeList<Unity.Entities.Entity> value);
    public abstract System.Void Write(Unity.Collections.NativeList<System.Int32> value);
    public abstract System.Void Write<TSerializable>(Unity.Collections.NativeArray<TSerializable> value);
    public abstract System.Void Write(Unity.Collections.NativeArray<System.Int32> value);
    public abstract System.Void Write(Unity.Collections.NativeArray<Unity.Mathematics.int2> value);
    public abstract System.Void Write(Unity.Collections.NativeArray<System.UInt16> value);
    public abstract System.Void Write(Unity.Collections.NativeArray<System.Byte> value);
    public abstract System.Void Write(Unity.Collections.NativeArray<Unity.Mathematics.float4> value);
    public abstract System.Void Write(Unity.Collections.NativeArray<Unity.Mathematics.float2> value);
    public abstract System.Void Write(Unity.Collections.NativeArray<System.Byte> value, System.Int32 stride);
    public abstract System.Void Write(Unity.Entities.Entity value);
    public abstract System.Void Write(Unity.Entities.Entity value, System.Boolean ignoreVersion);
    public abstract System.Void Write<TSerializable>(TSerializable value);
    public abstract System.Void Write(Colossal.Mathematics.Bezier4x3 curve);
    public abstract System.Void Write(System.String value);
    public abstract System.Void Write(UnityEngine.Color value);
    public abstract System.Void Write(UnityEngine.Color32 value);
    public abstract System.Void Write(Unity.Mathematics.quaternion value);
    public abstract System.Void Write(Unity.Mathematics.float4 value);
    public abstract System.Void Write(Unity.Mathematics.float3 value);
    public abstract System.Void Write(Unity.Mathematics.float2 value);
    public abstract System.Void Write(Unity.Mathematics.int4 value);
    public abstract System.Void Write(Unity.Mathematics.int3 value);
    public abstract System.Void Write(Unity.Mathematics.int2 value);
    public abstract System.Void Write(Unity.Mathematics.bool4 value);
    public abstract System.Void Write(Unity.Mathematics.bool3 value);
    public abstract System.Void Write(Unity.Mathematics.bool2 value);
    public abstract System.Void Write(Unity.Mathematics.uint4 value);
    public abstract System.Void Write(Colossal.Hash128 hash);
    public abstract System.Void Write(System.Char value);
    public abstract System.Void Write(System.Single value);
    public abstract System.Void Write(System.Double value);
    public abstract System.Void Write(System.Int32 value);
    public abstract System.Void Write(System.UInt32 value);
    public abstract System.Void Write(System.Int16 value);
    public abstract System.Void Write(System.UInt16 value);
    public abstract System.Void Write(System.SByte value);
    public abstract System.Void Write(System.Byte value);
    public abstract System.Void Write(System.Int64 value);
    public abstract System.Void Write(System.UInt64 value);
    public abstract System.Void Write(System.Boolean value);
}
```


## Properties

- `public Colossal.Serialization.Entities.Context context { get }`  

```csharp
public Colossal.Serialization.Entities.Context context { get; }
```


## Methods

- `public abstract Begin() : Colossal.Serialization.Entities.WriterBlock`  

```csharp
public abstract Colossal.Serialization.Entities.WriterBlock Begin();
```

- `public abstract End(Colossal.Serialization.Entities.WriterBlock block) : System.Boolean`  

```csharp
public abstract System.Boolean End(Colossal.Serialization.Entities.WriterBlock block);
```

- `public abstract End(Colossal.Serialization.Entities.WriterBlock block, System.Int32& size) : System.Boolean`  

```csharp
public abstract System.Boolean End(Colossal.Serialization.Entities.WriterBlock block, System.Int32& size);
```

- `public abstract Initialize(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeList<System.Byte> buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable) : System.Void`  

```csharp
public abstract System.Void Initialize(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeList<System.Byte> buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable);
```

- `public abstract Write(Unity.Collections.NativeArray<Unity.Entities.Entity> value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Collections.NativeArray<Unity.Entities.Entity> value);
```

- `public abstract Write(Unity.Collections.NativeList<Unity.Entities.Entity> value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Collections.NativeList<Unity.Entities.Entity> value);
```

- `public abstract Write(Unity.Collections.NativeList<System.Int32> value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Collections.NativeList<System.Int32> value);
```

- `public abstract Write<TSerializable>(Unity.Collections.NativeArray<TSerializable> value) : System.Void`  

```csharp
public abstract System.Void Write<TSerializable>(Unity.Collections.NativeArray<TSerializable> value);
```

- `public abstract Write(Unity.Collections.NativeArray<System.Int32> value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Collections.NativeArray<System.Int32> value);
```

- `public abstract Write(Unity.Collections.NativeArray<Unity.Mathematics.int2> value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Collections.NativeArray<Unity.Mathematics.int2> value);
```

- `public abstract Write(Unity.Collections.NativeArray<System.UInt16> value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Collections.NativeArray<System.UInt16> value);
```

- `public abstract Write(Unity.Collections.NativeArray<System.Byte> value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Collections.NativeArray<System.Byte> value);
```

- `public abstract Write(Unity.Collections.NativeArray<Unity.Mathematics.float4> value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Collections.NativeArray<Unity.Mathematics.float4> value);
```

- `public abstract Write(Unity.Collections.NativeArray<Unity.Mathematics.float2> value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Collections.NativeArray<Unity.Mathematics.float2> value);
```

- `public abstract Write(Unity.Collections.NativeArray<System.Byte> value, System.Int32 stride) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Collections.NativeArray<System.Byte> value, System.Int32 stride);
```

- `public abstract Write(Unity.Entities.Entity value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Entities.Entity value);
```

- `public abstract Write(Unity.Entities.Entity value, System.Boolean ignoreVersion) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Entities.Entity value, System.Boolean ignoreVersion);
```

- `public abstract Write<TSerializable>(TSerializable value) : System.Void`  

```csharp
public abstract System.Void Write<TSerializable>(TSerializable value);
```

- `public abstract Write(Colossal.Mathematics.Bezier4x3 curve) : System.Void`  

```csharp
public abstract System.Void Write(Colossal.Mathematics.Bezier4x3 curve);
```

- `public abstract Write(System.String value) : System.Void`  

```csharp
public abstract System.Void Write(System.String value);
```

- `public abstract Write(UnityEngine.Color value) : System.Void`  

```csharp
public abstract System.Void Write(UnityEngine.Color value);
```

- `public abstract Write(UnityEngine.Color32 value) : System.Void`  

```csharp
public abstract System.Void Write(UnityEngine.Color32 value);
```

- `public abstract Write(Unity.Mathematics.quaternion value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Mathematics.quaternion value);
```

- `public abstract Write(Unity.Mathematics.float4 value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Mathematics.float4 value);
```

- `public abstract Write(Unity.Mathematics.float3 value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Mathematics.float3 value);
```

- `public abstract Write(Unity.Mathematics.float2 value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Mathematics.float2 value);
```

- `public abstract Write(Unity.Mathematics.int4 value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Mathematics.int4 value);
```

- `public abstract Write(Unity.Mathematics.int3 value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Mathematics.int3 value);
```

- `public abstract Write(Unity.Mathematics.int2 value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Mathematics.int2 value);
```

- `public abstract Write(Unity.Mathematics.bool4 value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Mathematics.bool4 value);
```

- `public abstract Write(Unity.Mathematics.bool3 value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Mathematics.bool3 value);
```

- `public abstract Write(Unity.Mathematics.bool2 value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Mathematics.bool2 value);
```

- `public abstract Write(Unity.Mathematics.uint4 value) : System.Void`  

```csharp
public abstract System.Void Write(Unity.Mathematics.uint4 value);
```

- `public abstract Write(Colossal.Hash128 hash) : System.Void`  

```csharp
public abstract System.Void Write(Colossal.Hash128 hash);
```

- `public abstract Write(System.Char value) : System.Void`  

```csharp
public abstract System.Void Write(System.Char value);
```

- `public abstract Write(System.Single value) : System.Void`  

```csharp
public abstract System.Void Write(System.Single value);
```

- `public abstract Write(System.Double value) : System.Void`  

```csharp
public abstract System.Void Write(System.Double value);
```

- `public abstract Write(System.Int32 value) : System.Void`  

```csharp
public abstract System.Void Write(System.Int32 value);
```

- `public abstract Write(System.UInt32 value) : System.Void`  

```csharp
public abstract System.Void Write(System.UInt32 value);
```

- `public abstract Write(System.Int16 value) : System.Void`  

```csharp
public abstract System.Void Write(System.Int16 value);
```

- `public abstract Write(System.UInt16 value) : System.Void`  

```csharp
public abstract System.Void Write(System.UInt16 value);
```

- `public abstract Write(System.SByte value) : System.Void`  

```csharp
public abstract System.Void Write(System.SByte value);
```

- `public abstract Write(System.Byte value) : System.Void`  

```csharp
public abstract System.Void Write(System.Byte value);
```

- `public abstract Write(System.Int64 value) : System.Void`  

```csharp
public abstract System.Void Write(System.Int64 value);
```

- `public abstract Write(System.UInt64 value) : System.Void`  

```csharp
public abstract System.Void Write(System.UInt64 value);
```

- `public abstract Write(System.Boolean value) : System.Void`  

```csharp
public abstract System.Void Write(System.Boolean value);
```


