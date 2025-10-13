# Colossal.Serialization.Entities.WriterData

**Assembly:** `Colossal.Core`  
**Namespace:** `Colossal.Serialization.Entities`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct WriterData
{
    private Colossal.Serialization.Entities.Context m_Context;
    private Unity.Collections.NativeList<System.Byte> m_Buffer;

    public WriterData(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeList<System.Byte> buffer);

    public TWriter GetWriter<TWriter>();
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


## Constructors

- `public WriterData(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeList<System.Byte> buffer)`  

```csharp
public WriterData(Colossal.Serialization.Entities.Context context, Unity.Collections.NativeList<System.Byte> buffer);
```


## Methods

- `public GetWriter<TWriter>() : TWriter`  

```csharp
public TWriter GetWriter<TWriter>();
```


