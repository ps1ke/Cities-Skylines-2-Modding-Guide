# Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsGrouper

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class AtlasMaterialsGrouper
{
    private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasCategory>[] m_CategoriesPerStack;
    private System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo>[] m_RegisteredTextures;
    private System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.Dictionary<System.Int32, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry>> m_PreprocessedMidMipTilesInfo;
    private System.Collections.Generic.List<Unity.Collections.NativeArray<System.Byte>> m_PreprocessedTiles;
    private System.Collections.Generic.HashSet<Colossal.Hash128> m_RegisteredMaterials;
    private System.Int32 m_TileSize;
    private System.Int32 m_MaxGroupSize;
    private System.Int32 m_MidMipLevelsCount;
    private System.Int32 m_NbEntries;
    private System.Int32 m_NbGroups;
    private System.Boolean m_Initialized;
    private System.Int64 m_PreProcessedDataStart;
    private readonly Colossal.IO.AssetDatabase.MidMipCacheAsset m_MidMipCacheAsset;
    private readonly System.String m_MidMipPath;
    private readonly System.Int64 m_MidMipFileOffset;
    private System.Int32 m_NbPreProcessedTilesInFile;
    private System.Int32 m_AsyncTextureReadCount;
    private static readonly Colossal.Logging.ILog log;

    public System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasCategory>[] categoriesPerStack { get; }
    public System.Int32 preProcessedTilesInFileCount { get; }
    public System.Int32 categoriesPerStackCount { get; }
    public System.Int32 maxGroupSize { get; }
    public System.Int32 midMipLevelsCount { get; }
    public System.Boolean IsInitialized { get; }
    public System.Int32 asyncTextureReadCount { get; }
    public Colossal.IO.AssetDatabase.MidMipCacheAsset asset { get; }

    public AtlasMaterialsGrouper(System.Int32 nbConfigStacks, System.Int32 tileSize, System.Int32 midMipLevelsCount);
    public AtlasMaterialsGrouper(System.Int32 tileSize, System.Int32 nbMidMipLevels, Colossal.IO.AssetDatabase.MidMipCacheAsset asset);
    public AtlasMaterialsGrouper(System.Int32 tileSize, System.Int32 nbMidMipLevels);

    public System.Void Add(System.Int32 stackConfigIndex, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize unbiasedStackTextureSize, System.Int32 multiStackLayersMask, Colossal.IO.AssetDatabase.SurfaceAsset surface, System.Int64[] textureHash, System.Int32 mipBiasOverride);
    public System.Void Dispose();
    public UnityEngine.Texture2D FillData(System.Int32 tileIndex, System.Boolean isTrilinear);
    public System.Void FillRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry objectEntry, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest);
    private System.Void FillTestData(System.Int32 tileIndex, System.Boolean isTrilinear, System.Int32 midMipLevel, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedCoords internalCoords, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, Unity.Collections.NativeArray<System.Byte> dstData, System.Int32 dstOffsetInBlocks);
    public System.Void FillTileData(System.Int32 tileIndex, System.Int32 midMipLevel, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedCoords internalCoords, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, Unity.Collections.NativeArray<System.Byte> dstData, System.Int32 dstOffsetInBlocks);
    public Colossal.IO.AssetDatabase.VirtualTexturing.AtlasEntry FindAtlasEntry(System.Int32 stackConfigIndex, Colossal.Hash128 materialGuid);
    public static System.String GetAssetName(System.Int32 tileSize, System.Int32 nbMidMipLevels);
    public System.Void GroupEntries(Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Collections.Generic.Dictionary<Colossal.Hash128, Unity.Collections.NativeArray<System.Byte>> midMipDataDict, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]>[] materialTextures);
    public System.Boolean IsDuplicate(Colossal.Hash128 materialGuid);
    public System.Void Read(System.IO.BinaryReader br, System.Int32 tileSize, System.Int32 nbMidMipLevels);
    public System.Void ResolveDuplicates(System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]>[] materialTextures, System.Int32 stackCount);
    public System.Void Write(System.IO.BinaryWriter bw);
}
```


## Fields

- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasCategory>[] m_CategoriesPerStack`  

```csharp
private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasCategory>[] m_CategoriesPerStack;
```

- `private System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo>[] m_RegisteredTextures`  

```csharp
private System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo>[] m_RegisteredTextures;
```

