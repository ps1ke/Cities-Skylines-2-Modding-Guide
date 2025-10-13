# Colossal.Serialization.Entities.BinaryReader

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IReader`  

## Code

```csharp
public sealed struct BinaryReader : Colossal.Serialization.Entities.IReader
{
    private Unity.Collections.NativeArray<System.Byte> m_Buffer;
    private Unity.Collections.NativeReference<System.Int32> m_Position;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_EntityTable;
    private Colossal.Serialization.Entities.Context <context>k__BackingField;

    public Colossal.Serialization.Entities.Context context { get; private set; }

    public Colossal.Serialization.Entities.ReaderBlock Begin();
    public Colossal.Serialization.Entities.ReaderBlock Begin(System.Int32& size);
    public System.Boolean End(Colossal.Serialization.Entities.ReaderBlock block);
    public System.Void Initialize(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeArray<System.Byte> buffer, Unity.Collections.NativeReference<System.Int32> position, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable);
    public System.Void Read(Unity.Collections.NativeArray<Unity.Entities.Entity> value);
    public System.Void Read(Unity.Collections.NativeArray<System.Int32> value);
    public System.Void Read(Unity.Collections.NativeArray<Unity.Mathematics.int2> value);
    public System.Void Read(Unity.Collections.NativeArray<System.UInt16> value);
    public System.Void Read(Unity.Collections.NativeArray<System.Byte> value);
    public System.Void Read(Unity.Collections.NativeArray<Unity.Mathematics.float4> value);
    public System.Void Read(Unity.Collections.NativeArray<Unity.Mathematics.float2> value);
    public System.Void Read(Unity.Collections.NativeArray<System.Byte> value, System.Int32 stride);
    public System.Void Read(Unity.Collections.NativeList<System.Int32> value);
    public System.Void Read(Unity.Collections.NativeList<Unity.Entities.Entity> value);
    public System.Void Read<TSerializable>(Unity.Collections.NativeArray<TSerializable> value);
    public System.Void Read(Unity.Entities.Entity& value);
    public System.Void Read<TSerializable>(TSerializable& value);
    public System.Void Read<TSerializable>(TSerializable value);
    public System.Void Read(Colossal.Mathematics.Bezier4x3& curve);
    public System.Void Read(System.String& value);
    public System.Void Read(UnityEngine.Color& value);
    public System.Void Read(UnityEngine.Color32& value);
    public System.Void Read(Unity.Mathematics.quaternion& value);
    public System.Void Read(Unity.Mathematics.float4& value);
    public System.Void Read(Unity.Mathematics.float3& value);
    public System.Void Read(Unity.Mathematics.float2& value);
    public System.Void Read(Unity.Mathematics.int4& value);
    public System.Void Read(Unity.Mathematics.int3& value);
    public System.Void Read(Unity.Mathematics.int2& value);
    public System.Void Read(Unity.Mathematics.bool4& value);
    public System.Void Read(Unity.Mathematics.bool3& value);
    public System.Void Read(Unity.Mathematics.bool2& value);
    public System.Void Read(Unity.Mathematics.uint4& value);
    public System.Void Read(Colossal.Hash128& hash);
    public System.Void Read(System.Char& value);
    public System.Void Read(System.Single& value);
    public System.Void Read(System.Double& value);
    public System.Void Read(System.Int32& value);
    public System.Void Read(System.UInt32& value);
    public System.Void Read(System.Int16& value);
    public System.Void Read(System.UInt16& value);
    public System.Void Read(System.SByte& value);
    public System.Void Read(System.Byte& value);
    public System.Void Read(System.Int64& value);
    public System.Void Read(System.UInt64& value);
    public System.Void Read(System.Boolean& value);
    public System.Void Skip(System.Int32 size);
}
```


## Fields

- `private Unity.Collections.NativeArray<System.Byte> m_Buffer`  

```csharp
private Unity.Collections.NativeArray<System.Byte> m_Buffer;
```

- `private Unity.Collections.NativeReference<System.Int32> m_Position`  

```csharp
private Unity.Collections.NativeReference<System.Int32> m_Position;
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

