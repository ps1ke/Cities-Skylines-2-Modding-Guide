# Colossal.OdinSerializer.PrefabModification

**Assembly:** `Colossal.OdinSerializer`  
**Namespace:** `Colossal.OdinSerializer`  

**Type:** class sealed public  

**Base:** `System.Object`  

## Fields

- `public Colossal.OdinSerializer.PrefabModificationType ModificationType`  
- `public System.String Path`  
- `public System.Collections.Generic.List<System.String> ReferencePaths`  
- `public System.Object ModifiedValue`  
- `public System.Int32 NewLength`  
- `public System.Object[] DictionaryKeysAdded`  
- `public System.Object[] DictionaryKeysRemoved`  

## Constructors

- `public PrefabModification()`  

## Methods

- `public Apply(UnityEngine.Object unityObject) : System.Void`  
- `private ApplyDictionaryModifications(UnityEngine.Object unityObject) : System.Void`  
- `private ApplyListLength(UnityEngine.Object unityObject) : System.Void`  
- `private ApplyValue(UnityEngine.Object unityObject) : System.Void`  
- `private static GetInstanceFromPath(System.String path, System.Object instance) : System.Object`  
- `private static GetInstanceOfStep(System.String step, System.Object instance) : System.Object`  
- `private static ReplaceAllReferencesInGraph(System.Object graph, System.Object oldReference, System.Object newReference, System.Collections.Generic.HashSet<System.Object> processedReferences = null) : System.Void`  
- `private static SetInstanceToPath(System.String path, System.Object instance, System.Object value) : System.Void`  
- `private static SetInstanceToPath(System.String path, System.String[] steps, System.Int32 index, System.Object instance, System.Object value, System.Boolean& setParentInstance) : System.Void`  
- `private static TrySetInstanceOfStep(System.String step, System.Object instance, System.Object value, System.Boolean& setParentInstance) : System.Boolean`  

## Nested types

- `Colossal.OdinSerializer.PrefabModification+<>c`  

