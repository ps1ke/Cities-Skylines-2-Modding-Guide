# Colossal.OdinSerializer.Serializer

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class abstract public  

**Base:** `System.Object`  

## Fields

- `private static readonly System.Collections.Generic.Dictionary<System.Type, System.Type> PrimitiveReaderWriterTypes`  
- `private static readonly System.Object LOCK`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.Serializer> Weak_ReaderWriterCache`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.Serializer> Strong_ReaderWriterCache`  

## Constructors

- `protected Serializer()`  

## Methods

- `private static Create(System.Type type, System.Boolean allowWeakfallback) : Colossal.OdinSerializer.Serializer`  
- `protected static FireOnSerializedType(System.Type type) : System.Void`  
- `public static Get<T>() : Colossal.OdinSerializer.Serializer<T>`  
- `public static Get(System.Type type) : Colossal.OdinSerializer.Serializer`  
- `private static Get(System.Type type, System.Boolean allowWeakFallback) : Colossal.OdinSerializer.Serializer`  
- `public static GetForValue(System.Object value) : Colossal.OdinSerializer.Serializer`  
- `private static LogAOTError(System.Type type, System.ExecutionEngineException ex) : System.Void`  
- `public abstract ReadValueWeak(Colossal.OdinSerializer.IDataReader reader) : System.Object`  
- `public WriteValueWeak(System.Object value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  
- `public abstract WriteValueWeak(System.String name, System.Object value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

