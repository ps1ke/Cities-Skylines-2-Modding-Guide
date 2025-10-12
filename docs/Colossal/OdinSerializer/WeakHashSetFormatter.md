# Colossal.OdinSerializer.WeakHashSetFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `Colossal.OdinSerializer.WeakBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Fields

- `private readonly Colossal.OdinSerializer.Serializer ElementSerializer`  
- `private readonly System.Reflection.MethodInfo AddMethod`  
- `private readonly System.Reflection.PropertyInfo CountProperty`  

## Constructors

- `public WeakHashSetFormatter(System.Type serializedType)`  

## Methods

- `protected virtual DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  
- `protected virtual GetUninitializedObject() : System.Object`  
- `protected virtual SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

