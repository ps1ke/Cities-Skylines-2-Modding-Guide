# Colossal.IO.AssetDatabase.PrefabAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IO.AssetDatabase.IAssetData<UnityEngine.ScriptableObject>`  

## Code

```csharp
public class PrefabAsset : Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile, Colossal.IO.AssetDatabase.IAssetData<UnityEngine.ScriptableObject>
{
    private Colossal.IO.AssetDatabase.ContentType m_CachedContentType;
    private UnityEngine.ScriptableObject m_Instance;
    private System.Boolean m_Initialized;
    private System.String m_SubPath;
    private static Colossal.OdinSerializer.SerializationConfig kDefaultSerializationConfig;
    public static const System.String kExtension;
    public static const Colossal.IO.AssetDatabase.ContentType kDefaultFormat;
    public static const System.UInt16 kFormatVersion;

    public Colossal.IO.AssetDatabase.LoadState state { get; }
    public System.String subPath { get; }

    public PrefabAsset();

    private System.Void <Load>b__20_0(System.TimeSpan t);
    public T Load<T>();
    public UnityEngine.ScriptableObject Load();
    private UnityEngine.ScriptableObject Load(System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.PrefabAsset> dependencies);
    private UnityEngine.ScriptableObject LoadUninitialized();
    private Colossal.IO.AssetDatabase.ContentType PeekFormat();
    private Colossal.IO.AssetDatabase.ContentType PeekFormat(System.IO.Stream stream);
    public virtual System.Void PostCreate();
    public virtual System.Void Save(System.Boolean force);
    public System.Void Save(Colossal.IO.AssetDatabase.ContentType contentType, System.Boolean force);
    public System.Void Save(Colossal.IO.AssetDatabase.ContentType contentType, System.Boolean includeUnityDependencies, System.Boolean force);
    public System.Void Save(Colossal.IO.AssetDatabase.ContentType contentType, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.PrefabAsset> dependencies, System.Boolean includeUnityDependencies, System.Boolean force);
    public System.Void SetData(UnityEngine.ScriptableObject scriptableObject);
    private System.Void SetUninitializedInstance(UnityEngine.ScriptableObject instance);
    public virtual System.Void Unload(System.Boolean force);
}
```


## Fields

- `private Colossal.IO.AssetDatabase.ContentType m_CachedContentType`  

```csharp
private Colossal.IO.AssetDatabase.ContentType m_CachedContentType;
```

- `private UnityEngine.ScriptableObject m_Instance`  

```csharp
private UnityEngine.ScriptableObject m_Instance;
```

- `private System.Boolean m_Initialized`  

```csharp
private System.Boolean m_Initialized;
```

- `private System.String m_SubPath`  

```csharp
private System.String m_SubPath;
```

- `private static Colossal.OdinSerializer.SerializationConfig kDefaultSerializationConfig`  

```csharp
private static Colossal.OdinSerializer.SerializationConfig kDefaultSerializationConfig;
```

- `public static const System.String kExtension`  

```csharp
public static const System.String kExtension;
```

- `public static const Colossal.IO.AssetDatabase.ContentType kDefaultFormat`  

```csharp
public static const Colossal.IO.AssetDatabase.ContentType kDefaultFormat;
```

- `public static const System.UInt16 kFormatVersion`  

```csharp
public static const System.UInt16 kFormatVersion;
```


## Properties

- `public Colossal.IO.AssetDatabase.LoadState state { get }`  

```csharp
public Colossal.IO.AssetDatabase.LoadState state { get; }
```

- `public System.String subPath { get }`  

```csharp
public System.String subPath { get; }
```


## Constructors

- `public PrefabAsset()`  

```csharp
public PrefabAsset();
```


## Methods

- `private <Load>b__20_0(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <Load>b__20_0(System.TimeSpan t);
```

- `public Load<T>() : T`  

```csharp
public T Load<T>();
```

- `public Load() : UnityEngine.ScriptableObject`  

```csharp
public UnityEngine.ScriptableObject Load();
```

- `private Load(System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.PrefabAsset> dependencies) : UnityEngine.ScriptableObject`  

```csharp
private UnityEngine.ScriptableObject Load(System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.PrefabAsset> dependencies);
```

- `private LoadUninitialized() : UnityEngine.ScriptableObject`  

```csharp
private UnityEngine.ScriptableObject LoadUninitialized();
```

- `private PeekFormat() : Colossal.IO.AssetDatabase.ContentType`  

```csharp
private Colossal.IO.AssetDatabase.ContentType PeekFormat();
```

- `private PeekFormat(System.IO.Stream stream) : Colossal.IO.AssetDatabase.ContentType`  

```csharp
private Colossal.IO.AssetDatabase.ContentType PeekFormat(System.IO.Stream stream);
```

- `public virtual PostCreate() : System.Void`  

```csharp
public virtual System.Void PostCreate();
```

- `public virtual Save(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Save(System.Boolean force);
```

- `public Save(Colossal.IO.AssetDatabase.ContentType contentType, System.Boolean force = False) : System.Void`  

```csharp
public System.Void Save(Colossal.IO.AssetDatabase.ContentType contentType, System.Boolean force);
```

- `public Save(Colossal.IO.AssetDatabase.ContentType contentType, System.Boolean includeUnityDependencies, System.Boolean force) : System.Void`  

```csharp
public System.Void Save(Colossal.IO.AssetDatabase.ContentType contentType, System.Boolean includeUnityDependencies, System.Boolean force);
```

- `public Save(Colossal.IO.AssetDatabase.ContentType contentType, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.PrefabAsset> dependencies, System.Boolean includeUnityDependencies, System.Boolean force = False) : System.Void`  

```csharp
public System.Void Save(Colossal.IO.AssetDatabase.ContentType contentType, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.PrefabAsset> dependencies, System.Boolean includeUnityDependencies, System.Boolean force);
```

- `public SetData(UnityEngine.ScriptableObject scriptableObject) : System.Void`  

```csharp
public System.Void SetData(UnityEngine.ScriptableObject scriptableObject);
```

- `private SetUninitializedInstance(UnityEngine.ScriptableObject instance) : System.Void`  

```csharp
private System.Void SetUninitializedInstance(UnityEngine.ScriptableObject instance);
```

- `public virtual Unload(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Unload(System.Boolean force);
```


## Nested types

- `Colossal.IO.AssetDatabase.PrefabAsset+OdinLogger`  
- `Colossal.IO.AssetDatabase.PrefabAsset+EncodingHelper`  
- `Colossal.IO.AssetDatabase.PrefabAsset+PrefabReferenceResolver`  
- `Colossal.IO.AssetDatabase.PrefabAsset+PrefabFormatter<T>`  

