# Colossal.IO.AssetDatabase.AtlasAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.TextureAsset`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IO.AssetDatabase.IAssetData<UnityEngine.Texture>`, `Colossal.IO.AssetDatabase.IAssetData<Colossal.AssetPipeline.Importers.TextureImporter+ITexture>`, `Colossal.IO.AssetDatabase.ITextureAsset`, `System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.AtlasFrame+Entry>`, `System.Collections.IEnumerable`, `Colossal.IO.AssetDatabase.IAssetData<Colossal.IO.AssetDatabase.AtlasFrame>`  

## Code

```csharp
public class AtlasAsset : Colossal.IO.AssetDatabase.TextureAsset, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile, Colossal.IO.AssetDatabase.IAssetData<UnityEngine.Texture>, Colossal.IO.AssetDatabase.IAssetData<Colossal.AssetPipeline.Importers.TextureImporter+ITexture>, Colossal.IO.AssetDatabase.ITextureAsset, System.Collections.Generic.IEnumerable<Colossal.IO.AssetDatabase.AtlasFrame+Entry>, System.Collections.IEnumerable, Colossal.IO.AssetDatabase.IAssetData<Colossal.IO.AssetDatabase.AtlasFrame>
{
    private Colossal.IO.AssetDatabase.AtlasFrame m_AtlasFrame;
    public static const System.String kExtension;
    public static const System.UInt16 kFormatVersion;

    public Colossal.IO.AssetDatabase.AtlasFrame frameData { get; }

    public AtlasAsset();

    public System.Collections.Generic.IEnumerator<Colossal.IO.AssetDatabase.AtlasFrame+Entry> GetEnumerator();
    public Colossal.IO.AssetDatabase.AtlasFrame Load();
    protected virtual System.Void LoadAdditionalData(System.IO.BinaryReader sr);
    protected virtual System.Void SaveAdditionalData(System.IO.BinaryWriter sw);
    public System.Void SetData(Colossal.IO.AssetDatabase.AtlasFrame atlasFrame);
    private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
    public virtual System.Void Unload(System.Boolean force);
}
```


## Fields

- `private Colossal.IO.AssetDatabase.AtlasFrame m_AtlasFrame`  

```csharp
private Colossal.IO.AssetDatabase.AtlasFrame m_AtlasFrame;
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

- `public Colossal.IO.AssetDatabase.AtlasFrame frameData { get }`  

```csharp
public Colossal.IO.AssetDatabase.AtlasFrame frameData { get; }
```


## Constructors

- `public AtlasAsset()`  

```csharp
public AtlasAsset();
```


## Methods

- `public GetEnumerator() : System.Collections.Generic.IEnumerator<Colossal.IO.AssetDatabase.AtlasFrame+Entry>`  

```csharp
public System.Collections.Generic.IEnumerator<Colossal.IO.AssetDatabase.AtlasFrame+Entry> GetEnumerator();
```

- `public Load() : Colossal.IO.AssetDatabase.AtlasFrame`  

```csharp
public Colossal.IO.AssetDatabase.AtlasFrame Load();
```

- `protected virtual LoadAdditionalData(System.IO.BinaryReader sr) : System.Void`  

```csharp
protected virtual System.Void LoadAdditionalData(System.IO.BinaryReader sr);
```

- `protected virtual SaveAdditionalData(System.IO.BinaryWriter sw) : System.Void`  

```csharp
protected virtual System.Void SaveAdditionalData(System.IO.BinaryWriter sw);
```

- `public SetData(Colossal.IO.AssetDatabase.AtlasFrame atlasFrame) : System.Void`  

```csharp
public System.Void SetData(Colossal.IO.AssetDatabase.AtlasFrame atlasFrame);
```

- `private System.Collections.IEnumerable.GetEnumerator() : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator System.Collections.IEnumerable.GetEnumerator();
```

- `public virtual Unload(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Unload(System.Boolean force);
```


