# Colossal.Serialization.Entities.SystemSerializer

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Constructors

- `protected SystemSerializer()`  

## Methods

- `public abstract DeserializeSystem<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public static DeserializeType<TReader>(Colossal.Serialization.Entities.ReaderData readerData, System.Collections.Generic.Dictionary<System.String, System.Type> typeTable, System.Type& systemType, System.Int32& overhead) : System.Boolean`  
- `public abstract GetSystemType() : System.Type`  
- `public virtual Initialize(Unity.Collections.NativeArray<System.Int32> dataSizes, System.Int32 sizeIndex) : System.Void`  
- `public abstract SerializeSystem<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SerializeType<TWriter>(Colossal.Serialization.Entities.WriterData writerData, System.Int32& overhead) : System.Void`  
- `public abstract SetDefaults(Colossal.Serialization.Entities.Context context, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

