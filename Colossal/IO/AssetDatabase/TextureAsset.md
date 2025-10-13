# Colossal.IO.AssetDatabase.TextureAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IO.AssetDatabase.IAssetData<UnityEngine.Texture>`, `Colossal.IO.AssetDatabase.IAssetData<Colossal.AssetPipeline.Importers.TextureImporter+ITexture>`, `Colossal.IO.AssetDatabase.ITextureAsset`  

## Code

```csharp
public class TextureAsset : Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile, Colossal.IO.AssetDatabase.IAssetData<UnityEngine.Texture>, Colossal.IO.AssetDatabase.IAssetData<Colossal.AssetPipeline.Importers.TextureImporter+ITexture>, Colossal.IO.AssetDatabase.ITextureAsset
{
    protected UnityEngine.Texture m_Instance;
    private System.Int32 m_InstanceRefCount;
    private System.Int32 m_ObjectInstanceRefCount;
    private UnityEngine.Experimental.Rendering.GraphicsFormat m_Format;
    private UnityEngine.Rendering.TextureDimension m_Dimension;
    private System.Int32 m_MipsCount;
    private System.Int32 m_Width;
    private System.Int32 m_Height;
    private System.Int32 m_Depth;
    private UnityEngine.FilterMode m_FilterMode;
    private UnityEngine.TextureWrapMode m_WrapMode;
    private System.Int32 m_AnisoLevel;
    private Unity.Collections.NativeArray<System.Byte> m_RawData;
    public static readonly System.String[] kExtensions;
    public static const System.String kExtension;
    public static const System.UInt16 kFormatVersion;

    public UnityEngine.Experimental.Rendering.GraphicsFormat format { get; }
    public UnityEngine.Rendering.TextureDimension dimension { get; }
    public System.Int32 mipsCount { get; }
    public System.Int32 width { get; }
    public System.Int32 height { get; }
    public System.Int32 depth { get; }
    public UnityEngine.FilterMode filterMode { get; }
    public UnityEngine.TextureWrapMode wrapMode { get; }
    public System.Int32 anisoLevel { get; }
    public Unity.Collections.NativeArray<System.Byte> rawData { get; }
    public System.Boolean isDataLoaded { get; }
    public System.Boolean isObjectLoaded { get; }
    public Colossal.IO.AssetDatabase.LoadState state { get; }

    public TextureAsset();

    private System.Void <Load>b__56_0(System.TimeSpan t);
    private System.Void <LoadData>b__57_0(System.TimeSpan t);
    private System.Void <Save>b__53_0(System.TimeSpan t);
    private UnityEngine.Texture ApplyData(UnityEngine.Texture2D tex2D, UnityEngine.Texture2DArray tex2DArray, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU keepOnCPU);
    private System.Void ApplyMipBias(System.Int32 mipBiasOverride, System.Int32& offset, System.Int32& size);
    private System.Void CreateTexture(UnityEngine.Texture2D& tex2D, UnityEngine.Texture2DArray& tex2DArray);
    private System.Boolean DecrementRefCount(Colossal.IO.AssetDatabase.LoadState target, System.Boolean force);
    public Unity.Collections.NativeArray<System.Byte> GetMidMipData(System.Int32 nbMidMipLevels, System.Int32 tileSize);
    private System.Int32 GetMipBiasOverride(System.Int32 mipBiasOverride);
    private System.Boolean IncrementRefCount(Colossal.IO.AssetDatabase.LoadState target);
    public T Load<T>(System.Int32 mipBiasOverride, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU keepOnCPU);
    public UnityEngine.Texture Load(System.Int32 mipBiasOverride);
    public UnityEngine.Texture Load(System.Int32 mipBiasOverride, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU keepOnCPU);
    protected virtual System.Void LoadAdditionalData(System.IO.BinaryReader sr);
    public System.Void LoadData(System.Int32 mipBiasOverride);
    private Unity.Collections.NativeArray<System.Byte> LoadData(System.Int32 firstMip, System.Int32 lastMip, System.Int32& width, System.Int32& height);
    private System.Void LoadData(System.IO.BinaryReader sr, System.Int32 offset, System.Int32 size);
    private System.UInt16 ReadHeader(System.IO.BinaryReader sr);
    public virtual System.Void Save(System.Boolean force);
    public System.Void Save(System.Int32 mipBias, System.Boolean force);
    protected virtual System.Void SaveAdditionalData(System.IO.BinaryWriter sw);
    public Colossal.IO.AssetDatabase.ImageAsset SaveAsImageAsset(Colossal.IO.AssetDatabase.ImageAsset+FileFormat fileFormat, Colossal.IO.AssetDatabase.AssetDataPath targetPath, Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase);
    public System.Void SetData(UnityEngine.Texture texture);
    public System.Void SetData(Colossal.AssetPipeline.Importers.TextureImporter+ITexture texture);
    private System.Void SetDataFromUnity(UnityEngine.Texture texture);
    public System.Boolean ToImageData(Colossal.IO.AssetDatabase.ImageAsset+FileFormat fileFormat, System.UInt32& channels, System.UInt32& bpp, System.Byte[]& data);
    public virtual System.Void Unload(System.Boolean force);
    private System.Void UnloadData();
}
```


