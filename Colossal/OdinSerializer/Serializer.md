# Colossal.OdinSerializer.Serializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Code

```csharp
public abstract class Serializer
{
    private static readonly System.Collections.Generic.Dictionary<System.Type, System.Type> PrimitiveReaderWriterTypes;
    private static readonly System.Object LOCK;
    private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.Serializer> Weak_ReaderWriterCache;
    private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.Serializer> Strong_ReaderWriterCache;

    protected Serializer();

    private static Colossal.OdinSerializer.Serializer Create(System.Type type, System.Boolean allowWeakfallback);
    protected static System.Void FireOnSerializedType(System.Type type);
    public static Colossal.OdinSerializer.Serializer<T> Get<T>();
    public static Colossal.OdinSerializer.Serializer Get(System.Type type);
    private static Colossal.OdinSerializer.Serializer Get(System.Type type, System.Boolean allowWeakFallback);
    public static Colossal.OdinSerializer.Serializer GetForValue(System.Object value);
    private static System.Void LogAOTError(System.Type type, System.ExecutionEngineException ex);
    public abstract System.Object ReadValueWeak(Colossal.OdinSerializer.IDataReader reader);
    public System.Void WriteValueWeak(System.Object value, Colossal.OdinSerializer.IDataWriter writer);
    public abstract System.Void WriteValueWeak(System.String name, System.Object value, Colossal.OdinSerializer.IDataWriter writer);
}
```


## Fields

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Type> PrimitiveReaderWriterTypes`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, System.Type> PrimitiveReaderWriterTypes;
```

- `private static readonly System.Object LOCK`  

```csharp
private static readonly System.Object LOCK;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.Serializer> Weak_ReaderWriterCache`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.Serializer> Weak_ReaderWriterCache;
```

- `private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.Serializer> Strong_ReaderWriterCache`  

```csharp
private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.Serializer> Strong_ReaderWriterCache;
```


## Constructors

- `protected Serializer()`  

```csharp
protected Serializer();
```


## Methods

- `private static Create(System.Type type, System.Boolean allowWeakfallback) : Colossal.OdinSerializer.Serializer`  

```csharp
private static Colossal.OdinSerializer.Serializer Create(System.Type type, System.Boolean allowWeakfallback);
```

- `protected static FireOnSerializedType(System.Type type) : System.Void`  

```csharp
protected static System.Void FireOnSerializedType(System.Type type);
```

- `public static Get<T>() : Colossal.OdinSerializer.Serializer<T>`  

```csharp
public static Colossal.OdinSerializer.Serializer<T> Get<T>();
```

- `public static Get(System.Type type) : Colossal.OdinSerializer.Serializer`  

```csharp
public static Colossal.OdinSerializer.Serializer Get(System.Type type);
```

- `private static Get(System.Type type, System.Boolean allowWeakFallback) : Colossal.OdinSerializer.Serializer`  

```csharp
private static Colossal.OdinSerializer.Serializer Get(System.Type type, System.Boolean allowWeakFallback);
```

- `public static GetForValue(System.Object value) : Colossal.OdinSerializer.Serializer`  

```csharp
public static Colossal.OdinSerializer.Serializer GetForValue(System.Object value);
```

- `private static LogAOTError(System.Type type, System.ExecutionEngineException ex) : System.Void`  

```csharp
private static System.Void LogAOTError(System.Type type, System.ExecutionEngineException ex);
```

- `public abstract ReadValueWeak(Colossal.OdinSerializer.IDataReader reader) : System.Object`  

```csharp
public abstract System.Object ReadValueWeak(Colossal.OdinSerializer.IDataReader reader);
```

- `public WriteValueWeak(System.Object value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public System.Void WriteValueWeak(System.Object value, Colossal.OdinSerializer.IDataWriter writer);
```

- `public abstract WriteValueWeak(System.String name, System.Object value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

```csharp
public abstract System.Void WriteValueWeak(System.String name, System.Object value, Colossal.OdinSerializer.IDataWriter writer);
```


