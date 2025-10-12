# Colossal.Serialization.Entities.BinaryReader

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Serialization.Entities.IReader`  

## Fields

- `private Unity.Collections.NativeArray<System.Byte> m_Buffer`  
- `private Unity.Collections.NativeReference<System.Int32> m_Position`  
- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_EntityTable`  
- `private Colossal.Serialization.Entities.Context <context>k__BackingField`  

## Properties

- `public Colossal.Serialization.Entities.Context context { get; private set }`  

## Methods

- `public Begin() : Colossal.Serialization.Entities.ReaderBlock`  
- `public Begin(System.Int32& size) : Colossal.Serialization.Entities.ReaderBlock`  
- `public End(Colossal.Serialization.Entities.ReaderBlock block) : System.Boolean`  
- `public Initialize(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeArray<System.Byte> buffer, Unity.Collections.NativeReference<System.Int32> position, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable) : System.Void`  
- `public Read(Unity.Collections.NativeArray<Unity.Entities.Entity> value) : System.Void`  
- `public Read(Unity.Collections.NativeArray<System.Int32> value) : System.Void`  
- `public Read(Unity.Collections.NativeArray<Unity.Mathematics.int2> value) : System.Void`  
- `public Read(Unity.Collections.NativeArray<System.UInt16> value) : System.Void`  
- `public Read(Unity.Collections.NativeArray<System.Byte> value) : System.Void`  
- `public Read(Unity.Collections.NativeArray<Unity.Mathematics.float4> value) : System.Void`  
- `public Read(Unity.Collections.NativeArray<Unity.Mathematics.float2> value) : System.Void`  
- `public Read(Unity.Collections.NativeArray<System.Byte> value, System.Int32 stride) : System.Void`  
- `public Read(Unity.Collections.NativeList<System.Int32> value) : System.Void`  
- `public Read(Unity.Collections.NativeList<Unity.Entities.Entity> value) : System.Void`  
- `public Read<TSerializable>(Unity.Collections.NativeArray<TSerializable> value) : System.Void`  
- `public Read(Unity.Entities.Entity& value) : System.Void`  
- `public Read<TSerializable>(TSerializable& value) : System.Void`  
- `public Read<TSerializable>(TSerializable value) : System.Void`  
- `public Read(Colossal.Mathematics.Bezier4x3& curve) : System.Void`  
- `public Read(System.String& value) : System.Void`  
- `public Read(UnityEngine.Color& value) : System.Void`  
- `public Read(UnityEngine.Color32& value) : System.Void`  
- `public Read(Unity.Mathematics.quaternion& value) : System.Void`  
- `public Read(Unity.Mathematics.float4& value) : System.Void`  
- `public Read(Unity.Mathematics.float3& value) : System.Void`  
- `public Read(Unity.Mathematics.float2& value) : System.Void`  
- `public Read(Unity.Mathematics.int4& value) : System.Void`  
- `public Read(Unity.Mathematics.int3& value) : System.Void`  
- `public Read(Unity.Mathematics.int2& value) : System.Void`  
- `public Read(Unity.Mathematics.bool4& value) : System.Void`  
- `public Read(Unity.Mathematics.bool3& value) : System.Void`  
- `public Read(Unity.Mathematics.bool2& value) : System.Void`  
- `public Read(Unity.Mathematics.uint4& value) : System.Void`  
- `public Read(Colossal.Hash128& hash) : System.Void`  
- `public Read(System.Char& value) : System.Void`  
- `public Read(System.Single& value) : System.Void`  
- `public Read(System.Double& value) : System.Void`  
- `public Read(System.Int32& value) : System.Void`  
- `public Read(System.UInt32& value) : System.Void`  
- `public Read(System.Int16& value) : System.Void`  
- `public Read(System.UInt16& value) : System.Void`  
- `public Read(System.SByte& value) : System.Void`  
- `public Read(System.Byte& value) : System.Void`  
- `public Read(System.Int64& value) : System.Void`  
- `public Read(System.UInt64& value) : System.Void`  
- `public Read(System.Boolean& value) : System.Void`  
- `public Skip(System.Int32 size) : System.Void`  

