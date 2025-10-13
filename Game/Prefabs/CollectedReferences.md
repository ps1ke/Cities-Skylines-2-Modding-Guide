# Game.Prefabs.ReferenceCollector+CollectedReferences

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class CollectedReferences
{
    private readonly System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase> m_PrefabReferences;
    private readonly System.Collections.Generic.HashSet<UnityEngine.ScriptableObject> m_ScriptableObjectReferences;
    private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetReference> m_AssetReferences;
    private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetData> m_AssetDatas;

    public System.Collections.Generic.IReadOnlyCollection<Game.Prefabs.PrefabBase> prefabReferences { get; }
    public System.Collections.Generic.IReadOnlyCollection<UnityEngine.ScriptableObject> scriptableObjectReferences { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.IO.AssetDatabase.AssetReference> assetReferences { get; }
    public System.Collections.Generic.IReadOnlyCollection<Colossal.IO.AssetDatabase.AssetData> assetDatas { get; }

    public CollectedReferences();

    public System.Void Add(System.Object obj);
}
```


## Fields

- `private readonly System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase> m_PrefabReferences`  

```csharp
private readonly System.Collections.Generic.HashSet<Game.Prefabs.PrefabBase> m_PrefabReferences;
```

- `private readonly System.Collections.Generic.HashSet<UnityEngine.ScriptableObject> m_ScriptableObjectReferences`  

```csharp
private readonly System.Collections.Generic.HashSet<UnityEngine.ScriptableObject> m_ScriptableObjectReferences;
```

- `private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetReference> m_AssetReferences`  

```csharp
private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetReference> m_AssetReferences;
```

- `private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetData> m_AssetDatas`  

```csharp
private readonly System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.AssetData> m_AssetDatas;
```


## Properties

- `public System.Collections.Generic.IReadOnlyCollection<Game.Prefabs.PrefabBase> prefabReferences { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Game.Prefabs.PrefabBase> prefabReferences { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<UnityEngine.ScriptableObject> scriptableObjectReferences { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<UnityEngine.ScriptableObject> scriptableObjectReferences { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.IO.AssetDatabase.AssetReference> assetReferences { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.IO.AssetDatabase.AssetReference> assetReferences { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<Colossal.IO.AssetDatabase.AssetData> assetDatas { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<Colossal.IO.AssetDatabase.AssetData> assetDatas { get; }
```


## Constructors

- `public CollectedReferences()`  

```csharp
public CollectedReferences();
```


## Methods

- `public Add(System.Object obj) : System.Void`  

```csharp
public System.Void Add(System.Object obj);
```


