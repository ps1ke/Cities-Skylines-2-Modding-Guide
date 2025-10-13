# Colossal.AssetPipeline.Importers.TextureImporter+Texture

**Assembly:** `Colossal.AssetPipeline`  
**Namespace:** `Colossal.AssetPipeline.Importers`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Colossal.AssetPipeline.Importers.TextureImporter+ITexture`, `System.IDisposable`  

**Attributes:** `BurstCompile`  

## Code

```csharp
public class Texture : Colossal.AssetPipeline.Importers.TextureImporter+ITexture, System.IDisposable
{
    private readonly System.String <name>k__BackingField;
    public readonly System.String path;
    public readonly System.Int64 fileDataLength;
    public Colossal.AssetPipeline.Native.NativeTextures+ImageFileInfo info;
    public System.Collections.Generic.List<Unity.Collections.NativeArray<System.Byte>> rawMips;
    public System.Collections.Generic.List<Unity.Collections.NativeArray<System.Byte>> compressedMips;
    private UnityEngine.Experimental.Rendering.GraphicsFormat <rawFormat>k__BackingField;
    private UnityEngine.Experimental.Rendering.GraphicsFormat <compressedFormat>k__BackingField;
    private System.Boolean <normalMap>k__BackingField;
    private System.Boolean sRGB;
    private System.Boolean <hasAlpha>k__BackingField;
    private UnityEngine.FilterMode <filterMode>k__BackingField;
    private UnityEngine.TextureWrapMode <wrapMode>k__BackingField;
    private System.Int32 <anisoLevel>k__BackingField;
    private Colossal.AssetPipeline.IAsset <sourceAsset>k__BackingField;
    private UnityEngine.Texture2D m_CachedObject;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfConvertSingleChannel;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfEnsure16Bits;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfComputeMips;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfCompressBC;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfSwapChannels;
    private static readonly Unity.Profiling.ProfilerMarker s_ProfCopyChannel;

    public System.Int32 width { get; }
    public System.Int32 height { get; }
    public System.Int32 mipsCount { get; }
    public UnityEngine.Rendering.TextureDimension dimension { get; }
    public System.Int32 depth { get; }
    public System.String name { get; set; }
    public UnityEngine.Experimental.Rendering.GraphicsFormat format { get; }
    public UnityEngine.Experimental.Rendering.GraphicsFormat rawFormat { get; private set; }
    public UnityEngine.Experimental.Rendering.GraphicsFormat compressedFormat { get; private set; }
    public System.Int32 rawMipsCount { get; }
    public System.Int32 compressedMipsCount { get; }
    public System.Boolean normalMap { get; set; }
    public System.Boolean hasAlpha { get; set; }
    public UnityEngine.FilterMode filterMode { get; set; }
    public UnityEngine.TextureWrapMode wrapMode { get; set; }
    public System.Int32 anisoLevel { get; set; }
    public Colossal.AssetPipeline.IAsset sourceAsset { get; set; }

    public Texture(System.String name, System.String path, System.Int64 fileDataLength, System.Boolean sRGB);
    public Texture(System.String name, System.String path, UnityEngine.Texture2D unityTexture);

