# Colossal.Serialization.Entities.IWriter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** interface abstract public  


## Properties

- `public Colossal.Serialization.Entities.Context context { get }`  

## Methods

- `public abstract Begin() : Colossal.Serialization.Entities.WriterBlock`  
- `public abstract End(Colossal.Serialization.Entities.WriterBlock block) : System.Boolean`  
- `public abstract End(Colossal.Serialization.Entities.WriterBlock block, System.Int32& size) : System.Boolean`  
- `public abstract Initialize(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeList<System.Byte> buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable) : System.Void`  
- `public abstract Write(Unity.Collections.NativeArray<Unity.Entities.Entity> value) : System.Void`  
- `public abstract Write(Unity.Collections.NativeList<Unity.Entities.Entity> value) : System.Void`  
- `public abstract Write(Unity.Collections.NativeList<System.Int32> value) : System.Void`  
- `public abstract Write<TSerializable>(Unity.Collections.NativeArray<TSerializable> value) : System.Void`  
- `public abstract Write(Unity.Collections.NativeArray<System.Int32> value) : System.Void`  
- `public abstract Write(Unity.Collections.NativeArray<Unity.Mathematics.int2> value) : System.Void`  
- `public abstract Write(Unity.Collections.NativeArray<System.UInt16> value) : System.Void`  
- `public abstract Write(Unity.Collections.NativeArray<System.Byte> value) : System.Void`  
- `public abstract Write(Unity.Collections.NativeArray<Unity.Mathematics.float4> value) : System.Void`  
- `public abstract Write(Unity.Collections.NativeArray<Unity.Mathematics.float2> value) : System.Void`  
- `public abstract Write(Unity.Collections.NativeArray<System.Byte> value, System.Int32 stride) : System.Void`  
- `public abstract Write(Unity.Entities.Entity value) : System.Void`  
- `public abstract Write(Unity.Entities.Entity value, System.Boolean ignoreVersion) : System.Void`  
- `public abstract Write<TSerializable>(TSerializable value) : System.Void`  
- `public abstract Write(Colossal.Mathematics.Bezier4x3 curve) : System.Void`  
- `public abstract Write(System.String value) : System.Void`  
- `public abstract Write(UnityEngine.Color value) : System.Void`  
- `public abstract Write(UnityEngine.Color32 value) : System.Void`  
- `public abstract Write(Unity.Mathematics.quaternion value) : System.Void`  
- `public abstract Write(Unity.Mathematics.float4 value) : System.Void`  
- `public abstract Write(Unity.Mathematics.float3 value) : System.Void`  
- `public abstract Write(Unity.Mathematics.float2 value) : System.Void`  
- `public abstract Write(Unity.Mathematics.int4 value) : System.Void`  
- `public abstract Write(Unity.Mathematics.int3 value) : System.Void`  
- `public abstract Write(Unity.Mathematics.int2 value) : System.Void`  
- `public abstract Write(Unity.Mathematics.bool4 value) : System.Void`  
- `public abstract Write(Unity.Mathematics.bool3 value) : System.Void`  
- `public abstract Write(Unity.Mathematics.bool2 value) : System.Void`  
- `public abstract Write(Unity.Mathematics.uint4 value) : System.Void`  
- `public abstract Write(Colossal.Hash128 hash) : System.Void`  
- `public abstract Write(System.Char value) : System.Void`  
- `public abstract Write(System.Single value) : System.Void`  
- `public abstract Write(System.Double value) : System.Void`  
- `public abstract Write(System.Int32 value) : System.Void`  
- `public abstract Write(System.UInt32 value) : System.Void`  
- `public abstract Write(System.Int16 value) : System.Void`  
- `public abstract Write(System.UInt16 value) : System.Void`  
- `public abstract Write(System.SByte value) : System.Void`  
- `public abstract Write(System.Byte value) : System.Void`  
- `public abstract Write(System.Int64 value) : System.Void`  
- `public abstract Write(System.UInt64 value) : System.Void`  
- `public abstract Write(System.Boolean value) : System.Void`  