- `private System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.Dictionary<System.Int32, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry>> m_PreprocessedMidMipTilesInfo`  

```csharp
private System.Collections.Generic.Dictionary<System.Int32, System.Collections.Generic.Dictionary<System.Int32, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry>> m_PreprocessedMidMipTilesInfo;
```

- `private System.Collections.Generic.List<Unity.Collections.NativeArray<System.Byte>> m_PreprocessedTiles`  

```csharp
private System.Collections.Generic.List<Unity.Collections.NativeArray<System.Byte>> m_PreprocessedTiles;
```

- `private System.Collections.Generic.HashSet<Colossal.Hash128> m_RegisteredMaterials`  

```csharp
private System.Collections.Generic.HashSet<Colossal.Hash128> m_RegisteredMaterials;
```

- `private System.Int32 m_TileSize`  

```csharp
private System.Int32 m_TileSize;
```

- `private System.Int32 m_MaxGroupSize`  

```csharp
private System.Int32 m_MaxGroupSize;
```

- `private System.Int32 m_MidMipLevelsCount`  

```csharp
private System.Int32 m_MidMipLevelsCount;
```

- `private System.Int32 m_NbEntries`  

```csharp
private System.Int32 m_NbEntries;
```

- `private System.Int32 m_NbGroups`  

```csharp
private System.Int32 m_NbGroups;
```

- `private System.Boolean m_Initialized`  

```csharp
private System.Boolean m_Initialized;
```

- `private System.Int64 m_PreProcessedDataStart`  

```csharp
private System.Int64 m_PreProcessedDataStart;
```

- `private readonly Colossal.IO.AssetDatabase.MidMipCacheAsset m_MidMipCacheAsset`  

```csharp
private readonly Colossal.IO.AssetDatabase.MidMipCacheAsset m_MidMipCacheAsset;
```

- `private readonly System.String m_MidMipPath`  

```csharp
private readonly System.String m_MidMipPath;
```

- `private readonly System.Int64 m_MidMipFileOffset`  

```csharp
private readonly System.Int64 m_MidMipFileOffset;
```

- `private System.Int32 m_NbPreProcessedTilesInFile`  

```csharp
private System.Int32 m_NbPreProcessedTilesInFile;
```

- `private System.Int32 m_AsyncTextureReadCount`  

```csharp
private System.Int32 m_AsyncTextureReadCount;
```

- `private static readonly Colossal.Logging.ILog log`  

```csharp
private static readonly Colossal.Logging.ILog log;
```


## Properties

- `public System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasCategory>[] categoriesPerStack { get }`  

```csharp
public System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.AtlasCategory>[] categoriesPerStack { get; }
```

- `public System.Int32 preProcessedTilesInFileCount { get }`  

```csharp
public System.Int32 preProcessedTilesInFileCount { get; }
```

- `public System.Int32 categoriesPerStackCount { get }`  

```csharp
public System.Int32 categoriesPerStackCount { get; }
```

- `public System.Int32 maxGroupSize { get }`  

```csharp
public System.Int32 maxGroupSize { get; }
```

- `public System.Int32 midMipLevelsCount { get }`  

```csharp
public System.Int32 midMipLevelsCount { get; }
```

- `public System.Boolean IsInitialized { get }`  

```csharp
public System.Boolean IsInitialized { get; }
```

- `public System.Int32 asyncTextureReadCount { get }`  

```csharp
public System.Int32 asyncTextureReadCount { get; }
```

- `public Colossal.IO.AssetDatabase.MidMipCacheAsset asset { get }`  

```csharp
public Colossal.IO.AssetDatabase.MidMipCacheAsset asset { get; }
```


## Constructors

- `public AtlasMaterialsGrouper(System.Int32 nbConfigStacks, System.Int32 tileSize, System.Int32 midMipLevelsCount)`  

```csharp
public AtlasMaterialsGrouper(System.Int32 nbConfigStacks, System.Int32 tileSize, System.Int32 midMipLevelsCount);
```

- `public AtlasMaterialsGrouper(System.Int32 tileSize, System.Int32 nbMidMipLevels, Colossal.IO.AssetDatabase.MidMipCacheAsset asset)`  

```csharp
public AtlasMaterialsGrouper(System.Int32 tileSize, System.Int32 nbMidMipLevels, Colossal.IO.AssetDatabase.MidMipCacheAsset asset);
```

