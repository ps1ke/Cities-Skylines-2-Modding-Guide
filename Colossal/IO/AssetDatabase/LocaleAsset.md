# Colossal.IO.AssetDatabase.LocaleAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IDictionarySource`  

## Code

```csharp
public class LocaleAsset : Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile, Colossal.IDictionarySource
{
    private Colossal.IO.AssetDatabase.LocaleData m_Data;
    private UnityEngine.SystemLanguage m_SystemLanguage;
    private System.String <localizedName>k__BackingField;
    public static const System.String kExtension;
    public static const System.UInt16 kFormatVersion;

    public Colossal.IO.AssetDatabase.LocaleData data { get; }
    public Colossal.IO.AssetDatabase.LoadState state { get; }
    public System.String localeId { get; }
    public UnityEngine.SystemLanguage systemLanguage { get; }
    public System.String localizedName { get; private set; }
    public System.Boolean transient { get; }

    public LocaleAsset();

    private System.Void Colossal.IDictionarySource.Unload();
    private System.Void Load();
    public virtual System.Void PostCreate();
    public System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>> ReadEntries(System.Collections.Generic.IList<Colossal.IDictionaryEntryError> errors, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts);
    private System.Void ReadHeader();
    public virtual System.Void Save(System.Boolean force);
    public System.Void SetData(Colossal.IO.AssetDatabase.LocaleData data, UnityEngine.SystemLanguage systemLanguage, System.String localizedName);
    public virtual System.Void Unload(System.Boolean force);
}
```


## Fields

- `private Colossal.IO.AssetDatabase.LocaleData m_Data`  

```csharp
private Colossal.IO.AssetDatabase.LocaleData m_Data;
```

- `private UnityEngine.SystemLanguage m_SystemLanguage`  

```csharp
private UnityEngine.SystemLanguage m_SystemLanguage;
```

- `private System.String <localizedName>k__BackingField`  

```csharp
private System.String <localizedName>k__BackingField;
```

- `public static const System.String kExtension`  

```csharp
public static const System.String kExtension;
```

- `public static const System.UInt16 kFormatVersion`  

```csharp
public static const System.UInt16 kFormatVersion;
```


## Properties

- `public Colossal.IO.AssetDatabase.LocaleData data { get }`  

```csharp
public Colossal.IO.AssetDatabase.LocaleData data { get; }
```

- `public Colossal.IO.AssetDatabase.LoadState state { get }`  

```csharp
public Colossal.IO.AssetDatabase.LoadState state { get; }
```

- `public System.String localeId { get }`  

```csharp
public System.String localeId { get; }
```

- `public UnityEngine.SystemLanguage systemLanguage { get }`  

```csharp
public UnityEngine.SystemLanguage systemLanguage { get; }
```

- `public System.String localizedName { get; private set }`  

```csharp
public System.String localizedName { get; private set; }
```

- `public System.Boolean transient { get }`  

```csharp
public System.Boolean transient { get; }
```


## Constructors

- `public LocaleAsset()`  

```csharp
public LocaleAsset();
```


## Methods

- `private Colossal.IDictionarySource.Unload() : System.Void`  

```csharp
private System.Void Colossal.IDictionarySource.Unload();
```

- `private Load() : System.Void`  

```csharp
private System.Void Load();
```

- `public virtual PostCreate() : System.Void`  

```csharp
public virtual System.Void PostCreate();
```

- `public ReadEntries(System.Collections.Generic.IList<Colossal.IDictionaryEntryError> errors, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts) : System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>>`  

```csharp
public System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.String>> ReadEntries(System.Collections.Generic.IList<Colossal.IDictionaryEntryError> errors, System.Collections.Generic.Dictionary<System.String, System.Int32> indexCounts);
```

- `private ReadHeader() : System.Void`  

```csharp
private System.Void ReadHeader();
```

- `public virtual Save(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Save(System.Boolean force);
```

- `public SetData(Colossal.IO.AssetDatabase.LocaleData data, UnityEngine.SystemLanguage systemLanguage, System.String localizedName) : System.Void`  

```csharp
public System.Void SetData(Colossal.IO.AssetDatabase.LocaleData data, UnityEngine.SystemLanguage systemLanguage, System.String localizedName);
```

- `public virtual Unload(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Unload(System.Boolean force);
```


## Nested types

- `Colossal.IO.AssetDatabase.LocaleAsset+<ReadEntries>d__25`  

