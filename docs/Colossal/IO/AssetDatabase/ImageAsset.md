# Colossal.IO.AssetDatabase.ImageAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.FileAsset`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IO.AssetDatabase.ITextureAsset`  

## Fields

- `private UnityEngine.Texture2D m_Instance`  
- `public static readonly System.String[] kExtensions`  
- `public static const System.String kPngExtension`  
- `public static const System.String kTifExtension`  
- `public static const System.String kTiffExtension`  
- `public static const System.String kJpgExtension`  
- `public static const System.String kJpegExtension`  

## Properties

- `public Colossal.IO.AssetDatabase.LoadState state { get }`  

## Constructors

- `public ImageAsset()`  

## Methods

- `public Load(System.Int32 mipBiasOverride = -1) : UnityEngine.Texture`  
- `public Load(System.Boolean srgb) : UnityEngine.Texture2D`  
- `public Save(Colossal.IO.AssetDatabase.ImageAsset+FileFormat fileFormat, Colossal.IO.AssetDatabase.AssetDataPath targetPath, Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase) : Colossal.IO.AssetDatabase.ImageAsset`  
- `public virtual Unload(System.Boolean force = False) : System.Void`  

## Nested types

- `Colossal.IO.AssetDatabase.ImageAsset+FileFormat`  

