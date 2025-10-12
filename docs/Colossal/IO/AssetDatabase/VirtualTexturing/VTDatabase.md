# Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private readonly Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig m_VirtualTexturingConfig`  
- `private readonly System.Int32 m_NbMidSizeMipLevelsForPacking`  
- `private readonly Colossal.IO.AssetDatabase.VirtualTexturing.IVTStackCreator m_StackCreator`  
- `private readonly System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+HighMipCaching> m_RegisteredTextures`  
- `private readonly System.Collections.Generic.Dictionary<Colossal.Hash128, Unity.Collections.NativeArray<System.Byte>> m_TexturesData`  
- `private readonly System.Collections.Generic.HashSet<Colossal.Hash128> m_LoadingData`  
- `private readonly System.Collections.Generic.Dictionary<Colossal.Hash128, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTTextureInfo> m_VTTexturePaths`  
- `private readonly Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo[][] m_LayerInfos`  
- `private System.Collections.Generic.List<System.Collections.Generic.List<System.Int32>> m_GlobalStackIndices`  
- `private System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.Atlas> m_Atlas`  
- `private System.Collections.Generic.List<System.Int32> m_ConfigStackIndices`  
- `private System.Collections.Generic.List<System.Collections.Generic.Dictionary<System.Int32, Colossal.Hash128>[]> m_TextureGuidsPerIndex`  
- `private System.Collections.Generic.List<System.Collections.Generic.Dictionary<System.Int32, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo>> m_VTSurfaceTileInfo`  
- `private System.Int32 m_DataSize`  
- `private System.Int32 m_BC7SrgbEntriesCount`  
- `private System.Int32 m_BC7UNormEntriesCount`  
- `private System.Int32 m_OtherEntriesCount`  
- `private System.Int32 m_TilesFilledFromCPUCacheCount`  
- `private System.Int32 m_PerMaterialAsyncTileReadCount`  
- `private System.Int32 m_PerTextureAsyncTileReadCount`  
- `private System.Collections.Generic.List<System.Int32> m_ReservedTextureIndices`  

## Properties

- `public System.Collections.Generic.IReadOnlyList<Colossal.IO.AssetDatabase.VirtualTexturing.Atlas> atlas { get }`  
- `public System.Collections.Generic.IReadOnlyList<System.Collections.Generic.IReadOnlyDictionary<System.Int32, Colossal.Hash128>[]> textureGuidsPerIndex { get }`  
- `public System.Collections.Generic.IReadOnlyList<System.Collections.Generic.IReadOnlyDictionary<System.Int32, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo>> VTSurfaceTileInfo { get }`  
- `public System.Int32 tilesFilledFromCPUCacheCount { get }`  
- `public System.Int32 perMaterialAsyncTileReadCount { get }`  
- `public System.Int32 perTextureAsyncTileReadCount { get }`  
- `public System.Int32 bc7SrgbEntriesCount { get }`  
- `public System.Int32 bc7UNormEntriesCount { get }`  
- `public System.Int32 otherEntriesCount { get }`  
- `public System.Int32 dataSize { get }`  
- `public System.Int32 atlasDataSize { get }`  

## Constructors

- `public VTDatabase(Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig, System.Int32 nbMidSizeMipLevelsForPacking, Colossal.IO.AssetDatabase.VirtualTexturing.IVTStackCreator stackCreator = null)`  

## Methods

