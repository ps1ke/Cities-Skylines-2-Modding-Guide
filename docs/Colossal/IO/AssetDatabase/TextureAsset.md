# Colossal.IO.AssetDatabase.TextureAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`, `Colossal.IO.AssetDatabase.IAssetData<UnityEngine.Texture>`, `Colossal.IO.AssetDatabase.IAssetData<Colossal.AssetPipeline.Importers.TextureImporter+ITexture>`, `Colossal.IO.AssetDatabase.ITextureAsset`  

## Fields

- `protected UnityEngine.Texture m_Instance`  
- `private System.Int32 m_InstanceRefCount`  
- `private System.Int32 m_ObjectInstanceRefCount`  
- `private UnityEngine.Experimental.Rendering.GraphicsFormat m_Format`  
- `private UnityEngine.Rendering.TextureDimension m_Dimension`  
- `private System.Int32 m_MipsCount`  
- `private System.Int32 m_Width`  
- `private System.Int32 m_Height`  
- `private System.Int32 m_Depth`  
- `private UnityEngine.FilterMode m_FilterMode`  
- `private UnityEngine.TextureWrapMode m_WrapMode`  
- `private System.Int32 m_AnisoLevel`  
- `private Unity.Collections.NativeArray<System.Byte> m_RawData`  
- `public static readonly System.String[] kExtensions`  
- `public static const System.String kExtension`  
- `public static const System.UInt16 kFormatVersion`  

## Properties

- `public UnityEngine.Experimental.Rendering.GraphicsFormat format { get }`  
- `public UnityEngine.Rendering.TextureDimension dimension { get }`  
- `public System.Int32 mipsCount { get }`  
- `public System.Int32 width { get }`  
- `public System.Int32 height { get }`  
- `public System.Int32 depth { get }`  
- `public UnityEngine.FilterMode filterMode { get }`  
- `public UnityEngine.TextureWrapMode wrapMode { get }`  
- `public System.Int32 anisoLevel { get }`  
- `public Unity.Collections.NativeArray<System.Byte> rawData { get }`  
- `public System.Boolean isDataLoaded { get }`  
- `public System.Boolean isObjectLoaded { get }`  
- `public Colossal.IO.AssetDatabase.LoadState state { get }`  

## Constructors

- `public TextureAsset()`  

## Methods

- `private <Load>b__56_0(System.TimeSpan t) : System.Void`  
- `private <LoadData>b__57_0(System.TimeSpan t) : System.Void`  
- `private <Save>b__53_0(System.TimeSpan t) : System.Void`  
- `private ApplyData(UnityEngine.Texture2D tex2D, UnityEngine.Texture2DArray tex2DArray, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU keepOnCPU) : UnityEngine.Texture`  
- `private ApplyMipBias(System.Int32 mipBiasOverride, System.Int32& offset, System.Int32& size) : System.Void`  
- `private CreateTexture(UnityEngine.Texture2D& tex2D, UnityEngine.Texture2DArray& tex2DArray) : System.Void`  
- `private DecrementRefCount(Colossal.IO.AssetDatabase.LoadState target, System.Boolean force = False) : System.Boolean`  
- `public GetMidMipData(System.Int32 nbMidMipLevels, System.Int32 tileSize) : Unity.Collections.NativeArray<System.Byte>`  
- `private GetMipBiasOverride(System.Int32 mipBiasOverride) : System.Int32`  
- `private IncrementRefCount(Colossal.IO.AssetDatabase.LoadState target) : System.Boolean`  
- `public Load<T>(System.Int32 mipBiasOverride = -1, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU keepOnCPU = Dont) : T`  
- `public Load(System.Int32 mipBiasOverride = -1) : UnityEngine.Texture`  
- `public Load(System.Int32 mipBiasOverride, Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU keepOnCPU) : UnityEngine.Texture`  
- `protected virtual LoadAdditionalData(System.IO.BinaryReader sr) : System.Void`  
- `public LoadData(System.Int32 mipBiasOverride = -1) : System.Void`  
- `private LoadData(System.Int32 firstMip, System.Int32 lastMip, System.Int32& width, System.Int32& height) : Unity.Collections.NativeArray<System.Byte>`  
- `private LoadData(System.IO.BinaryReader sr, System.Int32 offset, System.Int32 size) : System.Void`  
- `private ReadHeader(System.IO.BinaryReader sr) : System.UInt16`  
- `public virtual Save(System.Boolean force = False) : System.Void`  
- `public Save(System.Int32 mipBias = 0, System.Boolean force = False) : System.Void`  
- `protected virtual SaveAdditionalData(System.IO.BinaryWriter sw) : System.Void`  
- `public SaveAsImageAsset(Colossal.IO.AssetDatabase.ImageAsset+FileFormat fileFormat, Colossal.IO.AssetDatabase.AssetDataPath targetPath, Colossal.IO.AssetDatabase.ILocalAssetDatabase targetDatabase) : Colossal.IO.AssetDatabase.ImageAsset`  
- `public SetData(UnityEngine.Texture texture) : System.Void`  
- `public SetData(Colossal.AssetPipeline.Importers.TextureImporter+ITexture texture) : System.Void`  
- `private SetDataFromUnity(UnityEngine.Texture texture) : System.Void`  
- `public ToImageData(Colossal.IO.AssetDatabase.ImageAsset+FileFormat fileFormat, System.UInt32& channels, System.UInt32& bpp, System.Byte[]& data) : System.Boolean`  
- `public virtual Unload(System.Boolean force = False) : System.Void`  
- `private UnloadData() : System.Void`  

## Nested types

- `Colossal.IO.AssetDatabase.TextureAsset+KeepOnCPU`  