    private System.Int32 Clamp(System.Int32 min, System.Int32 max, System.Int32 value);
    public System.Void CompressBC(System.Int32 effort, Colossal.AssetPipeline.Native.NativeTextures+BlockCompressionFormat overrideCompressedFormat);
    public System.Void ComputeMips(System.Boolean wrapClamp, System.Boolean alphaIsTransparency);
    public System.Void ConvertToSingleChannel();
    public static System.Void CopyChannel(Colossal.AssetPipeline.Importers.TextureImporter+Texture src, System.Int32 srcChannel, Colossal.AssetPipeline.Importers.TextureImporter+Texture dst, System.Int32 dstChannel);
    private static System.Void CopyChannelImpl<T>(System.Int32 width, System.Int32 height, T* src, T* dst, System.Int32 srcChannels, System.Int32 dstChannels, System.Int32 chSrc, System.Int32 chDst);
    public static Colossal.AssetPipeline.Importers.TextureImporter+Texture CreateUncompressed1Mip(System.String name, System.Int32 width, System.Int32 height, System.Boolean sRGB, Unity.Collections.NativeArray<System.Byte> data);
    public System.Void Dispose();
    public System.Void Ensure16BitsPerChannel();
    private System.Single FractionalPart(System.Single input);
    private System.Double FractionalPart(System.Double input);
    public Unity.Collections.NativeArray<System.Byte> GetCompressedMipData(System.Int32 slice, System.Int32 mip);
    public virtual System.Int32 GetHashCode();
    public Unity.Collections.NativeArray<System.Byte> GetMipData(System.Int32 slice, System.Int32 mip);
    public UnityEngine.Color32 GetPixel(System.Int32 x, System.Int32 y);
    public UnityEngine.Color32 GetPixelBilinear(System.Double x, System.Double y);
    public Unity.Collections.NativeArray<System.Byte> GetRawMipData(System.Int32 slice, System.Int32 mip);
    public static System.Void SwapChannels(Colossal.AssetPipeline.Importers.TextureImporter+Texture texA, System.Int32 channelA, Colossal.AssetPipeline.Importers.TextureImporter+Texture texB, System.Int32 channelB);
    private static System.Void SwapChannelsImpl<T>(System.Int32 width, System.Int32 height, T* dataA, T* dataB, System.Int32 channelsA, System.Int32 channelsB, System.Int32 chA, System.Int32 chB);
    public UnityEngine.Texture ToUnityTexture(System.Boolean hideAndDontSave);
    public UnityEngine.Texture ToUnityTextureRaw(System.Boolean hideAndDontSave);
}
```


## Fields

- `private readonly System.String <name>k__BackingField`  

```csharp
private readonly System.String <name>k__BackingField;
```

- `public readonly System.String path`  

```csharp
public readonly System.String path;
```

- `public readonly System.Int64 fileDataLength`  

```csharp
public readonly System.Int64 fileDataLength;
```

- `public Colossal.AssetPipeline.Native.NativeTextures+ImageFileInfo info`  

```csharp
public Colossal.AssetPipeline.Native.NativeTextures+ImageFileInfo info;
```

- `public System.Collections.Generic.List<Unity.Collections.NativeArray<System.Byte>> rawMips`  

```csharp
public System.Collections.Generic.List<Unity.Collections.NativeArray<System.Byte>> rawMips;
```

- `public System.Collections.Generic.List<Unity.Collections.NativeArray<System.Byte>> compressedMips`  

```csharp
public System.Collections.Generic.List<Unity.Collections.NativeArray<System.Byte>> compressedMips;
```

- `private UnityEngine.Experimental.Rendering.GraphicsFormat <rawFormat>k__BackingField`  

```csharp
private UnityEngine.Experimental.Rendering.GraphicsFormat <rawFormat>k__BackingField;
```

- `private UnityEngine.Experimental.Rendering.GraphicsFormat <compressedFormat>k__BackingField`  

```csharp
private UnityEngine.Experimental.Rendering.GraphicsFormat <compressedFormat>k__BackingField;
```

- `private System.Boolean <normalMap>k__BackingField`  

```csharp
private System.Boolean <normalMap>k__BackingField;
```

- `private System.Boolean sRGB`  

```csharp
private System.Boolean sRGB;
```

- `private System.Boolean <hasAlpha>k__BackingField`  

```csharp
private System.Boolean <hasAlpha>k__BackingField;
```

- `private UnityEngine.FilterMode <filterMode>k__BackingField`  

```csharp
private UnityEngine.FilterMode <filterMode>k__BackingField;
```

- `private UnityEngine.TextureWrapMode <wrapMode>k__BackingField`  

```csharp
private UnityEngine.TextureWrapMode <wrapMode>k__BackingField;
```

- `private System.Int32 <anisoLevel>k__BackingField`  

```csharp
private System.Int32 <anisoLevel>k__BackingField;
```

- `private Colossal.AssetPipeline.IAsset <sourceAsset>k__BackingField`  

```csharp
private Colossal.AssetPipeline.IAsset <sourceAsset>k__BackingField;
```

- `private UnityEngine.Texture2D m_CachedObject`  

```csharp
private UnityEngine.Texture2D m_CachedObject;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfConvertSingleChannel`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfConvertSingleChannel;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfEnsure16Bits`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfEnsure16Bits;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfComputeMips`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfComputeMips;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfCompressBC`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfCompressBC;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfSwapChannels`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfSwapChannels;
```

