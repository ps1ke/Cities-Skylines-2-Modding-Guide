# Colossal.IO.AssetDatabase.LocaleAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IDictionarySource`  

## Fields

- `private Colossal.IO.AssetDatabase.LocaleData m_Data`  
- `private UnityEngine.SystemLanguage m_SystemLanguage`  
- `private System.String <localizedName>k__BackingField`  
- `public static const System.String kExtension`  
- `public static const System.UInt16 kFormatVersion`  

## Properties

- `public Colossal.IO.AssetDatabase.LocaleData data { get }`  
- `public Colossal.IO.AssetDatabase.LoadState state { get }`  
- `public System.String localeId { get }`  
- `public UnityEngine.SystemLanguage systemLanguage { get }`  
- `public System.String localizedName { get; private set }`  
- `public System.Boolean transient { get }`  

## Constructors

- `public LocaleAsset()`  

## Methods

- `private Colossal.IDictionarySource.Unload() : System.Void`  
- `private Load() : System.Void`  
- `public virtual PostCreate() : System.Void`  
- `public ReadEntries(System.Collections.Generic.IList<Colossal.IDictionaryEntryError> errors, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts) : System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>>`  
- `private ReadHeader() : System.Void`  
- `public virtual Save(System.Boolean force = False) : System.Void`  
- `public SetData(Colossal.IO.AssetDatabase.LocaleData data, UnityEngine.SystemLanguage systemLanguage, System.String localizedName) : System.Void`  
- `public virtual Unload(System.Boolean force = False) : System.Void`  

## Nested types

- `Colossal.IO.AssetDatabase.LocaleAsset+<ReadEntries>d__25`  

