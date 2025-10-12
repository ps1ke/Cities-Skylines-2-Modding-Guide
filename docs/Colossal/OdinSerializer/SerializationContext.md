# Colossal.OdinSerializer.SerializationContext

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver`  

## Fields

- `private Colossal.OdinSerializer.SerializationConfig config`  
- `private System.Collections.Generic.Dictionary<System.Object, System.Int32> internalReferenceIdMap`  
- `private System.Runtime.Serialization.StreamingContext streamingContext`  
- `private System.Runtime.Serialization.IFormatterConverter formatterConverter`  
- `private Colossal.OdinSerializer.TwoWaySerializationBinder binder`  
- `private Colossal.OdinSerializer.IExternalIndexReferenceResolver <IndexReferenceResolver>k__BackingField`  
- `private Colossal.OdinSerializer.IExternalStringReferenceResolver <StringReferenceResolver>k__BackingField`  
- `private Colossal.OdinSerializer.IExternalGuidReferenceResolver <GuidReferenceResolver>k__BackingField`  

## Properties

- `public Colossal.OdinSerializer.TwoWaySerializationBinder Binder { get; set }`  
- `public System.Runtime.Serialization.StreamingContext StreamingContext { get }`  
- `public System.Runtime.Serialization.IFormatterConverter FormatterConverter { get }`  
- `public Colossal.OdinSerializer.IExternalIndexReferenceResolver IndexReferenceResolver { get; set }`  
- `public Colossal.OdinSerializer.IExternalStringReferenceResolver StringReferenceResolver { get; set }`  
- `public Colossal.OdinSerializer.IExternalGuidReferenceResolver GuidReferenceResolver { get; set }`  
- `public Colossal.OdinSerializer.SerializationConfig Config { get; set }`  

## Constructors

- `public SerializationContext()`  
- `public SerializationContext(System.Runtime.Serialization.StreamingContext context)`  
- `public SerializationContext(System.Runtime.Serialization.FormatterConverter formatterConverter)`  
- `public SerializationContext(System.Runtime.Serialization.StreamingContext context, System.Runtime.Serialization.FormatterConverter formatterConverter)`  

## Methods

- `private Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnClaimed() : System.Void`  
- `private Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnFreed() : System.Void`  
- `public ResetInternalReferences() : System.Void`  
- `public ResetToDefault() : System.Void`  
- `public TryGetInternalReferenceId(System.Object reference, System.Int32& id) : System.Boolean`  
- `public TryRegisterExternalReference(System.Object obj, System.Int32& index) : System.Boolean`  
- `public TryRegisterExternalReference(System.Object obj, System.Guid& guid) : System.Boolean`  
- `public TryRegisterExternalReference(System.Object obj, System.String& id) : System.Boolean`  
- `public TryRegisterInternalReference(System.Object reference, System.Int32& id) : System.Boolean`  

