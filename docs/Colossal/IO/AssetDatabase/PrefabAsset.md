# Colossal.IO.AssetDatabase.PrefabAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IO.AssetDatabase.IAssetData<UnityEngine.ScriptableObject>`  

## Fields

- `private Colossal.IO.AssetDatabase.ContentType m_CachedContentType`  
- `private UnityEngine.ScriptableObject m_Instance`  
- `private System.Boolean m_Initialized`  
- `private System.String m_SubPath`  
- `private static Colossal.OdinSerializer.SerializationConfig kDefaultSerializationConfig`  
- `public static const System.String kExtension`  
- `public static const Colossal.IO.AssetDatabase.ContentType kDefaultFormat`  
- `public static const System.UInt16 kFormatVersion`  

## Properties

- `public Colossal.IO.AssetDatabase.LoadState state { get }`  
- `public System.String subPath { get }`  

## Constructors

- `public PrefabAsset()`  

## Methods

- `private <Load>b__20_0(System.TimeSpan t) : System.Void`  
- `public Load<T>() : T`  
- `public Load() : UnityEngine.ScriptableObject`  
- `private Load(System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.PrefabAsset> dependencies) : UnityEngine.ScriptableObject`  
- `private LoadUninitialized() : UnityEngine.ScriptableObject`  
- `private PeekFormat() : Colossal.IO.AssetDatabase.ContentType`  
- `private PeekFormat(System.IO.Stream stream) : Colossal.IO.AssetDatabase.ContentType`  
- `public virtual PostCreate() : System.Void`  
- `public virtual Save(System.Boolean force = False) : System.Void`  
- `public Save(Colossal.IO.AssetDatabase.ContentType contentType, System.Boolean force = False) : System.Void`  
- `public Save(Colossal.IO.AssetDatabase.ContentType contentType, System.Boolean includeUnityDependencies, System.Boolean force) : System.Void`  
- `public Save(Colossal.IO.AssetDatabase.ContentType contentType, System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.PrefabAsset> dependencies, System.Boolean includeUnityDependencies, System.Boolean force = False) : System.Void`  
- `public SetData(UnityEngine.ScriptableObject scriptableObject) : System.Void`  
- `private SetUninitializedInstance(UnityEngine.ScriptableObject instance) : System.Void`  
- `public virtual Unload(System.Boolean force = False) : System.Void`  

## Nested types

- `Colossal.IO.AssetDatabase.PrefabAsset+OdinLogger`  
- `Colossal.IO.AssetDatabase.PrefabAsset+EncodingHelper`  
- `Colossal.IO.AssetDatabase.PrefabAsset+PrefabReferenceResolver`  
- `Colossal.IO.AssetDatabase.PrefabAsset+PrefabFormatter<T>`  

