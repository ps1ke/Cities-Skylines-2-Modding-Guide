# Colossal.Serialization.Entities.IReader

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IReader
{
    public Colossal.Serialization.Entities.Context context { get; }

    public abstract Colossal.Serialization.Entities.ReaderBlock Begin();
    public abstract Colossal.Serialization.Entities.ReaderBlock Begin(System.Int32& size);
    public abstract System.Boolean End(Colossal.Serialization.Entities.ReaderBlock block);
    public abstract System.Void Initialize(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeArray<System.Byte> buffer, Unity.Collections.NativeReference<System.Int32> position, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable);
    public abstract System.Void Read(Unity.Collections.NativeArray<Unity.Entities.Entity> value);
    public abstract System.Void Read(Unity.Collections.NativeArray<System.Int32> value);
    public abstract System.Void Read(Unity.Collections.NativeArray<Unity.Mathematics.int2> value);
    public abstract System.Void Read(Unity.Collections.NativeArray<System.UInt16> value);
    public abstract System.Void Read(Unity.Collections.NativeArray<System.Byte> value);
    public abstract System.Void Read(Unity.Collections.NativeArray<Unity.Mathematics.float4> value);
    public abstract System.Void Read(Unity.Collections.NativeArray<Unity.Mathematics.float2> value);
    public abstract System.Void Read(Unity.Collections.NativeArray<System.Byte> value, System.Int32 stride);
    public abstract System.Void Read(Unity.Collections.NativeList<System.Int32> value);
    public abstract System.Void Read(Unity.Collections.NativeList<Unity.Entities.Entity> value);
    public abstract System.Void Read<TSerializable>(Unity.Collections.NativeArray<TSerializable> value);
    public abstract System.Void Read(Unity.Entities.Entity& value);
    public abstract System.Void Read<TSerializable>(TSerializable& value);
    public abstract System.Void Read<TSerializable>(TSerializable value);
    public abstract System.Void Read(Colossal.Mathematics.Bezier4x3& curve);
    public abstract System.Void Read(System.String& value);
    public abstract System.Void Read(UnityEngine.Color& value);
    public abstract System.Void Read(UnityEngine.Color32& value);
    public abstract System.Void Read(Unity.Mathematics.quaternion& value);
    public abstract System.Void Read(Unity.Mathematics.float4& value);
    public abstract System.Void Read(Unity.Mathematics.float3& value);
    public abstract System.Void Read(Unity.Mathematics.float2& value);
    public abstract System.Void Read(Unity.Mathematics.int4& value);
    public abstract System.Void Read(Unity.Mathematics.int3& value);
    public abstract System.Void Read(Unity.Mathematics.int2& value);
    public abstract System.Void Read(Unity.Mathematics.bool4& value);
    public abstract System.Void Read(Unity.Mathematics.bool3& value);
    public abstract System.Void Read(Unity.Mathematics.bool2& value);
    public abstract System.Void Read(Unity.Mathematics.uint4& value);
    public abstract System.Void Read(Colossal.Hash128& value);
    public abstract System.Void Read(System.Char& value);
    public abstract System.Void Read(System.Single& value);
    public abstract System.Void Read(System.Double& value);
    public abstract System.Void Read(System.Int32& value);
    public abstract System.Void Read(System.UInt32& value);
    public abstract System.Void Read(System.Int16& value);
    public abstract System.Void Read(System.UInt16& value);
    public abstract System.Void Read(System.SByte& value);
    public abstract System.Void Read(System.Byte& value);
    public abstract System.Void Read(System.Int64& value);
    public abstract System.Void Read(System.UInt64& value);
    public abstract System.Void Read(System.Boolean& value);
    public abstract System.Void Skip(System.Int32 size);
}
```


## Properties

- `public Colossal.Serialization.Entities.Context context { get }`  

```csharp
public Colossal.Serialization.Entities.Context context { get; }
```


## Methods

- `public abstract Begin() : Colossal.Serialization.Entities.ReaderBlock`  

```csharp
public abstract Colossal.Serialization.Entities.ReaderBlock Begin();
```

- `public abstract Begin(System.Int32& size) : Colossal.Serialization.Entities.ReaderBlock`  

```csharp
public abstract Colossal.Serialization.Entities.ReaderBlock Begin(System.Int32& size);
```

- `public abstract End(Colossal.Serialization.Entities.ReaderBlock block) : System.Boolean`  

```csharp
public abstract System.Boolean End(Colossal.Serialization.Entities.ReaderBlock block);
```

- `public abstract Initialize(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeArray<System.Byte> buffer, Unity.Collections.NativeReference<System.Int32> position, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable) : System.Void`  

```csharp
public abstract System.Void Initialize(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeArray<System.Byte> buffer, Unity.Collections.NativeReference<System.Int32> position, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable);
```

- `public abstract Read(Unity.Collections.NativeArray<Unity.Entities.Entity> value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Collections.NativeArray<Unity.Entities.Entity> value);
```

- `public abstract Read(Unity.Collections.NativeArray<System.Int32> value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Collections.NativeArray<System.Int32> value);
```

- `public abstract Read(Unity.Collections.NativeArray<Unity.Mathematics.int2> value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Collections.NativeArray<Unity.Mathematics.int2> value);
```

- `public abstract Read(Unity.Collections.NativeArray<System.UInt16> value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Collections.NativeArray<System.UInt16> value);
```

- `public abstract Read(Unity.Collections.NativeArray<System.Byte> value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Collections.NativeArray<System.Byte> value);
```

- `public abstract Read(Unity.Collections.NativeArray<Unity.Mathematics.float4> value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Collections.NativeArray<Unity.Mathematics.float4> value);
```

- `public abstract Read(Unity.Collections.NativeArray<Unity.Mathematics.float2> value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Collections.NativeArray<Unity.Mathematics.float2> value);
```

- `public abstract Read(Unity.Collections.NativeArray<System.Byte> value, System.Int32 stride) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Collections.NativeArray<System.Byte> value, System.Int32 stride);
```

- `public abstract Read(Unity.Collections.NativeList<System.Int32> value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Collections.NativeList<System.Int32> value);
```

- `public abstract Read(Unity.Collections.NativeList<Unity.Entities.Entity> value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Collections.NativeList<Unity.Entities.Entity> value);
```

- `public abstract Read<TSerializable>(Unity.Collections.NativeArray<TSerializable> value) : System.Void`  

```csharp
public abstract System.Void Read<TSerializable>(Unity.Collections.NativeArray<TSerializable> value);
```

- `public abstract Read(Unity.Entities.Entity& value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Entities.Entity& value);
```

- `public abstract Read<TSerializable>(TSerializable& value) : System.Void`  

```csharp
public abstract System.Void Read<TSerializable>(TSerializable& value);
```

- `public abstract Read<TSerializable>(TSerializable value) : System.Void`  

```csharp
public abstract System.Void Read<TSerializable>(TSerializable value);
```

- `public abstract Read(Colossal.Mathematics.Bezier4x3& curve) : System.Void`  

```csharp
public abstract System.Void Read(Colossal.Mathematics.Bezier4x3& curve);
```

- `public abstract Read(System.String& value) : System.Void`  

```csharp
public abstract System.Void Read(System.String& value);
```

- `public abstract Read(UnityEngine.Color& value) : System.Void`  

```csharp
public abstract System.Void Read(UnityEngine.Color& value);
```

- `public abstract Read(UnityEngine.Color32& value) : System.Void`  

```csharp
public abstract System.Void Read(UnityEngine.Color32& value);
```

- `public abstract Read(Unity.Mathematics.quaternion& value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Mathematics.quaternion& value);
```

- `public abstract Read(Unity.Mathematics.float4& value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Mathematics.float4& value);
```

- `public abstract Read(Unity.Mathematics.float3& value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Mathematics.float3& value);
```

- `public abstract Read(Unity.Mathematics.float2& value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Mathematics.float2& value);
```

- `public abstract Read(Unity.Mathematics.int4& value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Mathematics.int4& value);
```

- `public abstract Read(Unity.Mathematics.int3& value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Mathematics.int3& value);
```

- `public abstract Read(Unity.Mathematics.int2& value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Mathematics.int2& value);
```

- `public abstract Read(Unity.Mathematics.bool4& value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Mathematics.bool4& value);
```

- `public abstract Read(Unity.Mathematics.bool3& value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Mathematics.bool3& value);
```

- `public abstract Read(Unity.Mathematics.bool2& value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Mathematics.bool2& value);
```

- `public abstract Read(Unity.Mathematics.uint4& value) : System.Void`  

```csharp
public abstract System.Void Read(Unity.Mathematics.uint4& value);
```

- `public abstract Read(Colossal.Hash128& value) : System.Void`  

```csharp
public abstract System.Void Read(Colossal.Hash128& value);
```

- `public abstract Read(System.Char& value) : System.Void`  

```csharp
public abstract System.Void Read(System.Char& value);
```

- `public abstract Read(System.Single& value) : System.Void`  

```csharp
public abstract System.Void Read(System.Single& value);
```

- `public abstract Read(System.Double& value) : System.Void`  

```csharp
public abstract System.Void Read(System.Double& value);
```

- `public abstract Read(System.Int32& value) : System.Void`  

```csharp
public abstract System.Void Read(System.Int32& value);
```

- `public abstract Read(System.UInt32& value) : System.Void`  

```csharp
public abstract System.Void Read(System.UInt32& value);
```

- `public abstract Read(System.Int16& value) : System.Void`  

```csharp
public abstract System.Void Read(System.Int16& value);
```

- `public abstract Read(System.UInt16& value) : System.Void`  

```csharp
public abstract System.Void Read(System.UInt16& value);
```

- `public abstract Read(System.SByte& value) : System.Void`  

```csharp
public abstract System.Void Read(System.SByte& value);
```

- `public abstract Read(System.Byte& value) : System.Void`  

```csharp
public abstract System.Void Read(System.Byte& value);
```

- `public abstract Read(System.Int64& value) : System.Void`  

```csharp
public abstract System.Void Read(System.Int64& value);
```

- `public abstract Read(System.UInt64& value) : System.Void`  

```csharp
public abstract System.Void Read(System.UInt64& value);
```

- `public abstract Read(System.Boolean& value) : System.Void`  

```csharp
public abstract System.Void Read(System.Boolean& value);
```

- `public abstract Skip(System.Int32 size) : System.Void`  

```csharp
public abstract System.Void Skip(System.Int32 size);
```


