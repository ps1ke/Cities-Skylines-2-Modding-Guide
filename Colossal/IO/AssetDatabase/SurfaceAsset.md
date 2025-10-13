# Colossal.IO.AssetDatabase.SurfaceAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IO.AssetDatabase.IAssetData<Colossal.AssetPipeline.Surface>`, `Colossal.IO.AssetDatabase.IAssetData<UnityEngine.Material>`, `Colossal.AssetPipeline.ISurface`  

## Code

```csharp
public class SurfaceAsset : Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile, Colossal.IO.AssetDatabase.IAssetData<Colossal.AssetPipeline.Surface>, Colossal.IO.AssetDatabase.IAssetData<UnityEngine.Material>, Colossal.AssetPipeline.ISurface
{
    private System.Collections.Generic.Dictionary<System.String, System.Single> m_Floats;
    private System.Collections.Generic.Dictionary<System.String, System.Int32> m_Ints;
    private System.Collections.Generic.Dictionary<System.String, UnityEngine.Vector4> m_Vectors;
    private System.Collections.Generic.Dictionary<System.String, UnityEngine.Color> m_Colors;
    private System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.TextureAsset> m_Textures;
    private System.Collections.Generic.HashSet<System.String> m_Keywords;
    private UnityEngine.Material m_Instance;
    private System.Int32 m_MaterialTemplateHash;
    private System.Boolean m_IsVTMaterial;
    private System.Boolean m_UsingVT;
    private System.UInt16 m_Version;
    private Colossal.IO.AssetDatabase.SurfaceAssetVTHeader m_VTHeader;
    private System.Int32 m_InstanceRefCount;
    private System.Int32 m_ObjectInstanceRefCount;
    private Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] m_VTAtlassingInfos;
    private Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] m_PreReservedAtlassingInfos;
    private Colossal.IO.AssetDatabase.VirtualTexturing.VTTextureParamBlock[] m_VTTextureParamBlock;
    private Colossal.IO.AssetDatabase.VTSurfaceAsset m_VTSurfaceAsset;
    private static UnityEngine.Material s_DefaultMaterial;
    public static readonly System.String[] kExtensions;
    public static const System.String kExtension;
    public static const System.UInt16 kFormatVersion;

    public static UnityEngine.Material kDefaultMaterial { get; }
    public System.Collections.Generic.IReadOnlyDictionary<System.String, System.Single> floats { get; }
    public System.Collections.Generic.IReadOnlyDictionary<System.String, System.Int32> ints { get; }
    public System.Collections.Generic.IReadOnlyDictionary<System.String, UnityEngine.Vector4> vectors { get; }
    public System.Collections.Generic.IReadOnlyDictionary<System.String, UnityEngine.Color> colors { get; }
    public System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.IO.AssetDatabase.TextureAsset> textures { get; }
    public System.Collections.Generic.IReadOnlyCollection<System.String> keywords { get; }
    public System.Boolean isCurrentlyUsingVT { get; }
    public System.Boolean isVTMaterial { get; }
    public System.Int32 materialTemplateHash { get; }
    public System.UInt16 version { get; }
    public System.Boolean isDataLoaded { get; }
    public System.Boolean isObjectLoaded { get; }
    public Colossal.IO.AssetDatabase.LoadState state { get; }
    public System.Int32 stackCount { get; }
    public System.Collections.Generic.IEnumerable<Colossal.Hash128> preProcessedTextureGuids { get; }
    public System.Boolean hasVTSurfaceAsset { get; }
    public Colossal.IO.AssetDatabase.VTSurfaceAsset vtSurfaceAsset { get; }
    public Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] VTAtlassingInfos { get; }
    public Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] PreReservedAtlassingInfos { get; }

    public SurfaceAsset();

    private System.Void <Load>b__71_0(System.TimeSpan t);
    private System.Void <Save>b__75_0(System.TimeSpan t);
    private System.Collections.Generic.KeyValuePair<System.String, Colossal.IO.AssetDatabase.TextureAsset> <SetDataFromSurface>b__66_0(System.Collections.Generic.KeyValuePair<System.String, Colossal.AssetPipeline.Importers.TextureImporter+ITexture> kvp);
    public System.Void AddKeyword(System.String keyword);
    public System.Void AddMidMipTexturesDataToDictionnary(System.Int32 stackConfigIndex, System.Int32 nbMidMipLevels, System.Int32 tileSize, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData, System.Collections.Generic.Dictionary<Colossal.Hash128, Unity.Collections.NativeArray<System.Byte>> mipMipDataDict);
    public System.Void ClearVTAtlassingInfos();
    public System.Int32 ComputeVTLayersMask(Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]>[] materialTextures, System.Int64[] textureHash);
    public System.Void CopyFrom(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset);
    private System.Boolean DecrementRefCount(Colossal.IO.AssetDatabase.LoadState target, System.Boolean force);
    public System.Int32 GetMipBiasOverride();
    public Colossal.Hash128 GetPreProcessedTextureGuid(System.Int32 stackIndex, System.Int32 layerIndex);
    public UnityEngine.Material GetTemplateMaterial();
    public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize GetUnbiasedStackTextureSize(System.Int32 stackConfigIndex);
    public System.Boolean HasKeyword(System.String keyword);
    public System.Boolean HasProperty(System.String property);
    private System.Boolean IncrementRefCount(Colossal.IO.AssetDatabase.LoadState target);
    public System.Boolean IsHandledByVirtualTexturing(System.Collections.Generic.KeyValuePair<System.String, Colossal.IO.AssetDatabase.TextureAsset> propNameAndAsset);
    public System.Boolean IsVTMaterialFromHeader();
    public UnityEngine.Material Load(System.Int32 mipBias, System.Boolean loadTextures, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU mode, System.Boolean useVT);
    public System.Void LoadHeader();
    public System.Void LoadProperties(System.Boolean useVT);
    public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize LoadTexturesVT(System.Int32 stackConfigIndex, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, Colossal.IO.AssetDatabase.VTSurfaceDataHandler vtSurfaceDataHandler, Colossal.IO.AssetDatabase.TexturesAsyncLoader texturesAsyncLoader, System.Int32 nbPreProcessedMidMipLevels);
    public System.Void LoadVTAsync(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, System.Int32 mipBias, System.Int32 tileSize, System.Int32 nbPreProcessedMidMipLevels, System.Boolean duplicate);
    public System.Void PreRegisterToVT(Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] preReservedAtlassingInfo);
    private System.Void ReadHeader(System.IO.BinaryReader sr);
    private System.Boolean ReadMaterialPropertyLegacy(System.IO.BinaryReader sr);
    private System.Void ReadPropertiesLegacy(System.IO.BinaryReader sr);
    private System.Void ReadVTHeader(System.IO.BinaryReader sr);
    public System.Void RegisterToVT(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem);
    private System.Boolean ResolveLegacyMaterials(System.Int32 oldHash, System.Int32& newHash);
    public virtual System.Void Save(System.Boolean force);
    public System.Boolean Save(System.Int32 mipBias, System.Boolean force, System.Boolean saveTextures, System.Boolean vt, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> textureReferencesMap, System.Nullable<System.Int32> tileSize, System.Nullable<System.Int32> nbMidMipLevelsRequested);
    public System.Void SaveData(System.Boolean force);
    private System.Void SaveVTHeader(System.IO.BinaryWriter sw);
    public System.Void SetData(Colossal.AssetPipeline.Surface surface);
    public System.Void SetData(UnityEngine.Material material);
    private System.Void SetDataFromSurface(Colossal.AssetPipeline.Surface surface);
    public System.Void SetMaterialHash(System.Int32 hash);
    private System.Void SyncFromUnityMaterial(System.Boolean allProperties);
    private System.Void SyncToUnityMaterial(System.Int32 mipBiasOverride, System.Boolean loadTextures, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU mode);
    public virtual System.Void Unload(System.Boolean force);
    public System.Void UnloadTextures();
    public System.Void UpdateColors(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, UnityEngine.Color>> colors);
    public System.Void UpdateFloats(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.Single>> floats);
    public System.Void UpdateInts(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.Int32>> ints);
    public System.Void UpdateKeywords(System.Collections.Generic.IEnumerable<System.String> keywords);
    public System.Int32 UpdateMaterialHash(System.Int32 hash);
    public System.Void UpdateMipBias(Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase, System.Int32 mipBias, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested);
    public System.Void UpdateTexture(System.String property, Colossal.IO.AssetDatabase.TextureAsset texture);
    public System.Void UpdateTextures(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, Colossal.IO.AssetDatabase.TextureAsset>> textures);
    public System.Void UpdateVectors(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, UnityEngine.Vector4>> vectors);
}
```


