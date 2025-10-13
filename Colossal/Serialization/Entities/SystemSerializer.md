# Colossal.Serialization.Entities.SystemSerializer

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Code

```csharp
public abstract class SystemSerializer
{
    protected SystemSerializer();

    public abstract Unity.Jobs.JobHandle DeserializeSystem<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
    public static System.Boolean DeserializeType<TReader>(Colossal.Serialization.Entities.ReaderData readerData, System.Collections.Generic.Dictionary<System.String, System.Type> typeTable, System.Type& systemType, System.Int32& overhead);
    public abstract System.Type GetSystemType();
    public virtual System.Void Initialize(Unity.Collections.NativeArray<System.Int32> dataSizes, System.Int32 sizeIndex);
    public abstract Unity.Jobs.JobHandle SerializeSystem<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps);
    public System.Void SerializeType<TWriter>(Colossal.Serialization.Entities.WriterData writerData, System.Int32& overhead);
    public abstract Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context, Unity.Jobs.JobHandle inputDeps);
}
```


## Constructors

- `protected SystemSerializer()`  

```csharp
protected SystemSerializer();
```


## Methods

- `public abstract DeserializeSystem<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public abstract Unity.Jobs.JobHandle DeserializeSystem<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
```

- `public static DeserializeType<TReader>(Colossal.Serialization.Entities.ReaderData readerData, System.Collections.Generic.Dictionary<System.String, System.Type> typeTable, System.Type& systemType, System.Int32& overhead) : System.Boolean`  

```csharp
public static System.Boolean DeserializeType<TReader>(Colossal.Serialization.Entities.ReaderData readerData, System.Collections.Generic.Dictionary<System.String, System.Type> typeTable, System.Type& systemType, System.Int32& overhead);
```

- `public abstract GetSystemType() : System.Type`  

```csharp
public abstract System.Type GetSystemType();
```

- `public virtual Initialize(Unity.Collections.NativeArray<System.Int32> dataSizes, System.Int32 sizeIndex) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Collections.NativeArray<System.Int32> dataSizes, System.Int32 sizeIndex);
```

- `public abstract SerializeSystem<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public abstract Unity.Jobs.JobHandle SerializeSystem<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps);
```

- `public SerializeType<TWriter>(Colossal.Serialization.Entities.WriterData writerData, System.Int32& overhead) : System.Void`  

```csharp
public System.Void SerializeType<TWriter>(Colossal.Serialization.Entities.WriterData writerData, System.Int32& overhead);
```

- `public abstract SetDefaults(Colossal.Serialization.Entities.Context context, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public abstract Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context, Unity.Jobs.JobHandle inputDeps);
```


