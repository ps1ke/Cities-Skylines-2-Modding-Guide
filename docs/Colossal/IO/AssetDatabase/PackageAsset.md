# Colossal.IO.AssetDatabase.PackageAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IO.AssetDatabase.IAssetData<Colossal.IO.AssetDatabase.ILocalAssetDatabase>`  

## Fields

- `private Colossal.IO.AssetDatabase.ILocalAssetDatabase m_Source`  
- `public static readonly System.String[] kExtensions`  
- `public static const System.String kExtension`  

## Constructors

- `public PackageAsset()`  

## Methods

- `private Save(System.Boolean force, System.Boolean preserveTimestamp) : System.Void`  
- `public virtual Save(System.Boolean force = False) : System.Void`  
- `public SaveWithTimestamp(System.Boolean force = False) : System.Void`  
- `public SetData(Colossal.IO.AssetDatabase.ILocalAssetDatabase source) : System.Void`  
- `public virtual Unload(System.Boolean force = False) : System.Void`  

