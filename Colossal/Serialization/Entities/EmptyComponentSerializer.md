# Colossal.Serialization.Entities.EmptyComponentSerializer

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** class public  

**Base:** `Colossal.Serialization.Entities.ComponentSerializer`  

## Code

```csharp
public class EmptyComponentSerializer : Colossal.Serialization.Entities.ComponentSerializer
{
    private System.Type m_ComponentType;
    private System.Int32* m_SizePtr;

    public EmptyComponentSerializer(System.Type componentType);

    public virtual Unity.Jobs.JobHandle DeserializeData<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Collections.NativeArray<Unity.Entities.Entity> entities, Colossal.Serialization.Entities.ComponentSerializerType serializerType, Unity.Jobs.JobHandle inputDeps);
    public virtual System.Type GetComponentType();
    public virtual Colossal.Serialization.Entities.ComponentSerializerType GetSerializerType();
    public virtual System.Void Initialize(Unity.Entities.SystemBase system, Unity.Collections.NativeArray<System.Int32> dataSizes, System.Int32 sizeIndex);
    public virtual Unity.Jobs.JobHandle SerializeData<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Collections.NativeList<Colossal.Serialization.Entities.ComponentSerializerChunk> chunks, Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private System.Type m_ComponentType`  

```csharp
private System.Type m_ComponentType;
```

- `private System.Int32* m_SizePtr`  

```csharp
private System.Int32* m_SizePtr;
```


## Constructors

- `public EmptyComponentSerializer(System.Type componentType)`  

```csharp
public EmptyComponentSerializer(System.Type componentType);
```


## Methods

- `public virtual DeserializeData<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Collections.NativeArray<Unity.Entities.Entity> entities, Colossal.Serialization.Entities.ComponentSerializerType serializerType, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public virtual Unity.Jobs.JobHandle DeserializeData<TReader>(Colossal.Serialization.Entities.EntityReaderData readerData, Unity.Collections.NativeArray<Unity.Entities.Entity> entities, Colossal.Serialization.Entities.ComponentSerializerType serializerType, Unity.Jobs.JobHandle inputDeps);
```

- `public virtual GetComponentType() : System.Type`  

```csharp
public virtual System.Type GetComponentType();
```

- `public virtual GetSerializerType() : Colossal.Serialization.Entities.ComponentSerializerType`  

```csharp
public virtual Colossal.Serialization.Entities.ComponentSerializerType GetSerializerType();
```

- `public virtual Initialize(Unity.Entities.SystemBase system, Unity.Collections.NativeArray<System.Int32> dataSizes, System.Int32 sizeIndex) : System.Void`  

```csharp
public virtual System.Void Initialize(Unity.Entities.SystemBase system, Unity.Collections.NativeArray<System.Int32> dataSizes, System.Int32 sizeIndex);
```

- `public virtual SerializeData<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Collections.NativeList<Colossal.Serialization.Entities.ComponentSerializerChunk> chunks, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public virtual Unity.Jobs.JobHandle SerializeData<TWriter>(Colossal.Serialization.Entities.EntityWriterData writerData, Unity.Collections.NativeList<Colossal.Serialization.Entities.ComponentSerializerChunk> chunks, Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Colossal.Serialization.Entities.EmptyComponentSerializer+DeserializeEmptyComponentJob<TReader>`  

