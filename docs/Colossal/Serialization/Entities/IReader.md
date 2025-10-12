# Colossal.Serialization.Entities.IReader

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** interface abstract public  


## Properties

- `public Colossal.Serialization.Entities.Context context { get }`  

## Methods

- `public abstract Begin() : Colossal.Serialization.Entities.ReaderBlock`  
- `public abstract Begin(System.Int32& size) : Colossal.Serialization.Entities.ReaderBlock`  
- `public abstract End(Colossal.Serialization.Entities.ReaderBlock block) : System.Boolean`  
- `public abstract Initialize(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeArray<System.Byte> buffer, Unity.Collections.NativeReference<System.Int32> position, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable) : System.Void`  
- `public abstract Read(Unity.Collections.NativeArray<Unity.Entities.Entity> value) : System.Void`  
- `public abstract Read(Unity.Collections.NativeArray<System.Int32> value) : System.Void`  
- `public abstract Read(Unity.Collections.NativeArray<Unity.Mathematics.int2> value) : System.Void`  
- `public abstract Read(Unity.Collections.NativeArray<System.UInt16> value) : System.Void`  
- `public abstract Read(Unity.Collections.NativeArray<System.Byte> value) : System.Void`  
- `public abstract Read(Unity.Collections.NativeArray<Unity.Mathematics.float4> value) : System.Void`  
- `public abstract Read(Unity.Collections.NativeArray<Unity.Mathematics.float2> value) : System.Void`  
- `public abstract Read(Unity.Collections.NativeArray<System.Byte> value, System.Int32 stride) : System.Void`  
- `public abstract Read(Unity.Collections.NativeList<System.Int32> value) : System.Void`  
- `public abstract Read(Unity.Collections.NativeList<Unity.Entities.Entity> value) : System.Void`  
- `public abstract Read<TSerializable>(Unity.Collections.NativeArray<TSerializable> value) : System.Void`  
- `public abstract Read(Unity.Entities.Entity& value) : System.Void`  
- `public abstract Read<TSerializable>(TSerializable& value) : System.Void`  
- `public abstract Read<TSerializable>(TSerializable value) : System.Void`  
- `public abstract Read(Colossal.Mathematics.Bezier4x3& curve) : System.Void`  
- `public abstract Read(System.String& value) : System.Void`  
- `public abstract Read(UnityEngine.Color& value) : System.Void`  
- `public abstract Read(UnityEngine.Color32& value) : System.Void`  
- `public abstract Read(Unity.Mathematics.quaternion& value) : System.Void`  
- `public abstract Read(Unity.Mathematics.float4& value) : System.Void`  
- `public abstract Read(Unity.Mathematics.float3& value) : System.Void`  
- `public abstract Read(Unity.Mathematics.float2& value) : System.Void`  
- `public abstract Read(Unity.Mathematics.int4& value) : System.Void`  
- `public abstract Read(Unity.Mathematics.int3& value) : System.Void`  
- `public abstract Read(Unity.Mathematics.int2& value) : System.Void`  
- `public abstract Read(Unity.Mathematics.bool4& value) : System.Void`  
- `public abstract Read(Unity.Mathematics.bool3& value) : System.Void`  
- `public abstract Read(Unity.Mathematics.bool2& value) : System.Void`  
- `public abstract Read(Unity.Mathematics.uint4& value) : System.Void`  
- `public abstract Read(Colossal.Hash128& value) : System.Void`  
- `public abstract Read(System.Char& value) : System.Void`  
- `public abstract Read(System.Single& value) : System.Void`  
- `public abstract Read(System.Double& value) : System.Void`  
- `public abstract Read(System.Int32& value) : System.Void`  
- `public abstract Read(System.UInt32& value) : System.Void`  
- `public abstract Read(System.Int16& value) : System.Void`  
- `public abstract Read(System.UInt16& value) : System.Void`  
- `public abstract Read(System.SByte& value) : System.Void`  
- `public abstract Read(System.Byte& value) : System.Void`  
- `public abstract Read(System.Int64& value) : System.Void`  
- `public abstract Read(System.UInt64& value) : System.Void`  
- `public abstract Read(System.Boolean& value) : System.Void`  
- `public abstract Skip(System.Int32 size) : System.Void`  

