# Colossal.OdinSerializer.UnityReferenceResolver

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.IExternalIndexReferenceResolver`, `Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver`  

## Fields

- `private System.Collections.Generic.Dictionary<UnityEngine.Object, System.Int32> referenceIndexMapping`  
- `private System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects`  

## Constructors

- `public UnityReferenceResolver()`  
- `public UnityReferenceResolver(System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects)`  

## Methods

- `public CanReference(System.Object value, System.Int32& index) : System.Boolean`  
- `private Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnClaimed() : System.Void`  
- `private Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnFreed() : System.Void`  
- `public GetReferencedUnityObjects() : System.Collections.Generic.List<UnityEngine.Object>`  
- `public Reset() : System.Void`  
- `public SetReferencedUnityObjects(System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects) : System.Void`  
- `public TryResolveReference(System.Int32 index, System.Object& value) : System.Boolean`  

