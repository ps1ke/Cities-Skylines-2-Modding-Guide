# Colossal.IO.AssetDatabase.VTSettingsAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`  

## Code

```csharp
public class VTSettingsAsset : Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile
{
    public static const System.String kExtension;

    public VTSettingsAsset();

    public System.Int32 Load(System.Int32 tileSize, System.Int32& midMipsCount);
    public System.Void Save(System.Int32 mipBias, System.Int32 tileSize, System.Int32 midMipsCount);
}
```


## Fields

- `public static const System.String kExtension`  

```csharp
public static const System.String kExtension;
```


## Constructors

- `public VTSettingsAsset()`  

```csharp
public VTSettingsAsset();
```


## Methods

- `public Load(System.Int32 tileSize, System.Int32& midMipsCount) : System.Int32`  

```csharp
public System.Int32 Load(System.Int32 tileSize, System.Int32& midMipsCount);
```

- `public Save(System.Int32 mipBias, System.Int32 tileSize, System.Int32 midMipsCount) : System.Void`  

```csharp
public System.Void Save(System.Int32 mipBias, System.Int32 tileSize, System.Int32 midMipsCount);
```


