# Colossal.OdinSerializer.WeakBaseFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public abstract class WeakBaseFormatter : Colossal.OdinSerializer.IFormatter
{
    protected readonly System.Type SerializedType;
    protected readonly Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] OnSerializingCallbacks;
    protected readonly Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] OnSerializedCallbacks;
    protected readonly Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] OnDeserializingCallbacks;
    protected readonly Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] OnDeserializedCallbacks;
    protected readonly System.Boolean IsValueType;
    protected readonly System.Boolean ImplementsISerializationCallbackReceiver;
    protected readonly System.Boolean ImplementsIDeserializationCallback;
    protected readonly System.Boolean ImplementsIObjectReference;

    private System.Type Colossal.OdinSerializer.IFormatter.SerializedType { private get; }

    public WeakBaseFormatter(System.Type serializedType);

    private static Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback CreateCallback(System.Reflection.MethodInfo info);
    public System.Object Deserialize(Colossal.OdinSerializer.IDataReader reader);
    protected abstract System.Void DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader);
    private static Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] GetCallbacks(System.Reflection.MethodInfo[] methods, System.Type callbackAttribute, System.Collections.Generic.List`1[[Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback, Colossal.OdinSerializer, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null]]& list);
    protected virtual System.Object GetUninitializedObject();
    protected System.Void InvokeOnDeserializingCallbacks(System.Object value, Colossal.OdinSerializer.DeserializationContext context);
    protected System.Void RegisterReferenceID(System.Object value, Colossal.OdinSerializer.IDataReader reader);
    public System.Void Serialize(System.Object value, Colossal.OdinSerializer.IDataWriter writer);
    protected abstract System.Void SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `protected readonly System.Type SerializedType`  

```csharp
protected readonly System.Type SerializedType;
```

- `protected readonly Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] OnSerializingCallbacks`  

```csharp
protected readonly Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] OnSerializingCallbacks;
```

- `protected readonly Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] OnSerializedCallbacks`  

```csharp
protected readonly Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] OnSerializedCallbacks;
```

- `protected readonly Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] OnDeserializingCallbacks`  

```csharp
protected readonly Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] OnDeserializingCallbacks;
```

- `protected readonly Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] OnDeserializedCallbacks`  

```csharp
protected readonly Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] OnDeserializedCallbacks;
```

- `protected readonly System.Boolean IsValueType`  

```csharp
protected readonly System.Boolean IsValueType;
```

- `protected readonly System.Boolean ImplementsISerializationCallbackReceiver`  

```csharp
protected readonly System.Boolean ImplementsISerializationCallbackReceiver;
```

- `protected readonly System.Boolean ImplementsIDeserializationCallback`  

```csharp
protected readonly System.Boolean ImplementsIDeserializationCallback;
```

- `protected readonly System.Boolean ImplementsIObjectReference`  

```csharp
protected readonly System.Boolean ImplementsIObjectReference;
```


## Properties

- `private System.Type Colossal.OdinSerializer.IFormatter.SerializedType { private get }`  

```csharp
private System.Type Colossal.OdinSerializer.IFormatter.SerializedType { private get; }
```


## Constructors

- `public WeakBaseFormatter(System.Type serializedType)`  

```csharp
public WeakBaseFormatter(System.Type serializedType);
```


## Methods

- `private static CreateCallback(System.Reflection.MethodInfo info) : Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback`  

```csharp
private static Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback CreateCallback(System.Reflection.MethodInfo info);
```

- `public Deserialize(Colossal.OdinSerializer.IDataReader reader) : System.Object`  

```csharp
public System.Object Deserialize(Colossal.OdinSerializer.IDataReader reader);
```

- `protected abstract DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected abstract System.Void DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader);
```

- `private static GetCallbacks(System.Reflection.MethodInfo[] methods, System.Type callbackAttribute, System.Collections.Generic.List`1[[Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback, Colossal.OdinSerializer, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null]]& list) : Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[]`  

```csharp
private static Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] GetCallbacks(System.Reflection.MethodInfo[] methods, System.Type callbackAttribute, System.Collections.Generic.List`1[[Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback, Colossal.OdinSerializer, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null]]& list);
```

- `protected virtual GetUninitializedObject() : System.Object`  

```csharp
protected virtual System.Object GetUninitializedObject();
```

- `protected InvokeOnDeserializingCallbacks(System.Object value, Colossal.OdinSerializer.DeserializationContext context) : System.Void`  

```csharp
protected System.Void InvokeOnDeserializingCallbacks(System.Object value, Colossal.OdinSerializer.DeserializationContext context);
```

- `protected RegisterReferenceID(System.Object value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  

```csharp
protected System.Void RegisterReferenceID(System.Object value, Colossal.OdinSerializer.IDataReader reader);
```

- `public Serialize(System.Object value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public System.Void Serialize(System.Object value, Colossal.OdinSerializer.IDataWriter writer);
```

- `protected abstract SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected abstract System.Void SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
```


## Nested types

- `Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback`  
- `Colossal.OdinSerializer.WeakBaseFormatter+<>c__DisplayClass14_0`  

