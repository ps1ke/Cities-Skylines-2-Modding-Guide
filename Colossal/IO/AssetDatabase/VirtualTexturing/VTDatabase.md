# Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class VTDatabase
{
    private readonly Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig m_VirtualTexturingConfig;
    private readonly System.Int32 m_NbMidSizeMipLevelsForPacking;
    private readonly Colossal.IO.AssetDatabase.VirtualTexturing.IVTStackCreator m_StackCreator;
    private readonly System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+HighMipCaching> m_RegisteredTextures;
    private readonly System.Collections.Generic.Dictionary<Colossal.Hash128, Unity.Collections.NativeArray<System.Byte>> m_TexturesData;
    private readonly System.Collections.Generic.HashSet<Colossal.Hash128> m_LoadingData;
    private readonly System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTTextureInfo> m_VTTexturePaths;
    private readonly Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo[][] m_LayerInfos;
    private System.Collections.Generic.List<System.Collections.Generic.List<System.Int32>> m_GlobalStackIndices;
    private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.Atlas> m_Atlas;
    private System.Collections.Generic.List<System.Int32> m_ConfigStackIndices;
    private System.Collections.Generic.List<System.Collections.Generic.Dictionary<System.Int32, Colossal.Hash128>[]> m_TextureGuidsPerIndex;
    private System.Collections.Generic.List<System.Collections.Generic.Dictionary<System.Int32, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo>> m_VTSurfaceTileInfo;
    private System.Int32 m_DataSize;
    private System.Int32 m_BC7SrgbEntriesCount;
    private System.Int32 m_BC7UNormEntriesCount;
    private System.Int32 m_OtherEntriesCount;
    private System.Int32 m_TilesFilledFromCPUCacheCount;
    private System.Int32 m_PerMaterialAsyncTileReadCount;
    private System.Int32 m_PerTextureAsyncTileReadCount;
    private System.Collections.Generic.List<System.Int32> m_ReservedTextureIndices;

    public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.VirtualTexturing.Atlas> atlas { get; }
    public System.Collections.Generic.IReadOnlyList<System.Collections.Generic.IReadOnlyDictionary<System.Int32, Colossal.Hash128>[]> textureGuidsPerIndex { get; }
    public System.Collections.Generic.IReadOnlyList<System.Collections.Generic.IReadOnlyDictionary<System.Int32, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo>> VTSurfaceTileInfo { get; }
    public System.Int32 tilesFilledFromCPUCacheCount { get; }
    public System.Int32 perMaterialAsyncTileReadCount { get; }
    public System.Int32 perTextureAsyncTileReadCount { get; }
    public System.Int32 bc7SrgbEntriesCount { get; }
    public System.Int32 bc7UNormEntriesCount { get; }
    public System.Int32 otherEntriesCount { get; }
    public System.Int32 dataSize { get; }
    public System.Int32 atlasDataSize { get; }

    public VTDatabase(Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 nbMidSizeMipLevelsForPacking, Colossal.IO.AssetDatabase.VirtualTexturing.IVTStackCreator stackCreator);

    private System.Int32 AddStack(System.Int32 stackConfigIndex);
    public System.Void AddTextureToCache(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 textureIndex, System.Int32 textureWidth, System.Int32 textureHeight, Colossal.Hash128 guid, System.Int32 nbPreProcessedMidMipLevels);
    private System.Void ComputeNbEntriesPerFormat(System.Int32 stackConfigIndex, System.Int32 layerIndex);
    public System.Void CopyTextureDataFromRequest(System.Int32 stackGlobalIndex, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, System.Int32 layerIndex, System.Int32 textureIndex, System.Int32 paddingSize, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo);
    public System.Void CopyTextureDataFromRequest(System.Int32 stackGlobalIndex, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo vtSurfaceInfo, System.Int32 textureIndex, System.Int32 tileSize, System.Int32 paddingSize, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest);
    public System.Void Destroy();
    public System.Void DoneLoading(Colossal.Hash128 textureGuid);
    public System.Boolean FillFromCache(System.Int32 stackGlobalIndex, System.Int32 layerIndex, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req);
    public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedRect GetAtlassedRect(System.Int32 stackGlobalIndex, System.Int32 index);
    public System.Void GetCompressedTileOffsetAndSize(System.Int64 fileOffset, System.Collections.Generic.List<System.Int32> tileOffset, System.Int32 tileIndex, System.Int64& offset, System.Int32& size);
    public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo GetLayerInfoPerConfigIndex(System.Int32 stackConfigIndex, System.Int32 layerIndex);
    public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo GetLayerInfoPerGlobalIndex(System.Int32 stackGlobalIndex, System.Int32 layerIndex);
    public System.Int32 GetNbReservedBlocks(System.Int32 stackGlobalIndex);
    public UnityEngine.Rect GetRect(System.Int32 stackGlobalIndex, System.Int32 index);
    public System.Int32 GetStackConfigIndex(System.Int32 stackGlobalIndex);
    public Unity.Collections.NativeArray<System.Byte> GetTextureData(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 atlassedIndex);
    public Unity.Collections.NativeArray<System.Byte> GetTextureData(Colossal.Hash128 guid);
    public System.Int32 GetTextureIndex(System.Int32 stackGlobalIndex, System.Int32 xOffset, System.Int32 yOffset, System.Int32 width, System.Int32 height);
    public Colossal.IO.AssetDatabase.VirtualTexturing.VTTextureParamBlock GetTextureParamBlock(Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo vtAtlassingInfo);
    public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize GetTextureSize(System.Int32 stackGlobalIndex, System.Int32 index);
    public System.Int32 GetTotalNbBlocks(System.Int32 stackGlobalIndex);
    public Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo GetVTSurfaceTileInfo(System.Int32 stackGlobalIndex, System.Int32 atlassedIndex);
    internal Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTTextureInfo GetVTTextureInfo(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 textureIndex);
    public System.Boolean IsDoneLoading(Colossal.Hash128 textureGuid);
    public System.Boolean IsVTTextureData(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 textureIndex);
    public System.Void RegisterPerMaterialTileInfo(System.Int32 stackGlobalIndex, System.Int32 atlassedIndex, System.String path, System.Int64 tilesDataOffset, System.Int32[] dataOffsets, System.Int32[] dataSizes, System.Int32 nbTiles, System.Collections.Generic.List<System.Int32> compressedTileOffsets, System.Int32 width, System.Int32 height);
    public System.Boolean RegisterTextureData(Colossal.Hash128 textureGuid, System.Int32 dataSize);
    public System.Boolean RegisterVTTextureData(Colossal.Hash128 textureGuid, System.String fullPath, System.Int64 fileOffset, System.Int64 vtTextureDataIndex, System.Int32 dataSize, System.Collections.Generic.List<System.Int32> tileOffsets, System.Int32 width, System.Int32 height);
    public System.Collections.Generic.List<System.Int32> ReserveMultipleTextureRect(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height, System.Int32 qty, System.Int32 alignment, System.Int32& stackGlobalIndex);
    public Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo ReserveTextureRect(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height);
}
```


## Fields

- `private readonly Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig m_VirtualTexturingConfig`  

```csharp
private readonly Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig m_VirtualTexturingConfig;
```

- `private readonly System.Int32 m_NbMidSizeMipLevelsForPacking`  

```csharp
private readonly System.Int32 m_NbMidSizeMipLevelsForPacking;
```

- `private readonly Colossal.IO.AssetDatabase.VirtualTexturing.IVTStackCreator m_StackCreator`  

```csharp
private readonly Colossal.IO.AssetDatabase.VirtualTexturing.IVTStackCreator m_StackCreator;
```

- `private readonly System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+HighMipCaching> m_RegisteredTextures`  

```csharp
private readonly System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+HighMipCaching> m_RegisteredTextures;
```

- `private readonly System.Collections.Generic.Dictionary<Colossal.Hash128, Unity.Collections.NativeArray<System.Byte>> m_TexturesData`  

```csharp
private readonly System.Collections.Generic.Dictionary<Colossal.Hash128, Unity.Collections.NativeArray<System.Byte>> m_TexturesData;
```

- `private readonly System.Collections.Generic.HashSet<Colossal.Hash128> m_LoadingData`  

```csharp
private readonly System.Collections.Generic.HashSet<Colossal.Hash128> m_LoadingData;
```

- `private readonly System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTTextureInfo> m_VTTexturePaths`  

```csharp
private readonly System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTTextureInfo> m_VTTexturePaths;
```

- `private readonly Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo[][] m_LayerInfos`  

```csharp
private readonly Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo[][] m_LayerInfos;
```

- `private System.Collections.Generic.List<System.Collections.Generic.List<System.Int32>> m_GlobalStackIndices`  

```csharp
private System.Collections.Generic.List<System.Collections.Generic.List<System.Int32>> m_GlobalStackIndices;
```

- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.Atlas> m_Atlas`  

