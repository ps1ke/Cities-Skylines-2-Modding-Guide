# Colossal.Serialization.Entities.EntityWriterData

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct EntityWriterData
{
    private Colossal.Serialization.Entities.Context m_Context;
    private Unity.Collections.NativeList<System.Byte> m_Buffer;
    private Unity.Collections.NativeArray<Unity.Entities.Entity> m_EntityTable;

    public EntityWriterData(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeList<System.Byte> buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable);

    public TWriter GetWriter<TWriter>();
    public TWriter GetWriter<TWriter>(Unity.Collections.NativeList<System.Byte> buffer);
}
```


## Fields

- `private Colossal.Serialization.Entities.Context m_Context`  

```csharp
private Colossal.Serialization.Entities.Context m_Context;
```

- `private Unity.Collections.NativeList<System.Byte> m_Buffer`  

```csharp
private Unity.Collections.NativeList<System.Byte> m_Buffer;
```

- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_EntityTable`  

```csharp
private Unity.Collections.NativeArray<Unity.Entities.Entity> m_EntityTable;
```


## Constructors

- `public EntityWriterData(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeList<System.Byte> buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable)`  

```csharp
public EntityWriterData(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeList<System.Byte> buffer, Unity.Collections.NativeArray<Unity.Entities.Entity> entityTable);
```


## Methods

- `public GetWriter<TWriter>() : TWriter`  

```csharp
public TWriter GetWriter<TWriter>();
```

- `public GetWriter<TWriter>(Unity.Collections.NativeList<System.Byte> buffer) : TWriter`  

```csharp
public TWriter GetWriter<TWriter>(Unity.Collections.NativeList<System.Byte> buffer);
```


