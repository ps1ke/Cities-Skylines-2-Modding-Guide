# Colossal.IO.AssetDatabase.SettingAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SettingAsset+Fragment>`, `System.Collections.IEnumerable`  

## Code

```csharp
public class SettingAsset : Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.SettingAsset+Fragment>, System.Collections.IEnumerable
{
    private readonly System.String <name>k__BackingField;
    private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.SettingAsset+Fragment> m_SettingFragments;
    public static const System.String kExtension;
    public static const System.String kExtensionBackup;

    public System.String name { get; }

    public SettingAsset(System.String name);

    private System.Void <Save>b__20_0(System.TimeSpan t);
    public System.Void AddFragment(Colossal.Hash128 guid, System.String fragmentStr);
    public System.Void AddFragment(Colossal.IO.AssetDatabase.SettingAsset+Fragment fragment);
    public virtual System.Boolean Equals(System.Object obj);
    public System.Boolean Equals(Colossal.IO.AssetDatabase.SettingAsset other);
    public System.Collections.Generic.IEnumerator<Colossal.IO.AssetDatabase.SettingAsset+Fragment> GetEnumerator();
    public virtual System.Int32 GetHashCode();
    private System.Boolean IsEmptyJSON(System.String jsonString);
    public virtual System.Void Save(System.Boolean force);
    internal System.Threading.Tasks.Task Save(System.Boolean saveAll, System.Boolean cleanupSettings, Colossal.IO.AssetDatabase.Internal.SaveSettingsHelper helper);
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
    private System.String TrimJSON(System.String input);
}
```


## Fields

- `private readonly System.String <name>k__BackingField`  

```csharp
private readonly System.String <name>k__BackingField;
```

- `private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.SettingAsset+Fragment> m_SettingFragments`  

```csharp
private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.SettingAsset+Fragment> m_SettingFragments;
```

- `public static const System.String kExtension`  

```csharp
public static const System.String kExtension;
```

- `public static const System.String kExtensionBackup`  

```csharp
public static const System.String kExtensionBackup;
```


## Properties

- `public System.String name { get }`  

```csharp
public System.String name { get; }
```


## Constructors

- `public SettingAsset(System.String name)`  

```csharp
public SettingAsset(System.String name);
```


## Methods

- `private <Save>b__20_0(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <Save>b__20_0(System.TimeSpan t);
```

- `public AddFragment(Colossal.Hash128 guid, System.String fragmentStr) : System.Void`  

```csharp
public System.Void AddFragment(Colossal.Hash128 guid, System.String fragmentStr);
```

- `public AddFragment(Colossal.IO.AssetDatabase.SettingAsset+Fragment fragment) : System.Void`  

```csharp
public System.Void AddFragment(Colossal.IO.AssetDatabase.SettingAsset+Fragment fragment);
```

- `public virtual Equals(System.Object obj) : System.Boolean`  

```csharp
public virtual System.Boolean Equals(System.Object obj);
```

- `public Equals(Colossal.IO.AssetDatabase.SettingAsset other) : System.Boolean`  

```csharp
public System.Boolean Equals(Colossal.IO.AssetDatabase.SettingAsset other);
```

- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Colossal.IO.AssetDatabase.SettingAsset+Fragment>`  

```csharp
public System.Collections.Generic.IEnumerator<Colossal.IO.AssetDatabase.SettingAsset+Fragment> GetEnumerator();
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `private IsEmptyJSON(System.String jsonString) : System.Boolean`  

```csharp
private System.Boolean IsEmptyJSON(System.String jsonString);
```

- `public virtual Save(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Save(System.Boolean force);
```

- `internal Save(System.Boolean saveAll, System.Boolean cleanupSettings, Colossal.IO.AssetDatabase.Internal.SaveSettingsHelper helper) : System.Threading.Tasks.Task`  

```csharp
internal System.Threading.Tasks.Task Save(System.Boolean saveAll, System.Boolean cleanupSettings, Colossal.IO.AssetDatabase.Internal.SaveSettingsHelper helper);
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
```

- `private TrimJSON(System.String input) : System.String`  

```csharp
private System.String TrimJSON(System.String input);
```


## Nested types

- `Colossal.IO.AssetDatabase.SettingAsset+Fragment`  
- `Colossal.IO.AssetDatabase.SettingAsset+<Save>d__17`  
- `Colossal.IO.AssetDatabase.SettingAsset+<Save>d__20`  

