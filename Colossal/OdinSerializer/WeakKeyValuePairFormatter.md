# Colossal.OdinSerializer.WeakKeyValuePairFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.WeakBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public sealed class WeakKeyValuePairFormatter : Colossal.OdinSerializer.WeakBaseFormatter, Colossal.OdinSerializer.IFormatter
{
    private readonly Colossal.OdinSerializer.Serializer KeySerializer;
    private readonly Colossal.OdinSerializer.Serializer ValueSerializer;
    private readonly System.Reflection.PropertyInfo KeyProperty;
    private readonly System.Reflection.PropertyInfo ValueProperty;

    public WeakKeyValuePairFormatter(System.Type serializedType);

    protected virtual System.Void DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private readonly Colossal.OdinSerializer.Serializer KeySerializer`  

```csharp
private readonly Colossal.OdinSerializer.Serializer KeySerializer;
```

- `private readonly Colossal.OdinSerializer.Serializer ValueSerializer`  

```csharp
private readonly Colossal.OdinSerializer.Serializer ValueSerializer;
```

- `private readonly System.Reflection.PropertyInfo KeyProperty`  

```csharp
private readonly System.Reflection.PropertyInfo KeyProperty;
```

- `private readonly System.Reflection.PropertyInfo ValueProperty`  

```csharp
private readonly System.Reflection.PropertyInfo ValueProperty;
```


## Constructors

- `public WeakKeyValuePairFormatter(System.Type serializedType)`  

```csharp
public WeakKeyValuePairFormatter(System.Type serializedType);
```


## Methods

- `protected virtual DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected virtual System.Void DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
```


