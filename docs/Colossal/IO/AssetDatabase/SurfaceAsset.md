# Colossal.IO.AssetDatabase.SurfaceAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IO.AssetDatabase.IAssetData<Colossal.AssetPipeline.Surface>`, `Colossal.IO.AssetDatabase.IAssetData<UnityEngine.Material>`, `Colossal.AssetPipeline.ISurface`  

## Fields

- `private System.Collections.Generic.Dictionary<System.String, System.Single> m_Floats`  
- `private System.Collections.Generic.Dictionary<System.String, System.Int32> m_Ints`  
- `private System.Collections.Generic.Dictionary<System.String, UnityEngine.Vector4> m_Vectors`  
- `private System.Collections.Generic.Dictionary<System.String, UnityEngine.Color> m_Colors`  
- `private System.Collections.Generic.Dictionary<System.String, Colossal.IO.AssetDatabase.TextureAsset> m_Textures`  
- `private System.Collections.Generic.HashSet<System.String> m_Keywords`  
- `private UnityEngine.Material m_Instance`  
- `private System.Int32 m_MaterialTemplateHash`  
- `private System.Boolean m_IsVTMaterial`  
- `private System.Boolean m_UsingVT`  
- `private System.UInt16 m_Version`  
- `private Colossal.IO.AssetDatabase.SurfaceAssetVTHeader m_VTHeader`  
- `private System.Int32 m_InstanceRefCount`  
- `private System.Int32 m_ObjectInstanceRefCount`  
- `private Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] m_VTAtlassingInfos`  
- `private Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] m_PreReservedAtlassingInfos`  
- `private Colossal.IO.AssetDatabase.VirtualTexturing.VTTextureParamBlock[] m_VTTextureParamBlock`  
- `private Colossal.IO.AssetDatabase.VTSurfaceAsset m_VTSurfaceAsset`  
- `private static UnityEngine.Material s_DefaultMaterial`  
- `public static readonly System.String[] kExtensions`  
- `public static const System.String kExtension`  
- `public static const System.UInt16 kFormatVersion`  

## Properties

- `public static UnityEngine.Material kDefaultMaterial { get }`  
- `public System.Collections.Generic.IReadOnlyDictionary<System.String, System.Single> floats { get }`  
- `public System.Collections.Generic.IReadOnlyDictionary<System.String, System.Int32> ints { get }`  
- `public System.Collections.Generic.IReadOnlyDictionary<System.String, UnityEngine.Vector4> vectors { get }`  
- `public System.Collections.Generic.IReadOnlyDictionary<System.String, UnityEngine.Color> colors { get }`  
- `public System.Collections.Generic.IReadOnlyDictionary<System.String, Colossal.IO.AssetDatabase.TextureAsset> textures { get }`  
- `public System.Collections.Generic.IReadOnlyCollection<System.String> keywords { get }`  
- `public System.Boolean isCurrentlyUsingVT { get }`  
- `public System.Boolean isVTMaterial { get }`  
- `public System.Int32 materialTemplateHash { get }`  
- `public System.UInt16 version { get }`  
- `public System.Boolean isDataLoaded { get }`  
- `public System.Boolean isObjectLoaded { get }`  
- `public Colossal.IO.AssetDatabase.LoadState state { get }`  
- `public System.Int32 stackCount { get }`  
- `public System.Collections.Generic.IEnumerable<Colossal.Hash128> preProcessedTextureGuids { get }`  
- `public System.Boolean hasVTSurfaceAsset { get }`  
- `public Colossal.IO.AssetDatabase.VTSurfaceAsset vtSurfaceAsset { get }`  
- `public Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] VTAtlassingInfos { get }`  
- `public Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] PreReservedAtlassingInfos { get }`  

## Constructors

- `public SurfaceAsset()`  

## Methods

