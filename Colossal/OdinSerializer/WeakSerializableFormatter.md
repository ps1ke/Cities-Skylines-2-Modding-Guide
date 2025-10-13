# Colossal.OdinSerializer.WeakSerializableFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.WeakBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Code

```csharp
public sealed class WeakSerializableFormatter : Colossal.OdinSerializer.WeakBaseFormatter, Colossal.OdinSerializer.IFormatter
{
    private readonly System.Func<System.Runtime.Serialization.SerializationInfo, System.Runtime.Serialization.StreamingContext, System.Runtime.Serialization.ISerializable> ISerializableConstructor;
    private readonly Colossal.OdinSerializer.WeakReflectionFormatter ReflectionFormatter;

    public WeakSerializableFormatter(System.Type serializedType);

    protected virtual System.Void DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Object GetUninitializedObject();
    private System.Runtime.Serialization.SerializationInfo ReadSerializationInfo(Colossal.OdinSerializer.IDataReader reader);
    protected virtual System.Void SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
    private System.Void WriteSerializationInfo(System.Runtime.Serialization.SerializationInfo info, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private readonly System.Func<System.Runtime.Serialization.SerializationInfo, System.Runtime.Serialization.StreamingContext, System.Runtime.Serialization.ISerializable> ISerializableConstructor`  

```csharp
private readonly System.Func<System.Runtime.Serialization.SerializationInfo, System.Runtime.Serialization.StreamingContext, System.Runtime.Serialization.ISerializable> ISerializableConstructor;
```

- `private readonly Colossal.OdinSerializer.WeakReflectionFormatter ReflectionFormatter`  

```csharp
private readonly Colossal.OdinSerializer.WeakReflectionFormatter ReflectionFormatter;
```


## Constructors

- `public WeakSerializableFormatter(System.Type serializedType)`  

```csharp
public WeakSerializableFormatter(System.Type serializedType);
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

- `private ReadSerializationInfo(Colossal.OdinSerializer.IDataReader reader) : System.Runtime.Serialization.SerializationInfo`  

```csharp
private System.Runtime.Serialization.SerializationInfo ReadSerializationInfo(Colossal.OdinSerializer.IDataReader reader);
```

- `protected virtual SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
protected virtual System.Void SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer);
```

- `private WriteSerializationInfo(System.Runtime.Serialization.SerializationInfo info, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
private System.Void WriteSerializationInfo(System.Runtime.Serialization.SerializationInfo info, Colossal.OdinSerializer.IDataWriter writer);
```


## Nested types

- `Colossal.OdinSerializer.WeakSerializableFormatter+<>c__DisplayClass2_0`  

