# Colossal.OdinSerializer.WeakArrayFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.WeakBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public sealed class WeakArrayFormatter : Colossal.OdinSerializer.WeakBaseFormatter, Colossal.OdinSerializer.IFormatter
{
    private readonly Colossal.OdinSerializer.Serializer ValueReaderWriter;
    private readonly System.Type ElementType;

    public WeakArrayFormatter(System.Type arrayType, System.Type elementType);

    protected virtual System.Void DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Object GetUninitializedObject();
    protected virtual System.Void SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private readonly Colossal.OdinSerializer.Serializer ValueReaderWriter`  

```csharp
private readonly Colossal.OdinSerializer.Serializer ValueReaderWriter;
```

- `private readonly System.Type ElementType`  

```csharp
private readonly System.Type ElementType;
```


## Constructors

- `public WeakArrayFormatter(System.Type arrayType, System.Type elementType)`  

```csharp
public WeakArrayFormatter(System.Type arrayType, System.Type elementType);
```


## Methods

- `protected virtual DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual GetUninitializedObject() : System.Object`  

```csharp
protected virtual System.Object GetUninitializedObject();
```

- `protected virtual SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
```