- `private <Load>b__71_0(System.TimeSpan t) : System.Void`  
- `private <Save>b__75_0(System.TimeSpan t) : System.Void`  
- `private <SetDataFromSurface>b__66_0(System.Collections.Generic.KeyValuePair<System.String, Colossal.AssetPipeline.Importers.TextureImporter+ITexture> kvp) : System.Collections.Generic.KeyValuePair<System.String, Colossal.IO.AssetDatabase.TextureAsset>`  
- `public AddKeyword(System.String keyword) : System.Void`  
- `public AddMidMipTexturesDataToDictionnary(System.Int32 stackConfigIndex, System.Int32 nbMidMipLevels, System.Int32 tileSize, Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData, System.Collections.Generic.Dictionary<Colossal.Hash128, Unity.Collections.NativeArray<System.Byte>> mipMipDataDict) : System.Void`  
- `public ClearVTAtlassingInfos() : System.Void`  
- `public ComputeVTLayersMask(Colossal.IO.AssetDatabase.MaterialLibrary+MaterialDescription vtMaterialData, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]>[] materialTextures, System.Int64[] textureHash) : System.Int32`  
- `public CopyFrom(Colossal.IO.AssetDatabase.SurfaceAsset surfaceAsset) : System.Void`  
- `private DecrementRefCount(Colossal.IO.AssetDatabase.LoadState target, System.Boolean force = False) : System.Boolean`  
- `public GetMipBiasOverride() : System.Int32`  
- `public GetPreProcessedTextureGuid(System.Int32 stackIndex, System.Int32 layerIndex) : Colossal.Hash128`  
- `public GetTemplateMaterial() : UnityEngine.Material`  
- `public GetUnbiasedStackTextureSize(System.Int32 stackConfigIndex) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize`  
- `public HasKeyword(System.String keyword) : System.Boolean`  
- `public HasProperty(System.String property) : System.Boolean`  
- `private IncrementRefCount(Colossal.IO.AssetDatabase.LoadState target) : System.Boolean`  
- `public IsHandledByVirtualTexturing(System.Collections.Generic.KeyValuePair<System.String, Colossal.IO.AssetDatabase.TextureAsset> propNameAndAsset) : System.Boolean`  
- `public IsVTMaterialFromHeader() : System.Boolean`  
- `public Load(System.Int32 mipBias = -1, System.Boolean loadTextures = True, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU mode = Dont, System.Boolean useVT = True) : UnityEngine.Material`  
- `public LoadHeader() : System.Void`  
- `public LoadProperties(System.Boolean useVT) : System.Void`  
- `public LoadTexturesVT(System.Int32 stackConfigIndex, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, Colossal.IO.AssetDatabase.VTSurfaceDataHandler vtSurfaceDataHandler, Colossal.IO.AssetDatabase.TexturesAsyncLoader texturesAsyncLoader, System.Int32 nbPreProcessedMidMipLevels) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize`  
- `public LoadVTAsync(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, System.Int32 mipBias, System.Int32 tileSize, System.Int32 nbPreProcessedMidMipLevels, System.Boolean duplicate = False) : System.Void`  
- `public PreRegisterToVT(Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] preReservedAtlassingInfo) : System.Void`  
- `private ReadHeader(System.IO.BinaryReader sr) : System.Void`  
- `private ReadMaterialPropertyLegacy(System.IO.BinaryReader sr) : System.Boolean`  
- `private ReadPropertiesLegacy(System.IO.BinaryReader sr) : System.Void`  
- `private ReadVTHeader(System.IO.BinaryReader sr) : System.Void`  
- `public RegisterToVT(Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem) : System.Void`  
- `private ResolveLegacyMaterials(System.Int32 oldHash, System.Int32& newHash) : System.Boolean`  
- `public virtual Save(System.Boolean force = False) : System.Void`  
- `public Save(System.Int32 mipBias = 0, System.Boolean force = False, System.Boolean saveTextures = True, System.Boolean vt = False, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig = null, System.Collections.Generic.Dictionary<Colossal.IO.AssetDatabase.TextureAsset, System.Collections.Generic.List<Colossal.IO.AssetDatabase.SurfaceAsset>> textureReferencesMap = null, System.Nullable<System.Int32> tileSize = null, System.Nullable<System.Int32> nbMidMipLevelsRequested = null) : System.Boolean`  
- `public SaveData(System.Boolean force = False) : System.Void`  
- `private SaveVTHeader(System.IO.BinaryWriter sw) : System.Void`  
- `public SetData(Colossal.AssetPipeline.Surface surface) : System.Void`  
- `public SetData(UnityEngine.Material material) : System.Void`  
- `private SetDataFromSurface(Colossal.AssetPipeline.Surface surface) : System.Void`  
- `public SetMaterialHash(System.Int32 hash) : System.Void`  
- `private SyncFromUnityMaterial(System.Boolean allProperties) : System.Void`  
- `private SyncToUnityMaterial(System.Int32 mipBiasOverride = -1, System.Boolean loadTextures = True, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU mode = Dont) : System.Void`  
- `public virtual Unload(System.Boolean force = False) : System.Void`  
- `public UnloadTextures() : System.Void`  
- `public UpdateColors(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, UnityEngine.Color>> colors) : System.Void`  
- `public UpdateFloats(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.Single>> floats) : System.Void`  
- `public UpdateInts(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, System.Int32>> ints) : System.Void`  
- `public UpdateKeywords(System.Collections.Generic.IEnumerable<System.String> keywords) : System.Void`  
- `public UpdateMaterialHash(System.Int32 hash) : System.Int32`  
- `public UpdateMipBias(Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase, System.Int32 mipBias, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested) : System.Void`  
- `public UpdateTexture(System.String property, Colossal.IO.AssetDatabase.TextureAsset texture) : System.Void`  
- `public UpdateTextures(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, Colossal.IO.AssetDatabase.TextureAsset>> textures) : System.Void`  
- `public UpdateVectors(System.Collections.Generic.IEnumerable<System.Collections.Generic.KeyValuePair<System.String, UnityEngine.Vector4>> vectors) : System.Void`  

## Nested types

- `Colossal.IO.AssetDatabase.SurfaceAsset+<>c`  
- `Colossal.IO.AssetDatabase.SurfaceAsset+<>c__DisplayClass75_0`  
- `Colossal.IO.AssetDatabase.SurfaceAsset+<get_preProcessedTextureGuids>d__86`  

