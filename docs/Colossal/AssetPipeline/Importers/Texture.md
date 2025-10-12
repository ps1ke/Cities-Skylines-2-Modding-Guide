# Colossal.AssetPipeline.Importers.TextureImporter+Texture

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.Importers.TextureImporter+ITexture`, `System.IDisposable`  

**Attributes:** `BurstCompile`  

## Fields

- `private readonly System.String <name>k__BackingField`  
- `public readonly System.String path`  
- `public readonly System.Int64 fileDataLength`  
- `public Colossal.AssetPipeline.Native.NativeTextures+ImageFileInfo info`  
- `public System.Collections.Generic.List<Unity.Collections.NativeArray<System.Byte>> rawMips`  
- `public System.Collections.Generic.List<Unity.Collections.NativeArray<System.Byte>> compressedMips`  
- `private UnityEngine.Experimental.Rendering.GraphicsFormat <rawFormat>k__BackingField`  
- `private UnityEngine.Experimental.Rendering.GraphicsFormat <compressedFormat>k__BackingField`  
- `private System.Boolean <normalMap>k__BackingField`  
- `private System.Boolean sRGB`  
- `private System.Boolean <hasAlpha>k__BackingField`  
- `private UnityEngine.FilterMode <filterMode>k__BackingField`  
- `private UnityEngine.TextureWrapMode <wrapMode>k__BackingField`  
- `private System.Int32 <anisoLevel>k__BackingField`  
- `private Colossal.AssetPipeline.IAsset <sourceAsset>k__BackingField`  
- `private UnityEngine.Texture2D m_CachedObject`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfConvertSingleChannel`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfEnsure16Bits`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfComputeMips`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfCompressBC`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfSwapChannels`  
- `private static readonly Unity.Profiling.ProfilerMarker s_ProfCopyChannel`  

## Properties

- `public System.Int32 width { get }`  
- `public System.Int32 height { get }`  
- `public System.Int32 mipsCount { get }`  
- `public UnityEngine.Rendering.TextureDimension dimension { get }`  
- `public System.Int32 depth { get }`  
- `public System.String name { get; set }`  
- `public UnityEngine.Experimental.Rendering.GraphicsFormat format { get }`  
- `public UnityEngine.Experimental.Rendering.GraphicsFormat rawFormat { get; private set }`  
- `public UnityEngine.Experimental.Rendering.GraphicsFormat compressedFormat { get; private set }`  
- `public System.Int32 rawMipsCount { get }`  
- `public System.Int32 compressedMipsCount { get }`  
- `public System.Boolean normalMap { get; set }`  
- `public System.Boolean hasAlpha { get; set }`  
- `public UnityEngine.FilterMode filterMode { get; set }`  
- `public UnityEngine.TextureWrapMode wrapMode { get; set }`  
- `public System.Int32 anisoLevel { get; set }`  
- `public Colossal.AssetPipeline.IAsset sourceAsset { get; set }`  

## Constructors

- `public Texture(System.String name, System.String path, System.Int64 fileDataLength, System.Boolean sRGB)`  
- `public Texture(System.String name, System.String path, UnityEngine.Texture2D unityTexture)`  

## Methods

- `private Clamp(System.Int32 min, System.Int32 max, System.Int32 value) : System.Int32`  
- `public CompressBC(System.Int32 effort, Colossal.AssetPipeline.Native.NativeTextures+BlockCompressionFormat overrideCompressedFormat = None) : System.Void`  
- `public ComputeMips(System.Boolean wrapClamp, System.Boolean alphaIsTransparency) : System.Void`  
- `public ConvertToSingleChannel() : System.Void`  
- `public static CopyChannel(Colossal.AssetPipeline.Importers.TextureImporter+Texture src, System.Int32 srcChannel, Colossal.AssetPipeline.Importers.TextureImporter+Texture dst, System.Int32 dstChannel) : System.Void`  
- `private static CopyChannelImpl<T>(System.Int32 width, System.Int32 height, T* src, T* dst, System.Int32 srcChannels, System.Int32 dstChannels, System.Int32 chSrc, System.Int32 chDst) : System.Void`  
- `public static CreateUncompressed1Mip(System.String name, System.Int32 width, System.Int32 height, System.Boolean sRGB, Unity.Collections.NativeArray<System.Byte> data) : Colossal.AssetPipeline.Importers.TextureImporter+Texture`  
- `public Dispose() : System.Void`  
- `public Ensure16BitsPerChannel() : System.Void`  
- `private FractionalPart(System.Single input) : System.Single`  
- `private FractionalPart(System.Double input) : System.Double`  
- `public GetCompressedMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  
- `public virtual GetHashCode() : System.Int32`  
- `public GetMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  
- `public GetPixel(System.Int32 x, System.Int32 y) : UnityEngine.Color32`  
- `public GetPixelBilinear(System.Double x, System.Double y) : UnityEngine.Color32`  
- `public GetRawMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  
- `public static SwapChannels(Colossal.AssetPipeline.Importers.TextureImporter+Texture texA, System.Int32 channelA, Colossal.AssetPipeline.Importers.TextureImporter+Texture texB, System.Int32 channelB) : System.Void`  
- `private static SwapChannelsImpl<T>(System.Int32 width, System.Int32 height, T* dataA, T* dataB, System.Int32 channelsA, System.Int32 channelsB, System.Int32 chA, System.Int32 chB) : System.Void`  
- `public ToUnityTexture(System.Boolean hideAndDontSave = True) : UnityEngine.Texture`  
- `public ToUnityTextureRaw(System.Boolean hideAndDontSave = True) : UnityEngine.Texture`  

