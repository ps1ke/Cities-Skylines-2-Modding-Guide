# Colossal.Serialization.Entities.EntityReaderData

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct EntityReaderData
{
    private Colossal.Serialization.Entities.Context m_Context;
    private Unity.Collections.NativeArray<System.Byte> m_Buffer;
    private Unity.Collections.NativeReference<System.Int32> m_Position;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_EntityTable;

    public EntityReaderData(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeArray<System.Byte> buffer, Unity.Collections.NativeReference<System.Int32> position, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable);

    public TReader GetReader<TReader>();
    public TReader GetReader<TReader>(Unity.Collections.NativeArray<System.Byte> buffer, Unity.Collections.NativeReference<System.Int32> position);
}
```


## Fields

- `private Colossal.Serialization.Entities.Context m_Context`  

```csharp
private Colossal.Serialization.Entities.Context m_Context;
```

- `private Unity.Collections.NativeArray<System.Byte> m_Buffer`  

```csharp
private Unity.Collections.NativeArray<System.Byte> m_Buffer;
```

- `private Unity.Collections.NativeReference<System.Int32> m_Position`  

```csharp
private Unity.Collections.NativeReference<System.Int32> m_Position;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_EntityTable`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_EntityTable;
```


## Constructors

- `public EntityReaderData(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeArray<System.Byte> buffer, Unity.Collections.NativeReference<System.Int32> position, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable)`  

```csharp
public EntityReaderData(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeArray<System.Byte> buffer, Unity.Collections.NativeReference<System.Int32> position, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable);
```


## Methods

- `public GetReader<TReader>() : TReader`  

```csharp
public TReader GetReader<TReader>();
```

- `public GetReader<TReader>(Unity.Collections.NativeArray<System.Byte> buffer, Unity.Collections.NativeReference<System.Int32> position) : TReader`  

```csharp
public TReader GetReader<TReader>(Unity.Collections.NativeArray<System.Byte> buffer, Unity.Collections.NativeReference<System.Int32> position);
```