- `private static readonly Unity.Profiling.ProfilerMarker s_ProfCopyChannel`  

```csharp
private static readonly Unity.Profiling.ProfilerMarker s_ProfCopyChannel;
```


## Properties

- `public System.Int32 width { get }`  

```csharp
public System.Int32 width { get; }
```

- `public System.Int32 height { get }`  

```csharp
public System.Int32 height { get; }
```

- `public System.Int32 mipsCount { get }`  

```csharp
public System.Int32 mipsCount { get; }
```

- `public UnityEngine.Rendering.TextureDimension dimension { get }`  

```csharp
public UnityEngine.Rendering.TextureDimension dimension { get; }
```

- `public System.Int32 depth { get }`  

```csharp
public System.Int32 depth { get; }
```

- `public System.String name { get; set }`  

```csharp
public System.String name { get; set; }
```

- `public UnityEngine.Experimental.Rendering.GraphicsFormat format { get }`  

```csharp
public UnityEngine.Experimental.Rendering.GraphicsFormat format { get; }
```

- `public UnityEngine.Experimental.Rendering.GraphicsFormat rawFormat { get; private set }`  

```csharp
public UnityEngine.Experimental.Rendering.GraphicsFormat rawFormat { get; private set; }
```

- `public UnityEngine.Experimental.Rendering.GraphicsFormat compressedFormat { get; private set }`  

```csharp
public UnityEngine.Experimental.Rendering.GraphicsFormat compressedFormat { get; private set; }
```

- `public System.Int32 rawMipsCount { get }`  

```csharp
public System.Int32 rawMipsCount { get; }
```

- `public System.Int32 compressedMipsCount { get }`  

```csharp
public System.Int32 compressedMipsCount { get; }
```

- `public System.Boolean normalMap { get; set }`  

```csharp
public System.Boolean normalMap { get; set; }
```

- `public System.Boolean hasAlpha { get; set }`  

```csharp
public System.Boolean hasAlpha { get; set; }
```

- `public UnityEngine.FilterMode filterMode { get; set }`  

```csharp
public UnityEngine.FilterMode filterMode { get; set; }
```

- `public UnityEngine.TextureWrapMode wrapMode { get; set }`  

```csharp
public UnityEngine.TextureWrapMode wrapMode { get; set; }
```

- `public System.Int32 anisoLevel { get; set }`  

```csharp
public System.Int32 anisoLevel { get; set; }
```

- `public Colossal.AssetPipeline.IAsset sourceAsset { get; set }`  

```csharp
public Colossal.AssetPipeline.IAsset sourceAsset { get; set; }
```


## Constructors

- `public Texture(System.String name, System.String path, System.Int64 fileDataLength, System.Boolean sRGB)`  

```csharp
public Texture(System.String name, System.String path, System.Int64 fileDataLength, System.Boolean sRGB);
```

- `public Texture(System.String name, System.String path, UnityEngine.Texture2D unityTexture)`  

```csharp
public Texture(System.String name, System.String path, UnityEngine.Texture2D unityTexture);
```


## Methods

- `private Clamp(System.Int32 min, System.Int32 max, System.Int32 value) : System.Int32`  

```csharp
private System.Int32 Clamp(System.Int32 min, System.Int32 max, System.Int32 value);
```

- `public CompressBC(System.Int32 effort, Colossal.AssetPipeline.Native.NativeTextures+BlockCompressionFormat overrideCompressedFormat = None) : System.Void`  

```csharp
public System.Void CompressBC(System.Int32 effort, Colossal.AssetPipeline.Native.NativeTextures+BlockCompressionFormat overrideCompressedFormat);
```

- `public ComputeMips(System.Boolean wrapClamp, System.Boolean alphaIsTransparency) : System.Void`  

```csharp
public System.Void ComputeMips(System.Boolean wrapClamp, System.Boolean alphaIsTransparency);
```

- `public ConvertToSingleChannel() : System.Void`  

```csharp
public System.Void ConvertToSingleChannel();
```

