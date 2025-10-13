# Colossal.IO.AssetDatabase.VTTextureAsset

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase`  

**Type:** class public  

**Base:** `Colossal.IO.AssetDatabase.AssetData`  
**Implements:** `Colossal.IO.AssetDatabase.IAssetData`, `System.IDisposable`, `System.IComparable<Colossal.IO.AssetDatabase.IAssetData>`, `System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>`, `Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset`, `Colossal.AssetPipeline.Diagnostic.Report+IFile`  

## Code

```csharp
public class VTTextureAsset : Colossal.IO.AssetDatabase.AssetData, Colossal.IO.AssetDatabase.IAssetData, System.IDisposable, System.IComparable<Colossal.IO.AssetDatabase.IAssetData>, System.IEquatable<Colossal.IO.AssetDatabase.IAssetData>, Colossal.AssetPipeline.Diagnostic.Report+IAddressableAsset, Colossal.AssetPipeline.Diagnostic.Report+IFile
{
    private UnityEngine.Texture m_Instance;
    private System.Boolean m_Loaded;
    private System.Int32 m_Width;
    private System.Int32 m_Height;
    private UnityEngine.Experimental.Rendering.GraphicsFormat m_Format;
    private Colossal.IO.AssetDatabase.TextureAsset m_TextureAsset;
    private System.UInt16 m_TileSize;
    private System.UInt16 m_NbMidMipLevels;
    public static const System.String kExtension;
    private static const System.UInt16 kFormatVersion;

    public System.Int32 width { get; }
    public System.Int32 height { get; }
    public UnityEngine.Experimental.Rendering.GraphicsFormat format { get; }
    public Colossal.IO.AssetDatabase.TextureAsset textureAsset { get; }
    public Colossal.IO.AssetDatabase.LoadState state { get; }

    public VTTextureAsset();

    private System.Void <Load>b__31_0(System.TimeSpan t);
    private System.Void <Save>b__20_0(System.TimeSpan t);
    public static System.Int32 ApplyMipBias(System.Int32 width, System.Int32 height, System.Int32 tileSize, UnityEngine.Experimental.Rendering.GraphicsFormat format, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize& preProcessedTextureSize, System.Int32& mipBias);
    public static System.Int32 CalcTotalTextureSize(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, System.Int32 nbTiles, System.Int32 nbTilesInX, System.Int32 nbTilesInY, System.Int32 nbMidMipLevels, System.Int32 highMipDataSize);
    public static System.Int32 CalculateHighMip(System.Int32& highMipDataIndex, System.Int32& highMipDataSize, System.Int32& nbMidMipLevels, System.Int32 dataLength, System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested);
    public static UnityEngine.Texture2D CreateDebugTexture2D(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, System.Int32 nbTiles, System.Int32 nbTilesInX, System.Int32 nbTilesInY, System.Int32 width, System.Int32 height, System.Byte[] tilesData, System.Byte[] highMipData, System.Int32 mipMapCount, System.Int32 nbMidMipLevels, UnityEngine.Experimental.Rendering.GraphicsFormat format, UnityEngine.FilterMode filterMode, UnityEngine.TextureWrapMode wrapMode, System.Int32 anisoLevel, System.String name);
    public static System.Void FillDebugTextureOneTile(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, System.Int32 nbTilesInX, System.Int32 nbTilesInY, System.Int32 width, Unity.Collections.NativeArray<System.Byte> srcData, Unity.Collections.NativeArray<System.Byte> dstData, System.Int32 srcOffsetInBlocks, System.Int32 dstOffsetInBlocks);
    private System.Void GetCompressedTileOffsetAndSize(System.Int64 fileOffset, System.Collections.Generic.IList<System.Int32> tileOffset, System.Int32 tileIndex, System.Int64& offset, System.Int32& size);
    public UnityEngine.Texture Load();
    public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize Load(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize supportedTextureSize, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, Colossal.IO.AssetDatabase.TexturesAsyncLoader texturesAsyncLoader, System.Int32 layerIndex, System.Int32 nbPreProcessedMidMipLevels);
    public System.Void LoadHeader();
    public static System.UInt16 PreProcessData(Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 originalWidth, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize preprocessedTextureSize, System.Int32 maxPreprocessedLevel, Unity.Collections.NativeSlice<System.Byte> inputSlice, Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& preProcessedData, Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& preProcessedDataPart2, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, System.Int32 tileSize);
    private System.UInt16 ReadHeader(System.IO.BinaryReader sr);
    public System.Void Save(System.Int32 mipBias, Colossal.IO.AssetDatabase.TextureAsset texture, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig);
    public virtual System.Void Unload(System.Boolean force);
}
```


## Fields

- `private UnityEngine.Texture m_Instance`  

```csharp
private UnityEngine.Texture m_Instance;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private System.Int32 m_Width`  

```csharp
private System.Int32 m_Width;
```

- `private System.Int32 m_Height`  

```csharp
private System.Int32 m_Height;
```

- `private UnityEngine.Experimental.Rendering.GraphicsFormat m_Format`  

```csharp
private UnityEngine.Experimental.Rendering.GraphicsFormat m_Format;
```

- `private Colossal.IO.AssetDatabase.TextureAsset m_TextureAsset`  

```csharp
private Colossal.IO.AssetDatabase.TextureAsset m_TextureAsset;
```

- `private System.UInt16 m_TileSize`  

```csharp
private System.UInt16 m_TileSize;
```

- `private System.UInt16 m_NbMidMipLevels`  

```csharp
private System.UInt16 m_NbMidMipLevels;
```

- `public static const System.String kExtension`  

```csharp
public static const System.String kExtension;
```

- `private static const System.UInt16 kFormatVersion`  

```csharp
private static const System.UInt16 kFormatVersion;
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

