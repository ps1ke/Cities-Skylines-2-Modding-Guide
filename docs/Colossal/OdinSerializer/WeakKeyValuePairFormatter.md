# Colossal.OdinSerializer.WeakKeyValuePairFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.WeakBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Fields

- `private readonly Colossal.OdinSerializer.Serializer KeySerializer`  
- `private readonly Colossal.OdinSerializer.Serializer ValueSerializer`  
- `private readonly System.Reflection.PropertyInfo KeyProperty`  
- `private readonly System.Reflection.PropertyInfo ValueProperty`  

## Constructors

- `public WeakKeyValuePairFormatter(System.Type serializedType)`  

## Methods

- `protected virtual DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  
- `protected virtual SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