- `public AtlasMaterialsGrouper(System.Int32 tileSize, System.Int32 nbMidMipLevels)`  

```csharp
public AtlasMaterialsGrouper(System.Int32 tileSize, System.Int32 nbMidMipLevels);
```


## Methods

- `public Add(System.Int32 stackConfigIndex, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize unbiasedStackTextureSize, System.Int32 multiStackLayersMask, Colossal.IO.AssetDatabase.SurfaceAsset surface, System.Int64[] textureHash, System.Int32 mipBiasOverride) : System.Void`  

```csharp
public System.Void Add(System.Int32 stackConfigIndex, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize unbiasedStackTextureSize, System.Int32 multiStackLayersMask, Colossal.IO.AssetDatabase.SurfaceAsset surface, System.Int64[] textureHash, System.Int32 mipBiasOverride);
```

- `public Dispose() : System.Void`  

```csharp
public System.Void Dispose();
```

- `public FillData(System.Int32 tileIndex, System.Boolean isTrilinear) : UnityEngine.Texture2D`  

```csharp
public UnityEngine.Texture2D FillData(System.Int32 tileIndex, System.Boolean isTrilinear);
```

- `public FillRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry objectEntry, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest) : System.Void`  

```csharp
public System.Void FillRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry objectEntry, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest);
```

- `private FillTestData(System.Int32 tileIndex, System.Boolean isTrilinear, System.Int32 midMipLevel, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedCoords internalCoords, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, Unity.Collections.NativeArray<System.Byte> dstData, System.Int32 dstOffsetInBlocks) : System.Void`  

```csharp
private System.Void FillTestData(System.Int32 tileIndex, System.Boolean isTrilinear, System.Int32 midMipLevel, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedCoords internalCoords, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, Unity.Collections.NativeArray<System.Byte> dstData, System.Int32 dstOffsetInBlocks);
```

- `public FillTileData(System.Int32 tileIndex, System.Int32 midMipLevel, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedCoords internalCoords, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, Unity.Collections.NativeArray<System.Byte> dstData, System.Int32 dstOffsetInBlocks) : System.Void`  

```csharp
public System.Void FillTileData(System.Int32 tileIndex, System.Int32 midMipLevel, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedCoords internalCoords, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo, Unity.Collections.NativeArray<System.Byte> dstData, System.Int32 dstOffsetInBlocks);
```

- `public FindAtlasEntry(System.Int32 stackConfigIndex, Colossal.Hash128 materialGuid) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlasEntry`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.AtlasEntry FindAtlasEntry(System.Int32 stackConfigIndex, Colossal.Hash128 materialGuid);
```

- `public static GetAssetName(System.Int32 tileSize, System.Int32 nbMidMipLevels) : System.String`  

```csharp
public static System.String GetAssetName(System.Int32 tileSize, System.Int32 nbMidMipLevels);
```

- `public GroupEntries(Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Collections.Generic.Dictionary<Colossal.Hash128, Unity.Collections.NativeArray<System.Byte>> midMipDataDict, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]>[] materialTextures) : System.Void`  

```csharp
public System.Void GroupEntries(Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Collections.Generic.Dictionary<Colossal.Hash128, Unity.Collections.NativeArray<System.Byte>> midMipDataDict, System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]>[] materialTextures);
```

- `public IsDuplicate(Colossal.Hash128 materialGuid) : System.Boolean`  

```csharp
public System.Boolean IsDuplicate(Colossal.Hash128 materialGuid);
```

- `public Read(System.IO.BinaryReader br, System.Int32 tileSize, System.Int32 nbMidMipLevels) : System.Void`  

```csharp
public System.Void Read(System.IO.BinaryReader br, System.Int32 tileSize, System.Int32 nbMidMipLevels);
```

- `public ResolveDuplicates(System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]>[] materialTextures, System.Int32 stackCount) : System.Void`  

```csharp
public System.Void ResolveDuplicates(System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.Hash128[]>[] materialTextures, System.Int32 stackCount);
```

- `public Write(System.IO.BinaryWriter bw) : System.Void`  

```csharp
public System.Void Write(System.IO.BinaryWriter bw);
```


## Nested types

- `Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsGrouper+<>c__DisplayClass36_0`  

