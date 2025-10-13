# Colossal.Serialization.Entities.ObsoleteSystemSerializer

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** class public  

**Base:** `Colossal.Serialization.Entities.SystemSerializer`  

## Code

```csharp
public class ObsoleteSystemSerializer : Colossal.Serialization.Entities.SystemSerializer
{
    private System.Int32* m_SizePtr;

    public ObsoleteSystemSerializer();

    public virtual Unity.Jobs.JobHandle DeserializeSystem<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
    public virtual System.Type GetSystemType();
    public virtual System.Void Initialize(Unity.Collections.NativeArray<System.Int32> dataSizes, System.Int32 sizeIndex);
    public virtual Unity.Jobs.JobHandle SerializeSystem<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps);
    public virtual Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context, Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private System.Int32* m_SizePtr`  

```csharp
private System.Int32* m_SizePtr;
```


## Constructors

- `public ObsoleteSystemSerializer()`  

```csharp
public ObsoleteSystemSerializer();
```


## Methods

- `public virtual DeserializeSystem<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public virtual Unity.Jobs.JobHandle DeserializeSystem<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Jobs.JobHandle inputDeps);
```

- `public virtual GetSystemType() : System.Type`  

```csharp
public virtual System.Type GetSystemType();
```

- `public virtual Initialize(Unity.Collections.NativeArray<System.Int32> dataSizes, System.Int32 sizeIndex) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Collections.NativeArray<System.Int32> dataSizes, System.Int32 sizeIndex);
```

- `public virtual SerializeSystem<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public virtual Unity.Jobs.JobHandle SerializeSystem<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Jobs.JobHandle inputDeps);
```

- `public virtual SetDefaults(Colossal.Serialization.Entities.Context context, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public virtual Unity.Jobs.JobHandle SetDefaults(Colossal.Serialization.Entities.Context context, Unity.Jobs.JobHandle inputDeps);
```