```csharp
private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.Atlas> m_Atlas;
```

- `private System.Collections.Generic.List<System.Int32> m_ConfigStackIndices`  

```csharp
private System.Collections.Generic.List<System.Int32> m_ConfigStackIndices;
```

- `private System.Collections.Generic.List<System.Collections.Generic.Dictionary<System.Int32, Colossal.Hash128>[]> m_TextureGuidsPerIndex`  

```csharp
private System.Collections.Generic.List<System.Collections.Generic.Dictionary<System.Int32, Colossal.Hash128>[]> m_TextureGuidsPerIndex;
```

- `private System.Collections.Generic.List<System.Collections.Generic.Dictionary<System.Int32, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo>> m_VTSurfaceTileInfo`  

```csharp
private System.Collections.Generic.List<System.Collections.Generic.Dictionary<System.Int32, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo>> m_VTSurfaceTileInfo;
```

- `private System.Int32 m_DataSize`  

```csharp
private System.Int32 m_DataSize;
```

- `private System.Int32 m_BC7SrgbEntriesCount`  

```csharp
private System.Int32 m_BC7SrgbEntriesCount;
```

- `private System.Int32 m_BC7UNormEntriesCount`  

```csharp
private System.Int32 m_BC7UNormEntriesCount;
```

- `private System.Int32 m_OtherEntriesCount`  