## Fields

- `protected UnityEngine.Texture m_Instance`  

```csharp
protected UnityEngine.Texture m_Instance;
```

- `private System.Int32 m_InstanceRefCount`  

```csharp
private System.Int32 m_InstanceRefCount;
```

- `private System.Int32 m_ObjectInstanceRefCount`  

```csharp
private System.Int32 m_ObjectInstanceRefCount;
```

- `private UnityEngine.Experimental.Rendering.GraphicsFormat m_Format`  

```csharp
private UnityEngine.Experimental.Rendering.GraphicsFormat m_Format;
```

- `private UnityEngine.Rendering.TextureDimension m_Dimension`  

```csharp
private UnityEngine.Rendering.TextureDimension m_Dimension;
```

- `private System.Int32 m_MipsCount`  

```csharp
private System.Int32 m_MipsCount;
```

- `private System.Int32 m_Width`  

```csharp
private System.Int32 m_Width;
```

- `private System.Int32 m_Height`  

```csharp
private System.Int32 m_Height;
```

- `private System.Int32 m_Depth`  

```csharp
private System.Int32 m_Depth;
```

- `private UnityEngine.FilterMode m_FilterMode`  

```csharp
private UnityEngine.FilterMode m_FilterMode;
```

- `private UnityEngine.TextureWrapMode m_WrapMode`  

```csharp
private UnityEngine.TextureWrapMode m_WrapMode;
```

- `private System.Int32 m_AnisoLevel`  

```csharp
private System.Int32 m_AnisoLevel;
```

- `private Unity.Collections.NativeArray<System.Byte> m_RawData`  

```csharp
private Unity.Collections.NativeArray<System.Byte> m_RawData;
```

- `public static readonly System.String[] kExtensions`  