## Fields

- `private System.Collections.Generic.Dictionary<System.String, System.Single> m_Floats`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Single> m_Floats;
```

- `private System.Collections.Generic.Dictionary<System.String, System.Int32> m_Ints`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.Int32> m_Ints;
```

- `private System.Collections.Generic.Dictionary<System.String, UnityEngine.Vector4> m_Vectors`  

```csharp
private System.Collections.Generic.Dictionary<System.String, UnityEngine.Vector4> m_Vectors;
```

- `private System.Collections.Generic.Dictionary<System.String, UnityEngine.Color> m_Colors`  

```csharp
private System.Collections.Generic.Dictionary<System.String, UnityEngine.Color> m_Colors;
```

- `private System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.TextureAsset> m_Textures`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.TextureAsset> m_Textures;
```

- `private System.Collections.Generic.HashSet<System.String> m_Keywords`  

```csharp
private System.Collections.Generic.HashSet<System.String> m_Keywords;
```

- `private UnityEngine.Material m_Instance`  

```csharp
private UnityEngine.Material m_Instance;
```

- `private System.Int32 m_MaterialTemplateHash`  

```csharp
private System.Int32 m_MaterialTemplateHash;
```

- `private System.Boolean m_IsVTMaterial`  

```csharp
private System.Boolean m_IsVTMaterial;
```

- `private System.Boolean m_UsingVT`  

```csharp
private System.Boolean m_UsingVT;
```

- `private System.UInt16 m_Version`  

```csharp
private System.UInt16 m_Version;
```

- `private Colossal.IO.AssetDatabase.SurfaceAssetVTHeader m_VTHeader`  

```csharp
private Colossal.IO.AssetDatabase.SurfaceAssetVTHeader m_VTHeader;
```

- `private System.Int32 m_InstanceRefCount`  

```csharp
private System.Int32 m_InstanceRefCount;
```

- `private System.Int32 m_ObjectInstanceRefCount`  

```csharp
private System.Int32 m_ObjectInstanceRefCount;
```

- `private Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] m_VTAtlassingInfos`  

```csharp
private Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] m_VTAtlassingInfos;
```

- `private Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] m_PreReservedAtlassingInfos`  

```csharp
private Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] m_PreReservedAtlassingInfos;
```

- `private Colossal.IO.AssetDatabase.VirtualTexturing.VTTextureParamBlock[] m_VTTextureParamBlock`  

```csharp
private Colossal.IO.AssetDatabase.VirtualTexturing.VTTextureParamBlock[] m_VTTextureParamBlock;
```

- `private Colossal.IO.AssetDatabase.VTSurfaceAsset m_VTSurfaceAsset`  

```csharp
private Colossal.IO.AssetDatabase.VTSurfaceAsset m_VTSurfaceAsset;
```

- `private static UnityEngine.Material s_DefaultMaterial`  

```csharp
private static UnityEngine.Material s_DefaultMaterial;
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