```csharp
private System.Int32 m_OtherEntriesCount;
```

- `private System.Int32 m_TilesFilledFromCPUCacheCount`  

```csharp
private System.Int32 m_TilesFilledFromCPUCacheCount;
```

- `private System.Int32 m_PerMaterialAsyncTileReadCount`  

```csharp
private System.Int32 m_PerMaterialAsyncTileReadCount;
```

- `private System.Int32 m_PerTextureAsyncTileReadCount`  

```csharp
private System.Int32 m_PerTextureAsyncTileReadCount;
```

- `private System.Collections.Generic.List<System.Int32> m_ReservedTextureIndices`  

```csharp
private System.Collections.Generic.List<System.Int32> m_ReservedTextureIndices;
```


## Properties

- `public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.VirtualTexturing.Atlas> atlas { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.VirtualTexturing.Atlas> atlas { get; }
```

- `public System.Collections.Generic.IReadOnlyList<System.Collections.Generic.IReadOnlyDictionary<System.Int32, Colossal.Hash128>[]> textureGuidsPerIndex { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<System.Collections.Generic.IReadOnlyDictionary<System.Int32, Colossal.Hash128>[]> textureGuidsPerIndex { get; }
```

- `public System.Collections.Generic.IReadOnlyList<System.Collections.Generic.IReadOnlyDictionary<System.Int32, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo>> VTSurfaceTileInfo { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<System.Collections.Generic.IReadOnlyDictionary<System.Int32, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo>> VTSurfaceTileInfo { get; }
```

- `public System.Int32 tilesFilledFromCPUCacheCount { get }`  

```csharp
public System.Int32 tilesFilledFromCPUCacheCount { get; }
```

- `public System.Int32 perMaterialAsyncTileReadCount { get }`  

```csharp
public System.Int32 perMaterialAsyncTileReadCount { get; }
```

- `public System.Int32 perTextureAsyncTileReadCount { get }`  

```csharp
public System.Int32 perTextureAsyncTileReadCount { get; }
```

- `public System.Int32 bc7SrgbEntriesCount { get }`  

```csharp
public System.Int32 bc7SrgbEntriesCount { get; }
```

- `public System.Int32 bc7UNormEntriesCount { get }`  

```csharp
public System.Int32 bc7UNormEntriesCount { get; }
```

- `public System.Int32 otherEntriesCount { get }`  

```csharp
public System.Int32 otherEntriesCount { get; }
```

- `public System.Int32 dataSize { get }`  

```csharp
public System.Int32 dataSize { get; }
```

- `public System.Int32 atlasDataSize { get }`  

```csharp
public System.Int32 atlasDataSize { get; }
```


## Constructors

- `public VTDatabase(Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 nbMidSizeMipLevelsForPacking, Colossal.IO.AssetDatabase.VirtualTexturing.IVTStackCreator stackCreator = null)`  

