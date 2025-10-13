# Colossal.OdinSerializer.PrefabModification

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Code

```csharp
public sealed class PrefabModification
{
    public Colossal.OdinSerializer.PrefabModificationType ModificationType;
    public System.String Path;
    public System.Collections.Generic.List<System.String> ReferencePaths;
    public System.Object ModifiedValue;
    public System.Int32 NewLength;
    public System.Object[] DictionaryKeysAdded;
    public System.Object[] DictionaryKeysRemoved;

    public PrefabModification();

    public System.Void Apply(UnityEngine.Object unityObject);
    private System.Void ApplyDictionaryModifications(UnityEngine.Object unityObject);
    private System.Void ApplyListLength(UnityEngine.Object unityObject);
    private System.Void ApplyValue(UnityEngine.Object unityObject);
    private static System.Object GetInstanceFromPath(System.String path, System.Object instance);
    private static System.Object GetInstanceOfStep(System.String step, System.Object instance);
    private static System.Void ReplaceAllReferencesInGraph(System.Object graph, System.Object oldReference, System.Object newReference, System.Collections.Generic.HashSet<System.Object> processedReferences);
    private static System.Void SetInstanceToPath(System.String path, System.Object instance, System.Object value);
    private static System.Void SetInstanceToPath(System.String path, System.String[] steps, System.Int32 index, System.Object instance, System.Object value, System.Boolean& setParentInstance);
    private static System.Boolean TrySetInstanceOfStep(System.String step, System.Object instance, System.Object value, System.Boolean& setParentInstance);
}
```


## Fields

- `public Colossal.OdinSerializer.PrefabModificationType ModificationType`  

```csharp
public Colossal.OdinSerializer.PrefabModificationType ModificationType;
```

- `public System.String Path`  

```csharp
public System.String Path;
```

- `public System.Collections.Generic.List<System.String> ReferencePaths`  

```csharp
public System.Collections.Generic.List<System.String> ReferencePaths;
```

- `public System.Object ModifiedValue`  

```csharp
public System.Object ModifiedValue;
```

- `public System.Int32 NewLength`  

```csharp
public System.Int32 NewLength;
```

- `public System.Object[] DictionaryKeysAdded`  

```csharp
public System.Object[] DictionaryKeysAdded;
```

- `public System.Object[] DictionaryKeysRemoved`  

```csharp
public System.Object[] DictionaryKeysRemoved;
```


## Constructors

- `public PrefabModification()`  

```csharp
public PrefabModification();
```


## Methods

- `public Apply(UnityEngine.Object unityObject) : System.Void`  

```csharp
public System.Void Apply(UnityEngine.Object unityObject);
```

- `private ApplyDictionaryModifications(UnityEngine.Object unityObject) : System.Void`  

```csharp
private System.Void ApplyDictionaryModifications(UnityEngine.Object unityObject);
```

- `private ApplyListLength(UnityEngine.Object unityObject) : System.Void`  

```csharp
private System.Void ApplyListLength(UnityEngine.Object unityObject);
```

- `private ApplyValue(UnityEngine.Object unityObject) : System.Void`  

```csharp
private System.Void ApplyValue(UnityEngine.Object unityObject);
```

- `private static GetInstanceFromPath(System.String path, System.Object instance) : System.Object`  

```csharp
private static System.Object GetInstanceFromPath(System.String path, System.Object instance);
```

- `private static GetInstanceOfStep(System.String step, System.Object instance) : System.Object`  

```csharp
private static System.Object GetInstanceOfStep(System.String step, System.Object instance);
```

- `private static ReplaceAllReferencesInGraph(System.Object graph, System.Object oldReference, System.Object newReference, System.Collections.Generic.HashSet<System.Object> processedReferences = null) : System.Void`  

```csharp
private static System.Void ReplaceAllReferencesInGraph(System.Object graph, System.Object oldReference, System.Object newReference, System.Collections.Generic.HashSet<System.Object> processedReferences);
```

- `private static SetInstanceToPath(System.String path, System.Object instance, System.Object value) : System.Void`  

```csharp
private static System.Void SetInstanceToPath(System.String path, System.Object instance, System.Object value);
```

- `private static SetInstanceToPath(System.String path, System.String[] steps, System.Int32 index, System.Object instance, System.Object value, System.Boolean& setParentInstance) : System.Void`  

```csharp
private static System.Void SetInstanceToPath(System.String path, System.String[] steps, System.Int32 index, System.Object instance, System.Object value, System.Boolean& setParentInstance);
```

- `private static TrySetInstanceOfStep(System.String step, System.Object instance, System.Object value, System.Boolean& setParentInstance) : System.Boolean`  

```csharp
private static System.Boolean TrySetInstanceOfStep(System.String step, System.Object instance, System.Object value, System.Boolean& setParentInstance);
```


## Nested types

- `Colossal.OdinSerializer.PrefabModification+<>c`  

