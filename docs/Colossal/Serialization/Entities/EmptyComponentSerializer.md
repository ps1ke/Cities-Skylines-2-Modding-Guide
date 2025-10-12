# Colossal.Serialization.Entities.EmptyComponentSerializer

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** class public  

**Base:** `Colossal.Serialization.Entities.ComponentSerializer`  

## Fields

- `private System.Type m_ComponentType`  
- `private System.Int32* m_SizePtr`  

## Constructors

- `public EmptyComponentSerializer(System.Type componentType)`  

## Methods

- `public virtual DeserializeData<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Collections.NativeArray<Unity.Entities.Entity> entities, Colossal.Serialization.Entities.ComponentSerializerType serializerType, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public virtual GetComponentType() : System.Type`  
- `public virtual GetSerializerType() : Colossal.Serialization.Entities.ComponentSerializerType`  
- `public virtual Initialize(Unity.Entities.SystemBase system, Unity.Collections.NativeArray<System.Int32> dataSizes, System.Int32 sizeIndex) : System.Void`  
- `public virtual SerializeData<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Collections.NativeList<Colossal.Serialization.Entities.ComponentSerializerChunk> chunks, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Colossal.Serialization.Entities.EmptyComponentSerializer+DeserializeEmptyComponentJob<TReader>`  

