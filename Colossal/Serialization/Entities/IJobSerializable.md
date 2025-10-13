# Colossal.Serialization.Entities.IJobSerializable

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IJobSerializable
{
    public abstract Unity.Jobs.JobHandle Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
    public abstract Unity.Jobs.JobHandle Serialize<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps);
    public abstract Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context);
}
```


## Methods

- `public abstract Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public abstract Unity.Jobs.JobHandle Deserialize<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
```

- `public abstract Serialize<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public abstract Unity.Jobs.JobHandle Serialize<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps);
```

- `public abstract SetDefaults(Colossal.Serialization.Entities.Context context) : Unity.Jobs.JobHandle`  

```csharp
public abstract Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context);
```


