# Colossal.OdinSerializer.DeserializationContext

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver`  

## Fields

- `private Colossal.OdinSerializer.SerializationConfig config`  
- `private System.Collections.Generic.Dictionary<System.Int32, System.Object> internalIdReferenceMap`  
- `private System.Runtime.Serialization.StreamingContext streamingContext`  
- `private System.Runtime.Serialization.IFormatterConverter formatterConverter`  
- `private Colossal.OdinSerializer.TwoWaySerializationBinder binder`  
- `private Colossal.OdinSerializer.IExternalStringReferenceResolver <StringReferenceResolver>k__BackingField`  
- `private Colossal.OdinSerializer.IExternalGuidReferenceResolver <GuidReferenceResolver>k__BackingField`  
- `private Colossal.OdinSerializer.IExternalIndexReferenceResolver <IndexReferenceResolver>k__BackingField`  

## Properties

- `public Colossal.OdinSerializer.TwoWaySerializationBinder Binder { get; set }`  
- `public Colossal.OdinSerializer.IExternalStringReferenceResolver StringReferenceResolver { get; set }`  
- `public Colossal.OdinSerializer.IExternalGuidReferenceResolver GuidReferenceResolver { get; set }`  
- `public Colossal.OdinSerializer.IExternalIndexReferenceResolver IndexReferenceResolver { get; set }`  
- `public System.Runtime.Serialization.StreamingContext StreamingContext { get }`  
- `public System.Runtime.Serialization.IFormatterConverter FormatterConverter { get }`  
- `public Colossal.OdinSerializer.SerializationConfig Config { get; set }`  

## Constructors

- `public DeserializationContext()`  
- `public DeserializationContext(System.Runtime.Serialization.StreamingContext context)`  
- `public DeserializationContext(System.Runtime.Serialization.FormatterConverter formatterConverter)`  
- `public DeserializationContext(System.Runtime.Serialization.StreamingContext context, System.Runtime.Serialization.FormatterConverter formatterConverter)`  

## Methods

- `private Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnClaimed() : System.Void`  
- `private Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnFreed() : System.Void`  
- `public GetExternalObject(System.Int32 index) : System.Object`  
- `public GetExternalObject(System.Guid guid) : System.Object`  
- `public GetExternalObject(System.String id, System.Type serializedType = null) : System.Object`  
- `public GetInternalReference(System.Int32 id) : System.Object`  
- `public RegisterInternalReference(System.Int32 id, System.Object reference) : System.Void`  
- `public Reset() : System.Void`  

