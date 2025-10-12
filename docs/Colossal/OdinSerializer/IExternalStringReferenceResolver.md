# Colossal.OdinSerializer.IExternalStringReferenceResolver

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** interface abstract public  


## Properties

- `public Colossal.OdinSerializer.IExternalStringReferenceResolver NextResolver { get; set }`  

## Methods

- `public abstract CanReference(System.Object value, System.String& id) : System.Boolean`  
- `public abstract TryResolveReference(System.Type serializedType, System.String id, System.Object& value) : System.Boolean`  

