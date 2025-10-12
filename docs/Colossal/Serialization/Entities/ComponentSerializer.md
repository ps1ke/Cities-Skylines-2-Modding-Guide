# Colossal.Serialization.Entities.ComponentSerializer

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Constructors

- `protected ComponentSerializer()`  

## Methods

- `public virtual Apply(Unity.Entities.ExclusiveEntityTransaction transaction, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public virtual Clear() : System.Void`  
- `public abstract DeserializeData<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Collections.NativeArray<Unity.Entities.Entity> entities, Colossal.Serialization.Entities.ComponentSerializerType serializerType, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public static DeserializeType<TReader>(Colossal.Serialization.Entities.ReaderData readerData, System.Collections.Generic.Dictionary<System.String, System.Type> typeTable, Unity.Entities.ComponentType& componentType, Colossal.Serialization.Entities.ComponentSerializerType& serializerType, System.Int32& overhead) : System.Boolean`  
- `public virtual Dispose() : System.Void`  
- `public abstract GetComponentType() : System.Type`  
- `public abstract GetSerializerType() : Colossal.Serialization.Entities.ComponentSerializerType`  
- `public virtual Initialize(Unity.Entities.SystemBase system, Unity.Collections.NativeArray<System.Int32> dataSizes, System.Int32 sizeIndex) : System.Void`  
- `public abstract SerializeData<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Collections.NativeList<Colossal.Serialization.Entities.ComponentSerializerChunk> chunks, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SerializeType<TWriter>(Colossal.Serialization.Entities.WriterData writerData, System.Int32& overhead) : System.Void`  
- `public virtual Update(Unity.Entities.SystemBase system, Colossal.Serialization.Entities.Context context) : System.Void`  

