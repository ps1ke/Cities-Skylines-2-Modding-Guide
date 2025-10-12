# Colossal.OdinSerializer.WeakSerializableFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.WeakBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Fields

- `private readonly System.Func<System.Runtime.Serialization.SerializationInfo, System.Runtime.Serialization.StreamingContext, System.Runtime.Serialization.ISerializable> ISerializableConstructor`  
- `private readonly Colossal.OdinSerializer.WeakReflectionFormatter ReflectionFormatter`  

## Constructors

- `public WeakSerializableFormatter(System.Type serializedType)`  

## Methods

- `protected virtual DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  
- `protected virtual GetUninitializedObject() : System.Object`  
- `private ReadSerializationInfo(Colossal.OdinSerializer.IDataReader reader) : System.Runtime.Serialization.SerializationInfo`  
- `protected virtual SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  
- `private WriteSerializationInfo(System.Runtime.Serialization.SerializationInfo info, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

## Nested types

- `Colossal.OdinSerializer.WeakSerializableFormatter+<>c__DisplayClass2_0`  

