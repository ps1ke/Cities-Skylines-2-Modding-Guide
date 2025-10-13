# Colossal.Serialization.Entities.ComponentSerializer

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Code

```csharp
public abstract class ComponentSerializer
{
    protected ComponentSerializer();

    public virtual Unity.Jobs.JobHandle Apply(Unity.Entities.ExclusiveEntityTransaction transaction, Unity.Jobs.JobHandle inputDeps);
    public virtual System.Void Clear();
    public abstract Unity.Jobs.JobHandle DeserializeData<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Collections.NativeArray<Unity.Entities.Entity> entities, Colossal.Serialization.Entities.ComponentSerializerType serializerType, Unity.Jobs.JobHandle inputDeps);
    public static System.Boolean DeserializeType<TReader>(Colossal.Serialization.Entities.ReaderData readerData, System.Collections.Generic.Dictionary<System.String, System.Type> typeTable, Unity.Entities.ComponentType& componentType, Colossal.Serialization.Entities.ComponentSerializerType& serializerType, System.Int32& overhead);
    public virtual System.Void Dispose();
    public abstract System.Type GetComponentType();
    public abstract Colossal.Serialization.Entities.ComponentSerializerType GetSerializerType();
    public virtual System.Void Initialize(Unity.Entities.SystemBase system, Unity.Collections.NativeArray<System.Int32> dataSizes, System.Int32 sizeIndex);
    public abstract Unity.Jobs.JobHandle SerializeData<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Collections.NativeList<Colossal.Serialization.Entities.ComponentSerializerChunk> chunks, Unity.Jobs.JobHandle inputDeps);
    public System.Void SerializeType<TWriter>(Colossal.Serialization.Entities.WriterData writerData, System.Int32& overhead);
    public virtual System.Void Update(Unity.Entities.SystemBase system, Colossal.Serialization.Entities.Context context);
}
```


## Constructors

- `protected ComponentSerializer()`  

```csharp
protected ComponentSerializer();
```


## Methods

- `public virtual Apply(Unity.Entities.ExclusiveEntityTransaction transaction, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public virtual Unity.Jobs.JobHandle Apply(Unity.Entities.ExclusiveEntityTransaction transaction, Unity.Jobs.JobHandle inputDeps);
```

- `public virtual Clear() : System.Void`  

```csharp
public virtual System.Void Clear();
```

- `public abstract DeserializeData<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Collections.NativeArray<Unity.Entities.Entity> entities, Colossal.Serialization.Entities.ComponentSerializerType serializerType, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public abstract Unity.Jobs.JobHandle DeserializeData<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Collections.NativeArray<Unity.Entities.Entity> entities, Colossal.Serialization.Entities.ComponentSerializerType serializerType, Unity.Jobs.JobHandle inputDeps);
```

- `public static DeserializeType<TReader>(Colossal.Serialization.Entities.ReaderData readerData, System.Collections.Generic.Dictionary<System.String, System.Type> typeTable, Unity.Entities.ComponentType& componentType, Colossal.Serialization.Entities.ComponentSerializerType& serializerType, System.Int32& overhead) : System.Boolean`  

```csharp
public static System.Boolean DeserializeType<TReader>(Colossal.Serialization.Entities.ReaderData readerData, System.Collections.Generic.Dictionary<System.String, System.Type> typeTable, Unity.Entities.ComponentType& componentType, Colossal.Serialization.Entities.ComponentSerializerType& serializerType, System.Int32& overhead);
```

- `public virtual Dispose() : System.Void`  

```csharp
public virtual System.Void Dispose();
```

- `public abstract GetComponentType() : System.Type`  

```csharp
public abstract System.Type GetComponentType();
```

- `public abstract GetSerializerType() : Colossal.Serialization.Entities.ComponentSerializerType`  

```csharp
public abstract Colossal.Serialization.Entities.ComponentSerializerType GetSerializerType();
```

- `public virtual Initialize(Unity.Entities.SystemBase system, Unity.Collections.NativeArray<System.Int32> dataSizes, System.Int32 sizeIndex) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.SystemBase system, Unity.Collections.NativeArray<System.Int32> dataSizes, System.Int32 sizeIndex);
```

- `public abstract SerializeData<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Collections.NativeList<Colossal.Serialization.Entities.ComponentSerializerChunk> chunks, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public abstract Unity.Jobs.JobHandle SerializeData<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Collections.NativeList<Colossal.Serialization.Entities.ComponentSerializerChunk> chunks, Unity.Jobs.JobHandle inputDeps);
```

- `public SerializeType<TWriter>(Colossal.Serialization.Entities.WriterData writerData, System.Int32& overhead) : System.Void`  

```csharp
public System.Void SerializeType<TWriter>(Colossal.Serialization.Entities.WriterData writerData, System.Int32& overhead);
```

- `public virtual Update(Unity.Entities.SystemBase system, Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public virtual System.Void Update(Unity.Entities.SystemBase system, Colossal.Serialization.Entities.Context context);
```


