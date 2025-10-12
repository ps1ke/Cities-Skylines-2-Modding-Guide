# Colossal.UI.Binding.IJsonReader

**Assembly:** `Colossal.UI.Binding`  
**Namespace:** `Colossal.UI.Binding`  

**Type:** interface abstract public  


## Properties

- `public System.String debugName { get }`  

## Methods

- `public abstract GetArgumentsCount() : System.Int32`  
- `public abstract PeekValueType() : cohtml.Net.ValueType`  
- `public abstract Read(System.Boolean& value) : System.Void`  
- `public abstract Read(System.UInt32& value) : System.Void`  
- `public abstract Read(System.Int32& value) : System.Void`  
- `public abstract Read(System.Single& value) : System.Void`  
- `public abstract Read(System.Double& value) : System.Void`  
- `public abstract Read(System.String& value) : System.Void`  
- `public abstract ReadArrayBegin() : System.UInt64`  
- `public abstract ReadArrayElement(System.UInt64 index) : System.Void`  
- `public abstract ReadArrayEnd() : System.Void`  
- `public abstract ReadMapBegin() : System.UInt64`  
- `public abstract ReadMapEnd() : System.Void`  
- `public abstract ReadMapKeyValue() : System.Void`  
- `public abstract ReadProperty(System.String name) : System.Boolean`  
- `public abstract SkipValue() : System.Void`  