- `private AddStack(System.Int32 stackConfigIndex) : System.Int32`  
- `public AddTextureToCache(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 textureIndex, System.Int32 textureWidth, System.Int32 textureHeight, Colossal.Hash128 guid, System.Int32 nbPreProcessedMidMipLevels) : System.Void`  
- `private ComputeNbEntriesPerFormat(System.Int32 stackConfigIndex, System.Int32 layerIndex) : System.Void`  
- `public CopyTextureDataFromRequest(System.Int32 stackGlobalIndex, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, System.Int32 layerIndex, System.Int32 textureIndex, System.Int32 paddingSize, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo layerInfo) : System.Void`  
- `public CopyTextureDataFromRequest(System.Int32 stackGlobalIndex, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo vtSurfaceInfo, System.Int32 textureIndex, System.Int32 tileSize, System.Int32 paddingSize, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest) : System.Void`  
- `public Destroy() : System.Void`  
- `public DoneLoading(Colossal.Hash128 textureGuid) : System.Void`  
- `public FillFromCache(System.Int32 stackGlobalIndex, System.Int32 layerIndex, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req) : System.Boolean`  
- `public GetAtlassedRect(System.Int32 stackGlobalIndex, System.Int32 index) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedRect`  
- `public GetCompressedTileOffsetAndSize(System.Int64 fileOffset, System.Collections.Generic.List<System.Int32> tileOffset, System.Int32 tileIndex, System.Int64& offset, System.Int32& size) : System.Void`  
- `public GetLayerInfoPerConfigIndex(System.Int32 stackConfigIndex, System.Int32 layerIndex) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo`  
- `public GetLayerInfoPerGlobalIndex(System.Int32 stackGlobalIndex, System.Int32 layerIndex) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassingUtils+LayerInfo`  
- `public GetNbReservedBlocks(System.Int32 stackGlobalIndex) : System.Int32`  
- `public GetRect(System.Int32 stackGlobalIndex, System.Int32 index) : UnityEngine.Rect`  
- `public GetStackConfigIndex(System.Int32 stackGlobalIndex) : System.Int32`  
- `public GetTextureData(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 atlassedIndex) : Unity.Collections.NativeArray<System.Byte>`  
- `public GetTextureData(Colossal.Hash128 guid) : Unity.Collections.NativeArray<System.Byte>`  
- `public GetTextureIndex(System.Int32 stackGlobalIndex, System.Int32 xOffset, System.Int32 yOffset, System.Int32 width, System.Int32 height) : System.Int32`  
- `public GetTextureParamBlock(Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo vtAtlassingInfo) : Colossal.IO.AssetDatabase.VirtualTexturing.VTTextureParamBlock`  
- `public GetTextureSize(System.Int32 stackGlobalIndex, System.Int32 index) : Colossal.IO.AssetDatabase.VirtualTexturing.AtlassedSize`  
- `public GetTotalNbBlocks(System.Int32 stackGlobalIndex) : System.Int32`  
- `public GetVTSurfaceTileInfo(System.Int32 stackGlobalIndex, System.Int32 atlassedIndex) : Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo`  
- `internal GetVTTextureInfo(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 textureIndex) : Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTTextureInfo`  
- `public IsDoneLoading(Colossal.Hash128 textureGuid) : System.Boolean`  
- `public IsVTTextureData(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 textureIndex) : System.Boolean`  
- `public RegisterPerMaterialTileInfo(System.Int32 stackGlobalIndex, System.Int32 atlassedIndex, System.String path, System.Int64 tilesDataOffset, System.Int32[] dataOffsets, System.Int32[] dataSizes, System.Int32 nbTiles, System.Collections.Generic.List<System.Int32> compressedTileOffsets, System.Int32 width, System.Int32 height) : System.Void`  
- `public RegisterTextureData(Colossal.Hash128 textureGuid, System.Int32 dataSize) : System.Boolean`  
- `public RegisterVTTextureData(Colossal.Hash128 textureGuid, System.String fullPath, System.Int64 fileOffset, System.Int64 vtTextureDataIndex, System.Int32 dataSize, System.Collections.Generic.List<System.Int32> tileOffsets, System.Int32 width, System.Int32 height) : System.Boolean`  
- `public ReserveMultipleTextureRect(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height, System.Int32 qty, System.Int32 alignment, System.Int32& stackGlobalIndex) : System.Collections.Generic.List<System.Int32>`  
- `public ReserveTextureRect(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height) : Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo`  

## Nested types

- `Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+PathNotFoundException`  
- `Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTTextureInfo`  
- `Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+HighMipCaching`  
- `Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo`  

