# Colossal.OdinSerializer.CustomSerializationPolicy

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.ISerializationPolicy`  

## Fields

- `private System.String id`  
- `private System.Boolean allowNonSerializableTypes`  
- `private System.Func<System.Reflection.MemberInfo, System.Boolean> shouldSerializeFunc`  

## Properties

- `public System.String ID { get }`  
- `public System.Boolean AllowNonSerializableTypes { get }`  

## Constructors

- `public CustomSerializationPolicy(System.String id, System.Boolean allowNonSerializableTypes, System.Func<System.Reflection.MemberInfo, System.Boolean> shouldSerializeFunc)`  

## Methods

- `public ShouldSerializeMember(System.Reflection.MemberInfo member) : System.Boolean`  