```csharp
public VTDatabase(Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 nbMidSizeMipLevelsForPacking, Colossal.IO.AssetDatabase.VirtualTexturing.IVTStackCreator stackCreator);
```


## Methods

- `private AddStack(System.Int32 stackConfigIndex) : System.Int32`  

```csharp
private System.Int32 AddStack(System.Int32 stackConfigIndex);
```

- `public AddTextureToCache(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 textureIndex, System.Int32 textureWidth, System.Int32 textureHeight, Colossal.Hash128 guid, System.Int32 nbPreProcessedMidMipLevels) : System.Void`  

```csharp
public System.Void AddTextureToCache(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 textureIndex, System.Int32 textureWidth, System.Int32 textureHeight, Colossal.Hash128 guid, System.Int32 nbPreProcessedMidMipLevels);
```

- `private ComputeNbEntriesPerFormat(System.Int32 stackConfigIndex, System.Int32 layerIndex) : System.Void`  

```csharp
private System.Void ComputeNbEntriesPerFormat(System.Int32 stackConfigIndex, System.Int32 layerIndex);
```

- `public CopyTextureDataFromRequest(System.Int32 stackGlobalIndex, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, System.Int32 layerIndex, System.Int32 textureIndex, System.Int32 paddingSize, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo) : System.Void`  

```csharp
public System.Void CopyTextureDataFromRequest(System.Int32 stackGlobalIndex, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, System.Int32 layerIndex, System.Int32 textureIndex, System.Int32 paddingSize, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo);
```

- `public CopyTextureDataFromRequest(System.Int32 stackGlobalIndex, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo vtSurfaceInfo, System.Int32 textureIndex, System.Int32 tileSize, System.Int32 paddingSize, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest) : System.Void`  

```csharp
public System.Void CopyTextureDataFromRequest(System.Int32 stackGlobalIndex, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo vtSurfaceInfo, System.Int32 textureIndex, System.Int32 tileSize, System.Int32 paddingSize, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest);
```

- `public Destroy() : System.Void`  

```csharp
public System.Void Destroy();
```

- `public DoneLoading(Colossal.Hash128 textureGuid) : System.Void`  

```csharp
public System.Void DoneLoading(Colossal.Hash128 textureGuid);
```

- `public FillFromCache(System.Int32 stackGlobalIndex, System.Int32 layerIndex, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req) : System.Boolean`  

```csharp
public System.Boolean FillFromCache(System.Int32 stackGlobalIndex, System.Int32 layerIndex, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req);
```

- `public GetAtlassedRect(System.Int32 stackGlobalIndex, System.Int32 index) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedRect`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedRect GetAtlassedRect(System.Int32 stackGlobalIndex, System.Int32 index);
```

- `public GetCompressedTileOffsetAndSize(System.Int64 fileOffset, System.Collections.Generic.List<System.Int32> tileOffset, System.Int32 tileIndex, System.Int64& offset, System.Int32& size) : System.Void`  

```csharp
public System.Void GetCompressedTileOffsetAndSize(System.Int64 fileOffset, System.Collections.Generic.List<System.Int32> tileOffset, System.Int32 tileIndex, System.Int64& offset, System.Int32& size);
```

- `public GetLayerInfoPerConfigIndex(System.Int32 stackConfigIndex, System.Int32 layerIndex) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo GetLayerInfoPerConfigIndex(System.Int32 stackConfigIndex, System.Int32 layerIndex);
```

- `public GetLayerInfoPerGlobalIndex(System.Int32 stackGlobalIndex, System.Int32 layerIndex) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo GetLayerInfoPerGlobalIndex(System.Int32 stackGlobalIndex, System.Int32 layerIndex);
```

- `public GetNbReservedBlocks(System.Int32 stackGlobalIndex) : System.Int32`  

```csharp
public System.Int32 GetNbReservedBlocks(System.Int32 stackGlobalIndex);
```

- `public GetRect(System.Int32 stackGlobalIndex, System.Int32 index) : UnityEngine.Rect`  

```csharp
public UnityEngine.Rect GetRect(System.Int32 stackGlobalIndex, System.Int32 index);
```

- `public GetStackConfigIndex(System.Int32 stackGlobalIndex) : System.Int32`  

```csharp
public System.Int32 GetStackConfigIndex(System.Int32 stackGlobalIndex);
```

- `public GetTextureData(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 atlassedIndex) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public Unity.Collections.NativeArray<System.Byte> GetTextureData(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 atlassedIndex);
```

- `public GetTextureData(Colossal.Hash128 guid) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public Unity.Collections.NativeArray<System.Byte> GetTextureData(Colossal.Hash128 guid);
```

- `public GetTextureIndex(System.Int32 stackGlobalIndex, System.Int32 xOffset, System.Int32 yOffset, System.Int32 width, System.Int32 height) : System.Int32`  

```csharp
public System.Int32 GetTextureIndex(System.Int32 stackGlobalIndex, System.Int32 xOffset, System.Int32 yOffset, System.Int32 width, System.Int32 height);
```

- `public GetTextureParamBlock(Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo vtAtlassingInfo) : Colossal.IO.AssetDatabase.VirtualTexturing.VTTextureParamBlock`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.VTTextureParamBlock GetTextureParamBlock(Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo vtAtlassingInfo);
```

