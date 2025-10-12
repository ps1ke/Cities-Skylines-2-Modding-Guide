# Colossal.OdinSerializer.WeakBaseFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Fields

- `protected readonly System.Type SerializedType`  
- `protected readonly Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] OnSerializingCallbacks`  
- `protected readonly Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] OnSerializedCallbacks`  
- `protected readonly Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] OnDeserializingCallbacks`  
- `protected readonly Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[] OnDeserializedCallbacks`  
- `protected readonly System.Boolean IsValueType`  
- `protected readonly System.Boolean ImplementsISerializationCallbackReceiver`  
- `protected readonly System.Boolean ImplementsIDeserializationCallback`  
- `protected readonly System.Boolean ImplementsIObjectReference`  

## Properties

- `private System.Type Colossal.OdinSerializer.IFormatter.SerializedType { private get }`  

## Constructors

- `public WeakBaseFormatter(System.Type serializedType)`  

## Methods

- `private static CreateCallback(System.Reflection.MethodInfo info) : Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback`  
- `public Deserialize(Colossal.OdinSerializer.IDataReader reader) : System.Object`  
- `protected abstract DeserializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  
- `private static GetCallbacks(System.Reflection.MethodInfo[] methods, System.Type callbackAttribute, System.Collections.Generic.List`1[[Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback, Colossal.OdinSerializer, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null]]& list) : Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback[]`  
- `protected virtual GetUninitializedObject() : System.Object`  
- `protected InvokeOnDeserializingCallbacks(System.Object value, Colossal.OdinSerializer.DeserializationContext context) : System.Void`  
- `protected RegisterReferenceID(System.Object value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  
- `public Serialize(System.Object value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  
- `protected abstract SerializeImplementation(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

## Nested types

- `Colossal.OdinSerializer.WeakBaseFormatter+SerializationCallback`  
- `Colossal.OdinSerializer.WeakBaseFormatter+<>c__DisplayClass14_0`  

