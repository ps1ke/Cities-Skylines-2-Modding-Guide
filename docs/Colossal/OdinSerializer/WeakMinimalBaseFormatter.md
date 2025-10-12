# Colossal.OdinSerializer.WeakMinimalBaseFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Fields

- `protected readonly System.Type SerializedType`  
- `protected readonly System.Boolean IsValueType`  

## Properties

- `private System.Type Colossal.OdinSerializer.IFormatter.SerializedType { private get }`  

## Constructors

- `public WeakMinimalBaseFormatter(System.Type serializedType)`  

## Methods

- `public Deserialize(Colossal.OdinSerializer.IDataReader reader) : System.Object`  
- `protected virtual GetUninitializedObject() : System.Object`  
- `protected abstract Read(System.Object& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  
- `protected RegisterReferenceID(System.Object value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  
- `public Serialize(System.Object value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  
- `protected abstract Write(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

