# Colossal.OdinSerializer.WeakStackFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.WeakBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class WeakStackFormatter : Colossal.OdinSerializer.WeakBaseFormatter, Colossal.OdinSerializer.IFormatter
{
    private readonly Colossal.OdinSerializer.Serializer ElementSerializer;
    private readonly System.Boolean IsPlainStack;
    private readonly System.Reflection.MethodInfo PushMethod;

    public WeakStackFormatter(System.Type serializedType);

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

- `private readonly System.Boolean IsPlainStack`  

```csharp
private readonly System.Boolean IsPlainStack;
```

- `private readonly System.Reflection.MethodInfo PushMethod`  

```csharp
private readonly System.Reflection.MethodInfo PushMethod;
```


## Constructors

- `public WeakStackFormatter(System.Type serializedType)`  

```csharp
public WeakStackFormatter(System.Type serializedType);
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


