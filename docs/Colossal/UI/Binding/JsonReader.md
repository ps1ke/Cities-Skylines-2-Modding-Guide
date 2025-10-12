# Colossal.UI.Binding.JsonReader

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonReader`  

## Fields

- `private System.IntPtr <binder>k__BackingField`  
- `private readonly System.String <debugName>k__BackingField`  

## Properties

- `public System.IntPtr binder { get; set }`  
- `public System.String debugName { get }`  

## Constructors

- `protected JsonReader()`  
- `public JsonReader(System.String debugName)`  

## Methods

- `public GetArgumentsCount() : System.Int32`  
- `public PeekValueType() : cohtml.Net.ValueType`  
- `public Read(System.Boolean& value) : System.Void`  
- `public Read(System.UInt32& value) : System.Void`  
- `public Read(System.Int32& value) : System.Void`  
- `public Read(System.Single& value) : System.Void`  
- `public Read(System.Double& value) : System.Void`  
- `public Read(System.String& value) : System.Void`  
- `public ReadArrayBegin() : System.UInt64`  
- `public ReadArrayElement(System.UInt64 index) : System.Void`  
- `public ReadArrayEnd() : System.Void`  
- `public ReadMapBegin() : System.UInt64`  
- `public ReadMapEnd() : System.Void`  
- `public ReadMapKeyValue() : System.Void`  
- `public ReadProperty(System.String name) : System.Boolean`  
- `public SkipValue() : System.Void`  