```csharp
public static readonly System.String[] kExtensions;
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

- `public UnityEngine.Experimental.Rendering.GraphicsFormat format { get }`  

```csharp
public UnityEngine.Experimental.Rendering.GraphicsFormat format { get; }
```

- `public UnityEngine.Rendering.TextureDimension dimension { get }`  

```csharp
public UnityEngine.Rendering.TextureDimension dimension { get; }
```

- `public System.Int32 mipsCount { get }`  

```csharp
public System.Int32 mipsCount { get; }
```

- `public System.Int32 width { get }`  

```csharp
public System.Int32 width { get; }
```

- `public System.Int32 height { get }`  

```csharp
public System.Int32 height { get; }
```

- `public System.Int32 depth { get }`  

```csharp
public System.Int32 depth { get; }
```

- `public UnityEngine.FilterMode filterMode { get }`  

```csharp
public UnityEngine.FilterMode filterMode { get; }
```

- `public UnityEngine.TextureWrapMode wrapMode { get }`  

```csharp
public UnityEngine.TextureWrapMode wrapMode { get; }
```

- `public System.Int32 anisoLevel { get }`  

```csharp
public System.Int32 anisoLevel { get; }
```

- `public Unity.Collections.NativeArray<System.Byte> rawData { get }`  

```csharp
public Unity.Collections.NativeArray<System.Byte> rawData { get; }
```

- `public System.Boolean isDataLoaded { get }`  

```csharp
public System.Boolean isDataLoaded { get; }
```

- `public System.Boolean isObjectLoaded { get }`  

```csharp
public System.Boolean isObjectLoaded { get; }
```

- `public Colossal.IO.AssetDatabase.LoadState state { get }`  

```csharp
public Colossal.IO.AssetDatabase.LoadState state { get; }
```


## Constructors

- `public TextureAsset()`  

```csharp
public TextureAsset();
```


## Methods

- `private <Load>b__56_0(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <Load>b__56_0(System.TimeSpan t);
```

- `private <LoadData>b__57_0(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <LoadData>b__57_0(System.TimeSpan t);
```

- `private <Save>b__53_0(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <Save>b__53_0(System.TimeSpan t);
```

- `private ApplyData(UnityEngine.Texture2D tex2D, UnityEngine.Texture2DArray tex2DArray, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU keepOnCPU) : UnityEngine.Texture`  

```csharp
private UnityEngine.Texture ApplyData(UnityEngine.Texture2D tex2D, UnityEngine.Texture2DArray tex2DArray, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU keepOnCPU);
```

- `private ApplyMipBias(System.Int32 mipBiasOverride, System.Int32& offset, System.Int32& size) : System.Void`  

```csharp
private System.Void ApplyMipBias(System.Int32 mipBiasOverride, System.Int32& offset, System.Int32& size);
```

- `private CreateTexture(UnityEngine.Texture2D& tex2D, UnityEngine.Texture2DArray& tex2DArray) : System.Void`  

```csharp
private System.Void CreateTexture(UnityEngine.Texture2D& tex2D, UnityEngine.Texture2DArray& tex2DArray);
```

- `private DecrementRefCount(Colossal.IO.AssetDatabase.LoadState target, System.Boolean force = False) : System.Boolean`  

```csharp
private System.Boolean DecrementRefCount(Colossal.IO.AssetDatabase.LoadState target, System.Boolean force);
```

- `public GetMidMipData(System.Int32 nbMidMipLevels, System.Int32 tileSize) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public Unity.Collections.NativeArray<System.Byte> GetMidMipData(System.Int32 nbMidMipLevels, System.Int32 tileSize);
```

- `private GetMipBiasOverride(System.Int32 mipBiasOverride) : System.Int32`  

```csharp
private System.Int32 GetMipBiasOverride(System.Int32 mipBiasOverride);
```

- `private IncrementRefCount(Colossal.IO.AssetDatabase.LoadState target) : System.Boolean`  

```csharp
private System.Boolean IncrementRefCount(Colossal.IO.AssetDatabase.LoadState target);
```

- `public Load<T>(System.Int32 mipBiasOverride = -1, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU keepOnCPU = Dont) : T`  

```csharp
public T Load<T>(System.Int32 mipBiasOverride, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU keepOnCPU);
```

- `public Load(System.Int32 mipBiasOverride = -1) : UnityEngine.Texture`  

```csharp
public UnityEngine.Texture Load(System.Int32 mipBiasOverride);
```

- `public Load(System.Int32 mipBiasOverride, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU keepOnCPU) : UnityEngine.Texture`  

```csharp
public UnityEngine.Texture Load(System.Int32 mipBiasOverride, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU keepOnCPU);
```

- `protected virtual LoadAdditionalData(System.IO.BinaryReader sr) : System.Void`  

```csharp
protected virtual System.Void LoadAdditionalData(System.IO.BinaryReader sr);
```

- `public LoadData(System.Int32 mipBiasOverride = -1) : System.Void`  

```csharp
public System.Void LoadData(System.Int32 mipBiasOverride);
```

- `private LoadData(System.Int32 firstMip, System.Int32 lastMip, System.Int32& width, System.Int32& height) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
private Unity.Collections.NativeArray<System.Byte> LoadData(System.Int32 firstMip, System.Int32 lastMip, System.Int32& width, System.Int32& height);
```

- `private LoadData(System.IO.BinaryReader sr, System.Int32 offset, System.Int32 size) : System.Void`  

```csharp
private System.Void LoadData(System.IO.BinaryReader sr, System.Int32 offset, System.Int32 size);
```

- `private ReadHeader(System.IO.BinaryReader sr) : System.UInt16`  

```csharp
private System.UInt16 ReadHeader(System.IO.BinaryReader sr);
```

- `public virtual Save(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Save(System.Boolean force);
```

- `public Save(System.Int32 mipBias = 0, System.Boolean force = False) : System.Void`  

```csharp
public System.Void Save(System.Int32 mipBias, System.Boolean force);
```

- `protected virtual SaveAdditionalData(System.IO.BinaryWriter sw) : System.Void`  

```csharp
protected virtual System.Void SaveAdditionalData(System.IO.BinaryWriter sw);
```

- `public SaveAsImageAsset(Colossal.IO.AssetDatabase.ImageAsset+FileFormat fileFormat, Colossal.IO.AssetDatabase.AssetDataPath targetPath, Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase) : Colossal.IO.AssetDatabase.ImageAsset`  

```csharp
public Colossal.IO.AssetDatabase.ImageAsset SaveAsImageAsset(Colossal.IO.AssetDatabase.ImageAsset+FileFormat fileFormat, Colossal.IO.AssetDatabase.AssetDataPath targetPath, Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase);
```

- `public SetData(UnityEngine.Texture texture) : System.Void`  

```csharp
public System.Void SetData(UnityEngine.Texture texture);
```

- `public SetData(Colossal.AssetPipeline.Importers.TextureImporter+ITexture texture) : System.Void`  

```csharp
public System.Void SetData(Colossal.AssetPipeline.Importers.TextureImporter+ITexture texture);
```

- `private SetDataFromUnity(UnityEngine.Texture texture) : System.Void`  

```csharp
private System.Void SetDataFromUnity(UnityEngine.Texture texture);
```

- `public ToImageData(Colossal.IO.AssetDatabase.ImageAsset+FileFormat fileFormat, System.UInt32& channels, System.UInt32& bpp, System.Byte[]& data) : System.Boolean`  

```csharp
public System.Boolean ToImageData(Colossal.IO.AssetDatabase.ImageAsset+FileFormat fileFormat, System.UInt32& channels, System.UInt32& bpp, System.Byte[]& data);
```

- `public virtual Unload(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Unload(System.Boolean force);
```

- `private UnloadData() : System.Void`  

```csharp
private System.Void UnloadData();
```


## Nested types

- `Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU`  

