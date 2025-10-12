# Colossal.IO.AssetDatabase.UnityObjectsMap

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `UnityEngine.ScriptableObject`  
**Implements:** `System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, UnityEngine.Object>>`, `System.Collections.IEnumerable`  

**Attributes:** `CreateAssetMenu`  

## Fields

- `public Colossal.IO.AssetDatabase.StringObjectDictionary m_GuidToUnityObjectsMap`  
- `public Colossal.IO.AssetDatabase.ObjectStringDictionary m_UnityObjectsToGuidMap`  

## Properties

- `public System.Int32 Count { get }`  

## Constructors

- `public UnityObjectsMap()`  

## Methods

- `public Clear() : System.Void`  
- `public ContainsObject(UnityEngine.Object obj) : System.Boolean`  
- `public GetEnumerator() : System.Collections.Generic.IEnumerator<System.Collections.Generic.KeyValuePair<System.String, UnityEngine.Object>>`  
- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  
- `public TryGetGuid(UnityEngine.Object obj, System.String& id) : System.Boolean`  
- `public TryGetGuidOrAdd(UnityEngine.Object obj) : System.String`  
- `public TryGetObject(System.String guid, UnityEngine.Object& obj) : System.Boolean`  