- `public Begin() : Colossal.Serialization.Entities.ReaderBlock`  

```csharp
public Colossal.Serialization.Entities.ReaderBlock Begin();
```

- `public Begin(System.Int32& size) : Colossal.Serialization.Entities.ReaderBlock`  

```csharp
public Colossal.Serialization.Entities.ReaderBlock Begin(System.Int32& size);
```

- `public End(Colossal.Serialization.Entities.ReaderBlock block) : System.Boolean`  

```csharp
public System.Boolean End(Colossal.Serialization.Entities.ReaderBlock block);
```

- `public Initialize(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeArray<System.Byte> buffer, Unity.Collections.NativeReference<System.Int32> position, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable) : System.Void`  

```csharp
public System.Void Initialize(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeArray<System.Byte> buffer, Unity.Collections.NativeReference<System.Int32> position, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable);
```

- `public Read(Unity.Collections.NativeArray<Unity.Entities.Entity> value) : System.Void`  

```csharp
public System.Void Read(Unity.Collections.NativeArray<Unity.Entities.Entity> value);
```

- `public Read(Unity.Collections.NativeArray<System.Int32> value) : System.Void`  

```csharp
public System.Void Read(Unity.Collections.NativeArray<System.Int32> value);
```

- `public Read(Unity.Collections.NativeArray<Unity.Mathematics.int2> value) : System.Void`  

```csharp
public System.Void Read(Unity.Collections.NativeArray<Unity.Mathematics.int2> value);
```

- `public Read(Unity.Collections.NativeArray<System.UInt16> value) : System.Void`  

```csharp
public System.Void Read(Unity.Collections.NativeArray<System.UInt16> value);
```

- `public Read(Unity.Collections.NativeArray<System.Byte> value) : System.Void`  

```csharp
public System.Void Read(Unity.Collections.NativeArray<System.Byte> value);
```

- `public Read(Unity.Collections.NativeArray<Unity.Mathematics.float4> value) : System.Void`  

```csharp
public System.Void Read(Unity.Collections.NativeArray<Unity.Mathematics.float4> value);
```

- `public Read(Unity.Collections.NativeArray<Unity.Mathematics.float2> value) : System.Void`  

```csharp
public System.Void Read(Unity.Collections.NativeArray<Unity.Mathematics.float2> value);
```

- `public Read(Unity.Collections.NativeArray<System.Byte> value, System.Int32 stride) : System.Void`  

```csharp
public System.Void Read(Unity.Collections.NativeArray<System.Byte> value, System.Int32 stride);
```

- `public Read(Unity.Collections.NativeList<System.Int32> value) : System.Void`  

```csharp
public System.Void Read(Unity.Collections.NativeList<System.Int32> value);
```

- `public Read(Unity.Collections.NativeList<Unity.Entities.Entity> value) : System.Void`  

```csharp
public System.Void Read(Unity.Collections.NativeList<Unity.Entities.Entity> value);
```

- `public Read<TSerializable>(Unity.Collections.NativeArray<TSerializable> value) : System.Void`  

```csharp
public System.Void Read<TSerializable>(Unity.Collections.NativeArray<TSerializable> value);
```

- `public Read(Unity.Entities.Entity& value) : System.Void`  

```csharp
public System.Void Read(Unity.Entities.Entity& value);
```

- `public Read<TSerializable>(TSerializable& value) : System.Void`  

```csharp
public System.Void Read<TSerializable>(TSerializable& value);
```

- `public Read<TSerializable>(TSerializable value) : System.Void`  

```csharp
public System.Void Read<TSerializable>(TSerializable value);
```

- `public Read(Colossal.Mathematics.Bezier4x3& curve) : System.Void`  

