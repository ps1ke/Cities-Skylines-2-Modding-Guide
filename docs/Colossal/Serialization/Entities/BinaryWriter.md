# Colossal.Serialization.Entities.BinaryWriter

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IWriter`  

## Fields

- `private Unity.Collections.NativeList<System.Byte> m_Buffer`  
- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_EntityTable`  
- `private Colossal.Serialization.Entities.Context <context>k__BackingField`  

## Properties

- `public Colossal.Serialization.Entities.Context context { get; private set }`  

## Methods

- `public Begin() : Colossal.Serialization.Entities.WriterBlock`  
- `public End(Colossal.Serialization.Entities.WriterBlock block) : System.Boolean`  
- `public End(Colossal.Serialization.Entities.WriterBlock block, System.Int32& size) : System.Boolean`  
- `public Initialize(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeList<System.Byte> buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable) : System.Void`  
- `public Write(Unity.Collections.NativeArray<Unity.Entities.Entity> value) : System.Void`  
- `public Write(Unity.Collections.NativeList<Unity.Entities.Entity> value) : System.Void`  
- `public Write(Unity.Collections.NativeArray<System.Int32> value) : System.Void`  
- `public Write(Unity.Collections.NativeArray<Unity.Mathematics.int2> value) : System.Void`  
- `public Write(Unity.Collections.NativeArray<System.UInt16> value) : System.Void`  
- `public Write(Unity.Collections.NativeArray<System.Byte> value) : System.Void`  
- `public Write(Unity.Collections.NativeArray<Unity.Mathematics.float4> value) : System.Void`  
- `public Write(Unity.Collections.NativeArray<Unity.Mathematics.float2> value) : System.Void`  
- `public Write(Unity.Collections.NativeArray<System.Byte> value, System.Int32 stride) : System.Void`  
- `public Write(Unity.Collections.NativeList<System.Int32> value) : System.Void`  
- `public Write<TSerializable>(Unity.Collections.NativeArray<TSerializable> value) : System.Void`  
- `public Write(Unity.Entities.Entity value) : System.Void`  
- `public Write(Unity.Entities.Entity value, System.Boolean ignoreVersion) : System.Void`  
- `public Write<TSerializable>(TSerializable value) : System.Void`  
- `public Write(Colossal.Mathematics.Bezier4x3 curve) : System.Void`  
- `public Write(System.String value) : System.Void`  
- `public Write(UnityEngine.Color value) : System.Void`  
- `public Write(UnityEngine.Color32 value) : System.Void`  
- `public Write(Unity.Mathematics.quaternion value) : System.Void`  
- `public Write(Unity.Mathematics.float4 value) : System.Void`  
- `public Write(Unity.Mathematics.float3 value) : System.Void`  
- `public Write(Unity.Mathematics.float2 value) : System.Void`  
- `public Write(Unity.Mathematics.int4 value) : System.Void`  
- `public Write(Unity.Mathematics.int3 value) : System.Void`  
- `public Write(Unity.Mathematics.int2 value) : System.Void`  
- `public Write(Unity.Mathematics.bool4 value) : System.Void`  
- `public Write(Unity.Mathematics.bool3 value) : System.Void`  
- `public Write(Unity.Mathematics.bool2 value) : System.Void`  
- `public Write(Unity.Mathematics.uint4 value) : System.Void`  
- `public Write(Colossal.Hash128 hash) : System.Void`  
- `public Write(System.Char value) : System.Void`  
- `public Write(System.Single value) : System.Void`  
- `public Write(System.Double value) : System.Void`  
- `public Write(System.Int32 value) : System.Void`  
- `public Write(System.UInt32 value) : System.Void`  
- `public Write(System.Int16 value) : System.Void`  
- `public Write(System.UInt16 value) : System.Void`  
- `public Write(System.SByte value) : System.Void`  
- `public Write(System.Byte value) : System.Void`  
- `public Write(System.Int64 value) : System.Void`  
- `public Write(System.UInt64 value) : System.Void`  
- `public Write(System.Boolean value) : System.Void`  

