# Colossal.OdinSerializer.WeakQueueFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.WeakBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Fields

- `private readonly Colossal.OdinSerializer.Serializer ElementSerializer`  
- `private readonly System.Boolean IsPlainQueue`  
- `private System.Reflection.MethodInfo EnqueueMethod`  

## Constructors

- `public WeakQueueFormatter(System.Type serializedType)`  

## Methods

- `protected virtual DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  
- `protected virtual GetUninitializedObject() : System.Object`  
- `protected virtual SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

