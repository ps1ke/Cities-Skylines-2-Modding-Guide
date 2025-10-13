# Colossal.OdinSerializer.WeakQueueFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.WeakBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public class WeakQueueFormatter : Colossal.OdinSerializer.WeakBaseFormatter, Colossal.OdinSerializer.IFormatter
{
    private readonly Colossal.OdinSerializer.Serializer ElementSerializer;
    private readonly System.Boolean IsPlainQueue;
    private System.Reflection.MethodInfo EnqueueMethod;

    public WeakQueueFormatter(System.Type serializedType);

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

- `private readonly System.Boolean IsPlainQueue`  

```csharp
private readonly System.Boolean IsPlainQueue;
```

- `private System.Reflection.MethodInfo EnqueueMethod`  

```csharp
private System.Reflection.MethodInfo EnqueueMethod;
```


## Constructors

- `public WeakQueueFormatter(System.Type serializedType)`  

```csharp
public WeakQueueFormatter(System.Type serializedType);
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


