# Colossal.OdinSerializer.WeakPrimitiveArrayFormatter

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `Colossal.OdinSerializer.WeakMinimalBaseFormatter`  
**Implements:** `Colossal.OdinSerializer.IFormatter`  

## Fields

- `private readonly System.Type ElementType`  
- `private readonly Colossal.OdinSerializer.WeakPrimitiveArrayFormatter+PrimitiveArrayType PrimitiveType`  
- `private static readonly System.Collections.Generic.Dictionary<System.Type, Colossal.OdinSerializer.WeakPrimitiveArrayFormatter+PrimitiveArrayType> PrimitiveTypes`  

## Constructors

- `public WeakPrimitiveArrayFormatter(System.Type arrayType, System.Type elementType)`  

## Methods

- `protected virtual GetUninitializedObject() : System.Object`  
- `protected virtual Read(System.Object& value, Colossal.OdinSerializer.IDataReader reader) : System.Void`  
- `protected virtual Write(System.Object& value, Colossal.OdinSerializer.IDataWriter writer) : System.Void`  

## Nested types

- `Colossal.OdinSerializer.WeakPrimitiveArrayFormatter+PrimitiveArrayType`  

