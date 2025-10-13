# Colossal.IO.AssetDatabase.UnityObjectsMap

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `UnityEngine.ScriptableObject`  
**Implements:** `System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, UnityEngine.Object>>`, `System.Collections.IEnumerable`  

**Attributes:** `CreateAssetMenu`  

## Code

```csharp
public class UnityObjectsMap : UnityEngine.ScriptableObject, System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, UnityEngine.Object>>, System.Collections.IEnumerable
{
    public Colossal.IO.AssetDatabase.StringObjectDictionary m_GuidToUnityObjectsMap;
    public Colossal.IO.AssetDatabase.ObjectStringDictionary m_UnityObjectsToGuidMap;

    public System.Int32 Count { get; }

    public UnityObjectsMap();

    public System.Void Clear();
    public System.Boolean ContainsObject(UnityEngine.Object obj);
    public System.Collections.Generic.IEnumerator<System.Collections.Generic.KeyValuePair<System.String, UnityEngine.Object>> GetEnumerator();
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
    public System.Boolean TryGetGuid(UnityEngine.Object obj, System.String& id);
    public System.String TryGetGuidOrAdd(UnityEngine.Object obj);
    public System.Boolean TryGetObject(System.String guid, UnityEngine.Object& obj);
}
```


## Fields

- `public Colossal.IO.AssetDatabase.StringObjectDictionary m_GuidToUnityObjectsMap`  

```csharp
public Colossal.IO.AssetDatabase.StringObjectDictionary m_GuidToUnityObjectsMap;
```

- `public Colossal.IO.AssetDatabase.ObjectStringDictionary m_UnityObjectsToGuidMap`  

```csharp
public Colossal.IO.AssetDatabase.ObjectStringDictionary m_UnityObjectsToGuidMap;
```


## Properties

- `public System.Int32 Count { get }`  

```csharp
public System.Int32 Count { get; }
```


## Constructors

- `public UnityObjectsMap()`  

```csharp
public UnityObjectsMap();
```


## Methods

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `public ContainsObject(UnityEngine.Object obj) : System.Boolean`  

```csharp
public System.Boolean ContainsObject(UnityEngine.Object obj);
```

- `public GetEnumerator() : System.Collections.Generic.IEnumerator<System.Collections.Generic.KeyValuePair<System.String, UnityEngine.Object>>`  

```csharp
public System.Collections.Generic.IEnumerator<System.Collections.Generic.KeyValuePair<System.String, UnityEngine.Object>> GetEnumerator();
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
```

- `public TryGetGuid(UnityEngine.Object obj, System.String& id) : System.Boolean`  

```csharp
public System.Boolean TryGetGuid(UnityEngine.Object obj, System.String& id);
```

- `public TryGetGuidOrAdd(UnityEngine.Object obj) : System.String`  

```csharp
public System.String TryGetGuidOrAdd(UnityEngine.Object obj);
```

- `public TryGetObject(System.String guid, UnityEngine.Object& obj) : System.Boolean`  

```csharp
public System.Boolean TryGetObject(System.String guid, UnityEngine.Object& obj);
```


