# Colossal.OdinSerializer.IExternalGuidReferenceResolver

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** interface abstract public  


## Properties

- `public Colossal.OdinSerializer.IExternalGuidReferenceResolver NextResolver { get; set }`  

## Methods

- `public abstract CanReference(System.Object value, System.Guid& guid) : System.Boolean`  
- `public abstract TryResolveReference(System.Guid guid, System.Object& value) : System.Boolean`  