- `public static CopyChannel(Colossal.AssetPipeline.Importers.TextureImporter+Texture src, System.Int32 srcChannel, Colossal.AssetPipeline.Importers.TextureImporter+Texture dst, System.Int32 dstChannel) : System.Void`  

```csharp
public static System.Void CopyChannel(Colossal.AssetPipeline.Importers.TextureImporter+Texture src, System.Int32 srcChannel, Colossal.AssetPipeline.Importers.TextureImporter+Texture dst, System.Int32 dstChannel);
```

- `private static CopyChannelImpl<T>(System.Int32 width, System.Int32 height, T* src, T* dst, System.Int32 srcChannels, System.Int32 dstChannels, System.Int32 chSrc, System.Int32 chDst) : System.Void`  

```csharp
private static System.Void CopyChannelImpl<T>(System.Int32 width, System.Int32 height, T* src, T* dst, System.Int32 srcChannels, System.Int32 dstChannels, System.Int32 chSrc, System.Int32 chDst);
```

- `public static CreateUncompressed1Mip(System.String name, System.Int32 width, System.Int32 height, System.Boolean sRGB, Unity.Collections.NativeArray<System.Byte> data) : Colossal.AssetPipeline.Importers.TextureImporter+Texture`  

```csharp
public static Colossal.AssetPipeline.Importers.TextureImporter+Texture CreateUncompressed1Mip(System.String name, System.Int32 width, System.Int32 height, System.Boolean sRGB, Unity.Collections.NativeArray<System.Byte> data);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public Ensure16BitsPerChannel() : System.Void`  

```csharp
public System.Void Ensure16BitsPerChannel();
```

- `private FractionalPart(System.Single input) : System.Single`  

```csharp
private System.Single FractionalPart(System.Single input);
```

- `private FractionalPart(System.Double input) : System.Double`  

```csharp
private System.Double FractionalPart(System.Double input);
```

- `public GetCompressedMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public Unity.Collections.NativeArray<System.Byte> GetCompressedMipData(System.Int32 slice, System.Int32 mip);
```

- `public virtual GetHashCode() : System.Int32`  

```csharp
public virtual System.Int32 GetHashCode();
```

- `public GetMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public Unity.Collections.NativeArray<System.Byte> GetMipData(System.Int32 slice, System.Int32 mip);
```

- `public GetPixel(System.Int32 x, System.Int32 y) : UnityEngine.Color32`  

```csharp
public UnityEngine.Color32 GetPixel(System.Int32 x, System.Int32 y);
```

- `public GetPixelBilinear(System.Double x, System.Double y) : UnityEngine.Color32`  

```csharp
public UnityEngine.Color32 GetPixelBilinear(System.Double x, System.Double y);
```

- `public GetRawMipData(System.Int32 slice, System.Int32 mip) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public Unity.Collections.NativeArray<System.Byte> GetRawMipData(System.Int32 slice, System.Int32 mip);
```

- `public static SwapChannels(Colossal.AssetPipeline.Importers.TextureImporter+Texture texA, System.Int32 channelA, Colossal.AssetPipeline.Importers.TextureImporter+Texture texB, System.Int32 channelB) : System.Void`  

```csharp
public static System.Void SwapChannels(Colossal.AssetPipeline.Importers.TextureImporter+Texture texA, System.Int32 channelA, Colossal.AssetPipeline.Importers.TextureImporter+Texture texB, System.Int32 channelB);
```

- `private static SwapChannelsImpl<T>(System.Int32 width, System.Int32 height, T* dataA, T* dataB, System.Int32 channelsA, System.Int32 channelsB, System.Int32 chA, System.Int32 chB) : System.Void`  

```csharp
private static System.Void SwapChannelsImpl<T>(System.Int32 width, System.Int32 height, T* dataA, T* dataB, System.Int32 channelsA, System.Int32 channelsB, System.Int32 chA, System.Int32 chB);
```

- `public ToUnityTexture(System.Boolean hideAndDontSave = True) : UnityEngine.Texture`  

```csharp
public UnityEngine.Texture ToUnityTexture(System.Boolean hideAndDontSave);
```

- `public ToUnityTextureRaw(System.Boolean hideAndDontSave = True) : UnityEngine.Texture`  

```csharp
public UnityEngine.Texture ToUnityTextureRaw(System.Boolean hideAndDontSave);
```