```csharp
public System.Void Read(Colossal.Mathematics.Bezier4x3& curve);
```

- `public Read(System.String& value) : System.Void`  

```csharp
public System.Void Read(System.String& value);
```

- `public Read(UnityEngine.Color& value) : System.Void`  

```csharp
public System.Void Read(UnityEngine.Color& value);
```

- `public Read(UnityEngine.Color32& value) : System.Void`  

```csharp
public System.Void Read(UnityEngine.Color32& value);
```

- `public Read(Unity.Mathematics.quaternion& value) : System.Void`  

```csharp
public System.Void Read(Unity.Mathematics.quaternion& value);
```

- `public Read(Unity.Mathematics.float4& value) : System.Void`  

```csharp
public System.Void Read(Unity.Mathematics.float4& value);
```

- `public Read(Unity.Mathematics.float3& value) : System.Void`  

```csharp
public System.Void Read(Unity.Mathematics.float3& value);
```

- `public Read(Unity.Mathematics.float2& value) : System.Void`  

```csharp
public System.Void Read(Unity.Mathematics.float2& value);
```

- `public Read(Unity.Mathematics.int4& value) : System.Void`  

```csharp
public System.Void Read(Unity.Mathematics.int4& value);
```

- `public Read(Unity.Mathematics.int3& value) : System.Void`  

```csharp
public System.Void Read(Unity.Mathematics.int3& value);
```

- `public Read(Unity.Mathematics.int2& value) : System.Void`  

```csharp
public System.Void Read(Unity.Mathematics.int2& value);
```

- `public Read(Unity.Mathematics.bool4& value) : System.Void`  

```csharp
public System.Void Read(Unity.Mathematics.bool4& value);
```

- `public Read(Unity.Mathematics.bool3& value) : System.Void`  

```csharp
public System.Void Read(Unity.Mathematics.bool3& value);
```

- `public Read(Unity.Mathematics.bool2& value) : System.Void`  

```csharp
public System.Void Read(Unity.Mathematics.bool2& value);
```

- `public Read(Unity.Mathematics.uint4& value) : System.Void`  

```csharp
public System.Void Read(Unity.Mathematics.uint4& value);
```

- `public Read(Colossal.Hash128& hash) : System.Void`  

```csharp
public System.Void Read(Colossal.Hash128& hash);
```

- `public Read(System.Char& value) : System.Void`  

```csharp
public System.Void Read(System.Char& value);
```

- `public Read(System.Single& value) : System.Void`  

```csharp
public System.Void Read(System.Single& value);
```

- `public Read(System.Double& value) : System.Void`  

```csharp
public System.Void Read(System.Double& value);
```

- `public Read(System.Int32& value) : System.Void`  

```csharp
public System.Void Read(System.Int32& value);
```

- `public Read(System.UInt32& value) : System.Void`  

```csharp
public System.Void Read(System.UInt32& value);
```

- `public Read(System.Int16& value) : System.Void`  

```csharp
public System.Void Read(System.Int16& value);
```

- `public Read(System.UInt16& value) : System.Void`  

```csharp
public System.Void Read(System.UInt16& value);
```

- `public Read(System.SByte& value) : System.Void`  

```csharp
public System.Void Read(System.SByte& value);
```

- `public Read(System.Byte& value) : System.Void`  

```csharp
public System.Void Read(System.Byte& value);
```

- `public Read(System.Int64& value) : System.Void`  

```csharp
public System.Void Read(System.Int64& value);
```

- `public Read(System.UInt64& value) : System.Void`  

```csharp
public System.Void Read(System.UInt64& value);
```

- `public Read(System.Boolean& value) : System.Void`  

```csharp
public System.Void Read(System.Boolean& value);
```

- `public Skip(System.Int32 size) : System.Void`  

```csharp
public System.Void Skip(System.Int32 size);
```


