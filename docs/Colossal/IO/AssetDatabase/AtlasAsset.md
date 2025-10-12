# Colossal.IO.AssetDatabase.AtlasAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.TextureAsset`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IO.AssetDatabase.IAssetData<UnityEngine.Texture>`, `Colossal.IO.AssetDatabase.IAssetData<Colossal.AssetPipeline.Importers.TextureImporter+ITexture>`, `Colossal.IO.AssetDatabase.ITextureAsset`, `System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.AtlasFrame+Entry>`, `System.Collections.IEnumerable`, `Colossal.IO.AssetDatabase.IAssetData<Colossal.IO.AssetDatabase.AtlasFrame>`  

## Fields

- `private Colossal.IO.AssetDatabase.AtlasFrame m_AtlasFrame`  
- `public static const System.String kExtension`  
- `public static const System.UInt16 kFormatVersion`  

## Properties

- `public Colossal.IO.AssetDatabase.AtlasFrame frameData { get }`  

## Constructors

- `public AtlasAsset()`  

## Methods

- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Colossal.IO.AssetDatabase.AtlasFrame+Entry>`  
- `public Load() : Colossal.IO.AssetDatabase.AtlasFrame`  
- `protected virtual LoadAdditionalData(System.IO.BinaryReader sr) : System.Void`  
- `protected virtual SaveAdditionalData(System.IO.BinaryWriter sw) : System.Void`  
- `public SetData(Colossal.IO.AssetDatabase.AtlasFrame atlasFrame) : System.Void`  
- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  
- `public virtual Unload(System.Boolean force = False) : System.Void`  