- `public UnityEngine.Experimental.Rendering.GraphicsFormat format { get }`  

```csharp
public UnityEngine.Experimental.Rendering.GraphicsFormat format { get; }
```

- `public Colossal.IO.AssetDatabase.TextureAsset textureAsset { get }`  

```csharp
public Colossal.IO.AssetDatabase.TextureAsset textureAsset { get; }
```

- `public Colossal.IO.AssetDatabase.LoadState state { get }`  

```csharp
public Colossal.IO.AssetDatabase.LoadState state { get; }
```


## Constructors

- `public VTTextureAsset()`  

```csharp
public VTTextureAsset();
```


## Methods

- `private <Load>b__31_0(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <Load>b__31_0(System.TimeSpan t);
```

- `private <Save>b__20_0(System.TimeSpan t) : System.Void`  

```csharp
private System.Void <Save>b__20_0(System.TimeSpan t);
```

- `public static ApplyMipBias(System.Int32 width, System.Int32 height, System.Int32 tileSize, UnityEngine.Experimental.Rendering.GraphicsFormat format, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize& preProcessedTextureSize, System.Int32& mipBias) : System.Int32`  

```csharp
public static System.Int32 ApplyMipBias(System.Int32 width, System.Int32 height, System.Int32 tileSize, UnityEngine.Experimental.Rendering.GraphicsFormat format, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize& preProcessedTextureSize, System.Int32& mipBias);
```

- `public static CalcTotalTextureSize(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, System.Int32 nbTiles, System.Int32 nbTilesInX, System.Int32 nbTilesInY, System.Int32 nbMidMipLevels, System.Int32 highMipDataSize) : System.Int32`  

```csharp
public static System.Int32 CalcTotalTextureSize(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, System.Int32 nbTiles, System.Int32 nbTilesInX, System.Int32 nbTilesInY, System.Int32 nbMidMipLevels, System.Int32 highMipDataSize);
```

- `public static CalculateHighMip(System.Int32& highMipDataIndex, System.Int32& highMipDataSize, System.Int32& nbMidMipLevels, System.Int32 dataLength, System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested) : System.Int32`  

```csharp
public static System.Int32 CalculateHighMip(System.Int32& highMipDataIndex, System.Int32& highMipDataSize, System.Int32& nbMidMipLevels, System.Int32 dataLength, System.Int32 width, System.Int32 height, UnityEngine.Experimental.Rendering.GraphicsFormat format, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested);
```

- `public static CreateDebugTexture2D(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, System.Int32 nbTiles, System.Int32 nbTilesInX, System.Int32 nbTilesInY, System.Int32 width, System.Int32 height, System.Byte[] tilesData, System.Byte[] highMipData, System.Int32 mipMapCount, System.Int32 nbMidMipLevels, UnityEngine.Experimental.Rendering.GraphicsFormat format, UnityEngine.FilterMode filterMode, UnityEngine.TextureWrapMode wrapMode, System.Int32 anisoLevel, System.String name) : UnityEngine.Texture2D`  