- `public static UnityEngine.Material kDefaultMaterial { get }`  

```csharp
public static UnityEngine.Material kDefaultMaterial { get; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<System.String, System.Single> floats { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<System.String, System.Single> floats { get; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<System.String, System.Int32> ints { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<System.String, System.Int32> ints { get; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<System.String, UnityEngine.Vector4> vectors { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<System.String, UnityEngine.Vector4> vectors { get; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<System.String, UnityEngine.Color> colors { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<System.String, UnityEngine.Color> colors { get; }
```

- `public System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.IO.AssetDatabase.TextureAsset> textures { get }`  

```csharp
public System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.IO.AssetDatabase.TextureAsset> textures { get; }
```

- `public System.Collections.Generic.IReadOnlyCollection<System.String> keywords { get }`  

```csharp
public System.Collections.Generic.IReadOnlyCollection<System.String> keywords { get; }
```

- `public System.Boolean isCurrentlyUsingVT { get }`  

```csharp
public System.Boolean isCurrentlyUsingVT { get; }
```

- `public System.Boolean isVTMaterial { get }`  

```csharp
public System.Boolean isVTMaterial { get; }
```

- `public System.Int32 materialTemplateHash { get }`  

```csharp
public System.Int32 materialTemplateHash { get; }
```

- `public System.UInt16 version { get }`  

