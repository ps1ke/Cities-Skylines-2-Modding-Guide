# Colossal.IO.AssetDatabase.PackageAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IO.AssetDatabase.IAssetData<Colossal.IO.AssetDatabase.ILocalAssetDatabase>`  

## Code

```csharp
public class PackageAsset : Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile, Colossal.IO.AssetDatabase.IAssetData<Colossal.IO.AssetDatabase.ILocalAssetDatabase>
{
    private Colossal.IO.AssetDatabase.ILocalAssetDatabase m_Source;
    public static readonly System.String[] kExtensions;
    public static const System.String kExtension;

    public PackageAsset();

    private System.Void Save(System.Boolean force, System.Boolean preserveTimestamp);
    public virtual System.Void Save(System.Boolean force);
    public System.Void SaveWithTimestamp(System.Boolean force);
    public System.Void SetData(Colossal.IO.AssetDatabase.ILocalAssetDatabase source);
    public virtual System.Void Unload(System.Boolean force);
}
```


## Fields

- `private Colossal.IO.AssetDatabase.ILocalAssetDatabase m_Source`  

```csharp
private Colossal.IO.AssetDatabase.ILocalAssetDatabase m_Source;
```

- `public static readonly System.String[] kExtensions`  

```csharp
public static readonly System.String[] kExtensions;
```

- `public static const System.String kExtension`  

```csharp
public static const System.String kExtension;
```


## Constructors

- `public PackageAsset()`  

```csharp
public PackageAsset();
```


## Methods

- `private Save(System.Boolean force, System.Boolean preserveTimestamp) : System.Void`  

```csharp
private System.Void Save(System.Boolean force, System.Boolean preserveTimestamp);
```

- `public virtual Save(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Save(System.Boolean force);
```

- `public SaveWithTimestamp(System.Boolean force = False) : System.Void`  

```csharp
public System.Void SaveWithTimestamp(System.Boolean force);
```

- `public SetData(Colossal.IO.AssetDatabase.ILocalAssetDatabase source) : System.Void`  

```csharp
public System.Void SetData(Colossal.IO.AssetDatabase.ILocalAssetDatabase source);
```

- `public virtual Unload(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Unload(System.Boolean force);
```


