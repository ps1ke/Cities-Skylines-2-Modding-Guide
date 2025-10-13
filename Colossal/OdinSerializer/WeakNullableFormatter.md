# Colossal.OdinSerializer.WeakNullableFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.WeakBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public sealed class WeakNullableFormatter : Colossal.OdinSerializer.WeakBaseFormatter, Colossal.OdinSerializer.IFormatter
{
    private readonly Colossal.OdinSerializer.Serializer ValueSerializer;

    public WeakNullableFormatter(System.Type nullableType);

    protected virtual System.Void DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Object GetUninitializedObject();
    protected virtual System.Void SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private readonly Colossal.OdinSerializer.Serializer ValueSerializer`  

```csharp
private readonly Colossal.OdinSerializer.Serializer ValueSerializer;
```


## Constructors

- `public WeakNullableFormatter(System.Type nullableType)`  

```csharp
public WeakNullableFormatter(System.Type nullableType);
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