- `public GetTextureSize(System.Int32 stackGlobalIndex, System.Int32 index) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize GetTextureSize(System.Int32 stackGlobalIndex, System.Int32 index);
```

- `public GetTotalNbBlocks(System.Int32 stackGlobalIndex) : System.Int32`  

```csharp
public System.Int32 GetTotalNbBlocks(System.Int32 stackGlobalIndex);
```

- `public GetVTSurfaceTileInfo(System.Int32 stackGlobalIndex, System.Int32 atlassedIndex) : Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo GetVTSurfaceTileInfo(System.Int32 stackGlobalIndex, System.Int32 atlassedIndex);
```

- `internal GetVTTextureInfo(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 textureIndex) : Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTTextureInfo`  

```csharp
internal Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTTextureInfo GetVTTextureInfo(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 textureIndex);
```

- `public IsDoneLoading(Colossal.Hash128 textureGuid) : System.Boolean`  

```csharp
public System.Boolean IsDoneLoading(Colossal.Hash128 textureGuid);
```

- `public IsVTTextureData(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 textureIndex) : System.Boolean`  

```csharp
public System.Boolean IsVTTextureData(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 textureIndex);
```

- `public RegisterPerMaterialTileInfo(System.Int32 stackGlobalIndex, System.Int32 atlassedIndex, System.String path, System.Int64 tilesDataOffset, System.Int32[] dataOffsets, System.Int32[] dataSizes, System.Int32 nbTiles, System.Collections.Generic.List<System.Int32> compressedTileOffsets, System.Int32 width, System.Int32 height) : System.Void`  

```csharp
public System.Void RegisterPerMaterialTileInfo(System.Int32 stackGlobalIndex, System.Int32 atlassedIndex, System.String path, System.Int64 tilesDataOffset, System.Int32[] dataOffsets, System.Int32[] dataSizes, System.Int32 nbTiles, System.Collections.Generic.List<System.Int32> compressedTileOffsets, System.Int32 width, System.Int32 height);
```

- `public RegisterTextureData(Colossal.Hash128 textureGuid, System.Int32 dataSize) : System.Boolean`  

```csharp
public System.Boolean RegisterTextureData(Colossal.Hash128 textureGuid, System.Int32 dataSize);
```

- `public RegisterVTTextureData(Colossal.Hash128 textureGuid, System.String fullPath, System.Int64 fileOffset, System.Int64 vtTextureDataIndex, System.Int32 dataSize, System.Collections.Generic.List<System.Int32> tileOffsets, System.Int32 width, System.Int32 height) : System.Boolean`  

```csharp
public System.Boolean RegisterVTTextureData(Colossal.Hash128 textureGuid, System.String fullPath, System.Int64 fileOffset, System.Int64 vtTextureDataIndex, System.Int32 dataSize, System.Collections.Generic.List<System.Int32> tileOffsets, System.Int32 width, System.Int32 height);
```

- `public ReserveMultipleTextureRect(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height, System.Int32 qty, System.Int32 alignment, System.Int32& stackGlobalIndex) : System.Collections.Generic.List<System.Int32>`  

```csharp
public System.Collections.Generic.List<System.Int32> ReserveMultipleTextureRect(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height, System.Int32 qty, System.Int32 alignment, System.Int32& stackGlobalIndex);
```

- `public ReserveTextureRect(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height) : Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo ReserveTextureRect(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height);
```


## Nested types

- `Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+PathNotFoundException`  
- `Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTTextureInfo`  
- `Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+HighMipCaching`  
- `Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo`  