```csharp
public static UnityEngine.Texture2D CreateDebugTexture2D(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, System.Int32 nbTiles, System.Int32 nbTilesInX, System.Int32 nbTilesInY, System.Int32 width, System.Int32 height, System.Byte[] tilesData, System.Byte[] highMipData, System.Int32 mipMapCount, System.Int32 nbMidMipLevels, UnityEngine.Experimental.Rendering.GraphicsFormat format, UnityEngine.FilterMode filterMode, UnityEngine.TextureWrapMode wrapMode, System.Int32 anisoLevel, System.String name);
```

- `public static FillDebugTextureOneTile(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, System.Int32 nbTilesInX, System.Int32 nbTilesInY, System.Int32 width, Unity.Collections.NativeArray<System.Byte> srcData, Unity.Collections.NativeArray<System.Byte> dstData, System.Int32 srcOffsetInBlocks = 0, System.Int32 dstOffsetInBlocks = 0) : System.Void`  

```csharp
public static System.Void FillDebugTextureOneTile(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, System.Int32 nbTilesInX, System.Int32 nbTilesInY, System.Int32 width, Unity.Collections.NativeArray<System.Byte> srcData, Unity.Collections.NativeArray<System.Byte> dstData, System.Int32 srcOffsetInBlocks, System.Int32 dstOffsetInBlocks);
```

- `private GetCompressedTileOffsetAndSize(System.Int64 fileOffset, System.Collections.Generic.IList<System.Int32> tileOffset, System.Int32 tileIndex, System.Int64& offset, System.Int32& size) : System.Void`  

```csharp
private System.Void GetCompressedTileOffsetAndSize(System.Int64 fileOffset, System.Collections.Generic.IList<System.Int32> tileOffset, System.Int32 tileIndex, System.Int64& offset, System.Int32& size);
```

- `public Load() : UnityEngine.Texture`  

```csharp
public UnityEngine.Texture Load();
```

- `public Load(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize supportedTextureSize, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, Colossal.IO.AssetDatabase.TexturesAsyncLoader texturesAsyncLoader, System.Int32 layerIndex, System.Int32 nbPreProcessedMidMipLevels) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize Load(Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize supportedTextureSize, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem textureStreamingSystem, Colossal.IO.AssetDatabase.TexturesAsyncLoader texturesAsyncLoader, System.Int32 layerIndex, System.Int32 nbPreProcessedMidMipLevels);
```

- `public LoadHeader() : System.Void`  

```csharp
public System.Void LoadHeader();
```

- `public static PreProcessData(Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 originalWidth, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize preprocessedTextureSize, System.Int32 maxPreprocessedLevel, Unity.Collections.NativeSlice<System.Byte> inputSlice, Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& preProcessedData, Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& preProcessedDataPart2, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, System.Int32 tileSize) : System.UInt16`  

```csharp
public static System.UInt16 PreProcessData(Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 originalWidth, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize preprocessedTextureSize, System.Int32 maxPreprocessedLevel, Unity.Collections.NativeSlice<System.Byte> inputSlice, Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& preProcessedData, Unity.Collections.NativeArray`1[[System.Byte, System.Private.CoreLib, Version=8.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]& preProcessedDataPart2, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, System.Int32 tileSize);
```

- `private ReadHeader(System.IO.BinaryReader sr) : System.UInt16`  

```csharp
private System.UInt16 ReadHeader(System.IO.BinaryReader sr);
```

- `public Save(System.Int32 mipBias, Colossal.IO.AssetDatabase.TextureAsset texture, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig) : System.Void`  

```csharp
public System.Void Save(System.Int32 mipBias, Colossal.IO.AssetDatabase.TextureAsset texture, System.Int32 tileSize, System.Int32 nbMidMipLevelsRequested, Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig);
```

- `public virtual Unload(System.Boolean force = False) : System.Void`  

```csharp
public virtual System.Void Unload(System.Boolean force);
```


## Nested types

- `Colossal.IO.AssetDatabase.VTTextureAsset+<>c`  

