# Colossal.UI.Binding.JsonWriter

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.UI.Binding.IJsonWriter`  

## Fields

- `private System.IntPtr <binder>k__BackingField`  
- `private readonly System.String <debugName>k__BackingField`  

## Properties

- `public System.IntPtr binder { get; set }`  
- `public System.String debugName { get }`  

## Constructors

- `protected JsonWriter()`  
- `public JsonWriter(System.String debugName)`  

## Methods

- `public ArrayBegin(System.UInt32 size) : System.Void`  
- `public ArrayEnd() : System.Void`  
- `public BeginEvent(System.String name, System.Int32 arguments) : System.Void`  
- `public EndEvent() : System.Void`  
- `public MapBegin(System.UInt32 size) : System.Void`  
- `public MapEnd() : System.Void`  
- `public PropertyName(System.String name) : System.Void`  
- `public TypeBegin(System.String name) : System.Void`  
- `public TypeEnd() : System.Void`  
- `public Write(System.Boolean value) : System.Void`  
- `public Write(System.Int32 value) : System.Void`  
- `public Write(System.UInt32 value) : System.Void`  
- `public Write(System.Single value) : System.Void`  
- `public Write(System.Double value) : System.Void`  
- `public Write(System.String value) : System.Void`  
- `public WriteNull() : System.Void`  

