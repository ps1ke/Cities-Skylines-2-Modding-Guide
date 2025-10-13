# Colossal.OdinSerializer.WeakHashSetFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.WeakBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class WeakHashSetFormatter : Colossal.OdinSerializer.WeakBaseFormatter, Colossal.OdinSerializer.IFormatter
{
    private readonly Colossal.OdinSerializer.Serializer ElementSerializer;
    private readonly System.Reflection.MethodInfo AddMethod;
    private readonly System.Reflection.PropertyInfo CountProperty;

    public WeakHashSetFormatter(System.Type serializedType);

    protected virtual System.Void DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Object GetUninitializedObject();
    protected virtual System.Void SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private readonly Colossal.OdinSerializer.Serializer ElementSerializer`  

```csharp
private readonly Colossal.OdinSerializer.Serializer ElementSerializer;
```

- `private readonly System.Reflection.MethodInfo AddMethod`  

```csharp
private readonly System.Reflection.MethodInfo AddMethod;
```

- `private readonly System.Reflection.PropertyInfo CountProperty`  

```csharp
private readonly System.Reflection.PropertyInfo CountProperty;
```


## Constructors

- `public WeakHashSetFormatter(System.Type serializedType)`  

```csharp
public WeakHashSetFormatter(System.Type serializedType);
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


