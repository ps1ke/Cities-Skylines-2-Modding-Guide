# Colossal.Serialization.Entities.ReaderData

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ReaderData
{
    private Colossal.Serialization.Entities.Context m_Context;
    private Unity.Collections.NativeArray<System.Byte> m_Buffer;
    private Unity.Collections.NativeReference<System.Int32> m_Position;

    public ReaderData(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeArray<System.Byte> buffer, Unity.Collections.NativeReference<System.Int32> position);

    public TReader GetReader<TReader>();
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


## Constructors

- `public ReaderData(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeArray<System.Byte> buffer, Unity.Collections.NativeReference<System.Int32> position)`  

```csharp
public ReaderData(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeArray<System.Byte> buffer, Unity.Collections.NativeReference<System.Int32> position);
```


## Methods

- `public GetReader<TReader>() : TReader`  

```csharp
public TReader GetReader<TReader>();
```


