# Colossal.IO.AssetDatabase.ImageAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.FileAsset`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IO.AssetDatabase.ITextureAsset`  

## Code

```csharp
public class ImageAsset : Colossal.IO.AssetDatabase.FileAsset, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile, Colossal.IO.AssetDatabase.ITextureAsset
{
    private UnityEngine.Texture2D m_Instance;
    public static readonly System.String[] kExtensions;
    public static const System.String kPngExtension;
    public static const System.String kTifExtension;
    public static const System.String kTiffExtension;
    public static const System.String kJpgExtension;
    public static const System.String kJpegExtension;

    public Colossal.IO.AssetDatabase.LoadState state { get; }

    public ImageAsset();

    public UnityEngine.Texture Load(System.Int32 mipBiasOverride);
    public UnityEngine.Texture2D Load(System.Boolean srgb);
    public Colossal.IO.AssetDatabase.ImageAsset Save(Colossal.IO.AssetDatabase.ImageAsset+FileFormat fileFormat, Colossal.IO.AssetDatabase.AssetDataPath targetPath, Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase);
    public virtual System.Void Unload(System.Boolean force);
}
```


## Fields

- `private UnityEngine.Texture2D m_Instance`  

```csharp
private UnityEngine.Texture2D m_Instance;
```

- `public static readonly System.String[] kExtensions`  

```csharp
public static readonly System.String[] kExtensions;
```

- `public static const System.String kPngExtension`  

```csharp
public static const System.String kPngExtension;
```

- `public static const System.String kTifExtension`  

```csharp
public static const System.String kTifExtension;
```

- `public static const System.String kTiffExtension`  

```csharp
public static const System.String kTiffExtension;
```

- `public static const System.String kJpgExtension`  

```csharp
public static const System.String kJpgExtension;
```

- `public static const System.String kJpegExtension`  

```csharp
public static const System.String kJpegExtension;
```


## Properties

- `public Colossal.IO.AssetDatabase.LoadState state { get }`  

```csharp
public Colossal.IO.AssetDatabase.LoadState state { get; }
```


## Constructors

- `public ImageAsset()`  

```csharp
public ImageAsset();
```


## Methods

- `public Load(System.Int32 mipBiasOverride = -1) : UnityEngine.Texture`  

```csharp
public UnityEngine.Texture Load(System.Int32 mipBiasOverride);
```

- `public Load(System.Boolean srgb) : UnityEngine.Texture2D`  

```csharp
public UnityEngine.Texture2D Load(System.Boolean srgb);
```

- `public Save(Colossal.IO.AssetDatabase.ImageAsset+FileFormat fileFormat, Colossal.IO.AssetDatabase.AssetDataPath targetPath, Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase) : Colossal.IO.AssetDatabase.ImageAsset`  

```csharp
public Colossal.IO.AssetDatabase.ImageAsset Save(Colossal.IO.AssetDatabase.ImageAsset+FileFormat fileFormat, Colossal.IO.AssetDatabase.AssetDataPath targetPath, Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase);
```

- `public virtual Unload(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Unload(System.Boolean force);
```


## Nested types

- `Colossal.IO.AssetDatabase.ImageAsset+FileFormat`  