```csharp
public System.UInt16 version { get; }
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

- `public System.Int32 stackCount { get }`  

```csharp
public System.Int32 stackCount { get; }
```

- `public System.Collections.Generic.IEnumerable<Colossal.Hash128> preProcessedTextureGuids { get }`  

```csharp
public System.Collections.Generic.IEnumerable<Colossal.Hash128> preProcessedTextureGuids { get; }
```

- `public System.Boolean hasVTSurfaceAsset { get }`  

```csharp
public System.Boolean hasVTSurfaceAsset { get; }
```

- `public Colossal.IO.AssetDatabase.VTSurfaceAsset vtSurfaceAsset { get }`  

```csharp
public Colossal.IO.AssetDatabase.VTSurfaceAsset vtSurfaceAsset { get; }
```

- `public Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] VTAtlassingInfos { get }`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] VTAtlassingInfos { get; }
```

- `public Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] PreReservedAtlassingInfos { get }`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] PreReservedAtlassingInfos { get; }
```


## Constructors

- `public SurfaceAsset()`  

```csharp
public SurfaceAsset();
```


## Methods

- `private <Load>b__71_0(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <Load>b__71_0(System.TimeSpan t);
```

- `private <Save>b__75_0(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <Save>b__75_0(System.TimeSpan t);
```

- `private <SetDataFromSurface>b__66_0(System.Collections.Generic.KeyValuePair<System.String, Colossal.AssetPipeline.Importers.TextureImporter+ITexture> kvp) : System.Collections.Generic.KeyValuePair<System.String, Colossal.IO.AssetDatabase.TextureAsset>`  

```csharp
private System.Collections.Generic.KeyValuePair<System.String, Colossal.IO.AssetDatabase.TextureAsset> <SetDataFromSurface>b__66_0(System.Collections.Generic.KeyValuePair<System.String, Colossal.AssetPipeline.Importers.TextureImporter+ITexture> kvp);
```

- `public AddKeyword(System.String keyword) : System.Void`  

```csharp
public System.Void AddKeyword(System.String keyword);
```

- `public AddMidMipTexturesDataToDictionnary(System.Int32 stackConfigIndex, System.Int32 nbMidMipLevels, System.Int32 tileSize, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData, System.Collections.Generic.Dictionary<Colossal.Hash128, Unity.Collections.NativeArray<System.Byte>> mipMipDataDict) : System.Void`  

```csharp
public System.Void AddMidMipTexturesDataToDictionnary(System.Int32 stackConfigIndex, System.Int32 nbMidMipLevels, System.Int32 tileSize, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData, System.Collections.Generic.Dictionary<Colossal.Hash128, Unity.Collections.NativeArray<System.Byte>> mipMipDataDict);
```

- `public ClearVTAtlassingInfos() : System.Void`  

```csharp
public System.Void ClearVTAtlassingInfos();
```

- `public ComputeVTLayersMask(Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]>[] materialTextures, System.Int64[] textureHash) : System.Int32`  

```csharp
public System.Int32 ComputeVTLayersMask(Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]>[] materialTextures, System.Int64[] textureHash);
```

- `public CopyFrom(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset) : System.Void`  

```csharp
public System.Void CopyFrom(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset);
```

- `private DecrementRefCount(Colossal.IO.AssetDatabase.LoadState target, System.Boolean force = False) : System.Boolean`  

```csharp
private System.Boolean DecrementRefCount(Colossal.IO.AssetDatabase.LoadState target, System.Boolean force);
```

- `public GetMipBiasOverride() : System.Int32`  

```csharp
public System.Int32 GetMipBiasOverride();
```

- `public GetPreProcessedTextureGuid(System.Int32 stackIndex, System.Int32 layerIndex) : Colossal.Hash128`  

```csharp
public Colossal.Hash128 GetPreProcessedTextureGuid(System.Int32 stackIndex, System.Int32 layerIndex);
```

- `public GetTemplateMaterial() : UnityEngine.Material`  

```csharp
public UnityEngine.Material GetTemplateMaterial();
```

- `public GetUnbiasedStackTextureSize(System.Int32 stackConfigIndex) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize GetUnbiasedStackTextureSize(System.Int32 stackConfigIndex);
```

- `public HasKeyword(System.String keyword) : System.Boolean`  

```csharp
public System.Boolean HasKeyword(System.String keyword);
```

- `public HasProperty(System.String property) : System.Boolean`  

```csharp
public System.Boolean HasProperty(System.String property);
```

- `private IncrementRefCount(Colossal.IO.AssetDatabase.LoadState target) : System.Boolean`  

```csharp
private System.Boolean IncrementRefCount(Colossal.IO.AssetDatabase.LoadState target);
```

- `public IsHandledByVirtualTexturing(System.Collections.Generic.KeyValuePair<System.String, Colossal.IO.AssetDatabase.TextureAsset> propNameAndAsset) : System.Boolean`  

```csharp
public System.Boolean IsHandledByVirtualTexturing(System.Collections.Generic.KeyValuePair<System.String, Colossal.IO.AssetDatabase.TextureAsset> propNameAndAsset);
```

- `public IsVTMaterialFromHeader() : System.Boolean`  

```csharp
public System.Boolean IsVTMaterialFromHeader();
```

- `public Load(System.Int32 mipBias = -1, System.Boolean loadTextures = True, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU mode = Dont, System.Boolean useVT = True) : UnityEngine.Material`  

```csharp
public UnityEngine.Material Load(System.Int32 mipBias, System.Boolean loadTextures, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU mode, System.Boolean useVT);
```

- `public LoadHeader() : System.Void`  

```csharp
public System.Void LoadHeader();
```

- `public LoadProperties(System.Boolean useVT) : System.Void`  

```csharp
public System.Void LoadProperties(System.Boolean useVT);
```

- `public LoadTexturesVT(System.Int32 stackConfigIndex, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, Colossal.IO.AssetDatabase.VTSurfaceDataHandler vtSurfaceDataHandler, Colossal.IO.AssetDatabase.TexturesAsyncLoader texturesAsyncLoader, System.Int32 nbPreProcessedMidMipLevels) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize LoadTexturesVT(System.Int32 stackConfigIndex, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, Colossal.IO.AssetDatabase.VTSurfaceDataHandler vtSurfaceDataHandler, Colossal.IO.AssetDatabase.TexturesAsyncLoader texturesAsyncLoader, System.Int32 nbPreProcessedMidMipLevels);
```

- `public LoadVTAsync(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, System.Int32 mipBias, System.Int32 tileSize, System.Int32 nbPreProcessedMidMipLevels, System.Boolean duplicate = False) : System.Void`  

```csharp
public System.Void LoadVTAsync(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, System.Int32 mipBias, System.Int32 tileSize, System.Int32 nbPreProcessedMidMipLevels, System.Boolean duplicate);
```

- `public PreRegisterToVT(Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] preReservedAtlassingInfo) : System.Void`  

```csharp
public System.Void PreRegisterToVT(Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] preReservedAtlassingInfo);
```

- `private ReadHeader(System.IO.BinaryReader sr) : System.Void`  

```csharp
private System.Void ReadHeader(System.IO.BinaryReader sr);
```

- `private ReadMaterialPropertyLegacy(System.IO.BinaryReader sr) : System.Boolean`  

```csharp
private System.Boolean ReadMaterialPropertyLegacy(System.IO.BinaryReader sr);
```

- `private ReadPropertiesLegacy(System.IO.BinaryReader sr) : System.Void`  

```csharp
private System.Void ReadPropertiesLegacy(System.IO.BinaryReader sr);
```

- `private ReadVTHeader(System.IO.BinaryReader sr) : System.Void`  

```csharp
private System.Void ReadVTHeader(System.IO.BinaryReader sr);
```

- `public RegisterToVT(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem) : System.Void`  

```csharp
public System.Void RegisterToVT(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem);
```

- `private ResolveLegacyMaterials(System.Int32 oldHash, System.Int32& newHash) : System.Boolean`  

```csharp
private System.Boolean ResolveLegacyMaterials(System.Int32 oldHash, System.Int32& newHash);
```

- `public virtual Save(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Save(System.Boolean force);
```

- `public Save(System.Int32 mipBias = 0, System.Boolean force = False, System.Boolean saveTextures = True, System.Boolean vt = False, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig = null, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> textureReferencesMap = null, System.Nullable<System.Int32> tileSize = null, System.Nullable<System.Int32> nbMidMipLevelsRequested = null) : System.Boolean`  

```csharp
public System.Boolean Save(System.Int32 mipBias, System.Boolean force, System.Boolean saveTextures, System.Boolean vt, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> textureReferencesMap, System.Nullable<System.Int32> tileSize, System.Nullable<System.Int32> nbMidMipLevelsRequested);
```

- `public SaveData(System.Boolean force = False) : System.Void`  

```csharp
public System.Void SaveData(System.Boolean force);
```

- `private SaveVTHeader(System.IO.BinaryWriter sw) : System.Void`  

```csharp
private System.Void SaveVTHeader(System.IO.BinaryWriter sw);
```

- `public SetData(Colossal.AssetPipeline.Surface surface) : System.Void`  

```csharp
public System.Void SetData(Colossal.AssetPipeline.Surface surface);
```

- `public SetData(UnityEngine.Material material) : System.Void`  

```csharp
public System.Void SetData(UnityEngine.Material material);
```

- `private SetDataFromSurface(Colossal.AssetPipeline.Surface surface) : System.Void`  

```csharp
private System.Void SetDataFromSurface(Colossal.AssetPipeline.Surface surface);
```

- `public SetMaterialHash(System.Int32 hash) : System.Void`  

```csharp
public System.Void SetMaterialHash(System.Int32 hash);
```

- `private SyncFromUnityMaterial(System.Boolean allProperties) : System.Void`  

```csharp
private System.Void SyncFromUnityMaterial(System.Boolean allProperties);
```

- `private SyncToUnityMaterial(System.Int32 mipBiasOverride = -1, System.Boolean loadTextures = True, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU mode = Dont) : System.Void`  

```csharp
private System.Void SyncToUnityMaterial(System.Int32 mipBiasOverride, System.Boolean loadTextures, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU mode);
```

- `public virtual Unload(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Unload(System.Boolean force);
```

- `public UnloadTextures() : System.Void`  

```csharp
public System.Void UnloadTextures();
```

- `public UpdateColors(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, UnityEngine.Color>> colors) : System.Void`  

```csharp
public System.Void UpdateColors(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, UnityEngine.Color>> colors);
```

- `public UpdateFloats(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.Single>> floats) : System.Void`  

```csharp
public System.Void UpdateFloats(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.Single>> floats);
```

- `public UpdateInts(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.Int32>> ints) : System.Void`  

```csharp
public System.Void UpdateInts(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.Int32>> ints);
```

- `public UpdateKeywords(System.Collections.Generic.IEnumerable<System.String> keywords) : System.Void`  

```csharp
public System.Void UpdateKeywords(System.Collections.Generic.IEnumerable<System.String> keywords);
```

- `public UpdateMaterialHash(System.Int32 hash) : System.Int32`  

```csharp
public System.Int32 UpdateMaterialHash(System.Int32 hash);
```

- `public UpdateMipBias(Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase, System.Int32 mipBias, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested) : System.Void`  

```csharp
public System.Void UpdateMipBias(Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase, System.Int32 mipBias, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested);
```

- `public UpdateTexture(System.String property, Colossal.IO.AssetDatabase.TextureAsset texture) : System.Void`  

```csharp
public System.Void UpdateTexture(System.String property, Colossal.IO.AssetDatabase.TextureAsset texture);
```

- `public UpdateTextures(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, Colossal.IO.AssetDatabase.TextureAsset>> textures) : System.Void`  

```csharp
public System.Void UpdateTextures(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, Colossal.IO.AssetDatabase.TextureAsset>> textures);
```

- `public UpdateVectors(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, UnityEngine.Vector4>> vectors) : System.Void`  

```csharp
public System.Void UpdateVectors(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, UnityEngine.Vector4>> vectors);
```


## Nested types

- `Colossal.IO.AssetDatabase.SurfaceAsset+<>c`  
- `Colossal.IO.AssetDatabase.SurfaceAsset+<>c__DisplayClass75_0`  
- `Colossal.IO.AssetDatabase.SurfaceAsset+<get_preProcessedTextureGuids>d__86`  

