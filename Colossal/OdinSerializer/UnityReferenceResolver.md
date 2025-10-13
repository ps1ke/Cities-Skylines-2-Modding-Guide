# Colossal.OdinSerializer.UnityReferenceResolver

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `System.Object`  
**Implements:** `Colossal.OdinSerializer.IExternalIndexReferenceResolver`, `Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver`  

## Code

```csharp
public sealed class UnityReferenceResolver : Colossal.OdinSerializer.IExternalIndexReferenceResolver, Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver
{
    private System.Collections.Generic.Dictionary<UnityEngine.Object, System.Int32> referenceIndexMapping;
    private System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects;

    public UnityReferenceResolver();
    public UnityReferenceResolver(System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects);

    public System.Boolean CanReference(System.Object value, System.Int32& index);
    private System.Void Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnClaimed();
    private System.Void Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnFreed();
    public System.Collections.Generic.List<UnityEngine.Object> GetReferencedUnityObjects();
    public System.Void Reset();
    public System.Void SetReferencedUnityObjects(System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects);
    public System.Boolean TryResolveReference(System.Int32 index, System.Object& value);
}
```


## Fields

- `private System.Collections.Generic.Dictionary<UnityEngine.Object, System.Int32> referenceIndexMapping`  

```csharp
private System.Collections.Generic.Dictionary<UnityEngine.Object, System.Int32> referenceIndexMapping;
```

- `private System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects`  

```csharp
private System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects;
```


## Constructors

- `public UnityReferenceResolver()`  

```csharp
public UnityReferenceResolver();
```

- `public UnityReferenceResolver(System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects)`  

```csharp
public UnityReferenceResolver(System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects);
```


## Methods

- `public CanReference(System.Object value, System.Int32& index) : System.Boolean`  

```csharp
public System.Boolean CanReference(System.Object value, System.Int32& index);
```

- `private Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnClaimed() : System.Void`  

```csharp
private System.Void Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnClaimed();
```

- `private Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnFreed() : System.Void`  

```csharp
private System.Void Colossal.OdinSerializer.Utilities.ICacheNotificationReceiver.OnFreed();
```

- `public GetReferencedUnityObjects() : System.Collections.Generic.List<UnityEngine.Object>`  

```csharp
public System.Collections.Generic.List<UnityEngine.Object> GetReferencedUnityObjects();
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```

- `public SetReferencedUnityObjects(System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects) : System.Void`  

```csharp
public System.Void SetReferencedUnityObjects(System.Collections.Generic.List<UnityEngine.Object> referencedUnityObjects);
```

- `public TryResolveReference(System.Int32 index, System.Object& value) : System.Boolean`  

```csharp
public System.Boolean TryResolveReference(System.Int32 index, System.Object& value);
```


