# Colossal.Serialization.Entities.EntityWriterData

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Colossal.Serialization.Entities.Context m_Context`  
- `private Unity.Collections.NativeList<System.Byte> m_Buffer`  
- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_EntityTable`  

## Constructors

- `public EntityWriterData(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeList<System.Byte> buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable)`  

## Methods

- `public GetWriter<TWriter>() : TWriter`  
- `public GetWriter<TWriter>(Unity.Collections.NativeList<System.Byte> buffer) : TWriter`  

