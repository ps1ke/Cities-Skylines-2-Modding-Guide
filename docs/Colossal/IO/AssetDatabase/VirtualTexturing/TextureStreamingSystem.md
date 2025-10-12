# Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `Colossal.Entities.COSystemBase`  

## Fields

- `private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> m_BusyRequests`  
- `private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> m_AvailableRequests`  
- `private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.TexturesAsyncLoader> m_TexturesAsyncLoaders`  
- `private Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase m_VtDatabase`  
- `private Colossal.IO.AssetDatabase.VirtualTexturing.VTProceduralCPU m_VtProceduralCPU`  
- `private readonly System.Collections.Generic.Queue<Colossal.IO.AssetDatabase.SurfaceAsset> m_VTAssetsToInit`  
- `private readonly System.Collections.Generic.Queue<Colossal.IO.AssetDatabase.SurfaceAsset> m_VTAssetsShallowInit`  
- `private Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsDatabase m_AtlasMaterialsDatabase`  
- `private System.Int32 m_DatasetMipBias`  
- `private System.Int32 m_MidMipsCount`  
- `private System.Int32 m_MipBias`  
- `private System.Int32 m_VTMaterialsCountToLoad`  
- `private System.Int32 m_VTMaterialsDuplicatesCountToInit`  
- `private System.Boolean m_VTAssetsNeedRefresh`  
- `private System.Single <workingSetLodBias>k__BackingField`  
- `private UnityEngine.RenderTexture m_WorkingSetLodBiasRT`  
- `private UnityEngine.Material m_WorkingSetLodBiasMat`  
- `private readonly System.Collections.Generic.Queue<UnityEngine.Rendering.AsyncGPUReadbackRequest> m_MipBiasRequests`  
- `private static Unity.Profiling.ProfilerMarker s_OnUpdatePerfMarker`  
- `private static Unity.Profiling.ProfilerMarker s_ReadVTBiasPerfMarker`  
- `private static Unity.Profiling.ProfilerMarker s_LoadHeaderPerfMarker`  
- `private static Unity.Profiling.ProfilerMarker s_LoadVTAsyncPerfMarker`  
- `private static Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig s_VirtualTexturingConfig`  
- `private static System.String kMidMipCacheName`  
- `public static const System.String kLoadingTask`  

## Properties

- `public System.Single workingSetLodBias { get; private set }`  
- `public Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig { get }`  
- `public System.Int32 tileSize { get }`  
- `public System.Int32 mipBias { get }`  
- `public Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase VTDatabase { get }`  
- `public System.Int32 dataSize { get }`  
- `public System.Int32 atlasDataSize { get }`  
- `public System.Int32 tilesFilledFromCPUCacheCount { get }`  
- `public System.Int32 perSurfaceAsyncTileReadCount { get }`  
- `public System.Int32 perTextureAsyncTileReadCount { get }`  
- `public System.Int32 midMipAsyncTextureReadCount { get }`  
- `public System.Int32 VTMaterialsLeftToLoadCount { get }`  
- `public System.Int32 VTMaterialsCountAssetsCount { get }`  
- `public System.Single VTMaterialAssetsProgression { get }`  
- `public System.Int32 midMipLevelsCount { get }`  
- `public System.Int32 VTMaterialsDuplicatesToProcessCount { get }`  
- `public System.Int32 VTMaterialsAssetsDuplicatesCount { get }`  
- `public System.Single VTMaterialDuplicatesProgression { get }`  
- `public System.Int32 bc7SrgbEntriesCount { get }`  
- `public System.Int32 bc7UNormEntriesCount { get }`  
- `public System.Int32 otherEntriesCount { get }`  
- `public System.Int32 busyRequestsCount { get }`  
- `public System.Int32 availableRequestsCount { get }`  
- `public System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> BusyRequests { get }`  

## Constructors

- `public TextureStreamingSystem()`  

## Methods

- `private <OnUpdate>g__ReportProgress|45_0() : System.Void`  
- `private <RefreshVT>b__42_0(Colossal.IO.AssetDatabase.MidMipCacheAsset x) : System.Boolean`  
- `public AddTextureAsyncLoader(Colossal.IO.AssetDatabase.TexturesAsyncLoader texturesAsyncLoader) : System.Void`  
- `public AddTextureToCache(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 textureIndex, System.Int32 textureWidth, System.Int32 textureHeight, Colossal.Hash128 guid, System.Int32 nbPreProcessedMidMipLevels) : System.Void`  
- `public BindMaterial(UnityEngine.Material material, System.Int32 stackGlobalIndex, System.Int32 stackConfigIndex, Colossal.IO.AssetDatabase.VirtualTexturing.VTTextureParamBlock textureParams) : System.Void`  
- `public BindMaterial(UnityEngine.Material material, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] vtAtlassingInfos, System.Int32 materialIndex) : System.Void`  
- `public BindStacksGlobally(System.Int32 stackGlobalIndex) : System.Void`  
- `public BindStacksGlobally() : System.Void`  
- `private CleanupVT() : System.Void`  
- `private CompletedRequests(System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> busyRequests, System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> availableRequests) : System.Void`  
- `public DoneLoading(Colossal.Hash128 textureGuid) : System.Void`  
- `public FillRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry objectEntry, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest) : System.Void`  
- `public GetNbReservedBlocks(System.Int32 stackGlobalIndex) : System.Int32`  
- `public GetRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+TextureStackRequestHandle<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters> request) : Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest`  
- `public GetStackConfigIndex(System.Int32 stackGlobalIndex) : System.Int32`  
- `public GetTextureData(Colossal.Hash128 textureGuid) : Unity.Collections.NativeArray<System.Byte>`  
- `public GetTextureParamBlock(Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo vtAtlassingInfo) : Colossal.IO.AssetDatabase.VirtualTexturing.VTTextureParamBlock`  
- `public GetTotalNbBlocks(System.Int32 stackGlobalIndex) : System.Int32`  
- `public GetUniversalTileIndex(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req) : System.Int32`  
- `public Initialize() : System.Void`  
- `public Initialize(System.Int32 desiredMipBias, UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode) : System.Void`  
- `public InvalidateRegion(System.Int32 stackGlobalIndex, System.Int32 textureIndex) : System.Void`  
- `public IsDoneLoading(Colossal.Hash128 textureGuid) : System.Boolean`  
- `public MarkVTAssetsDirty() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public static ReadMidMipTextureDataAsync(System.String path, System.Int64 srcStart, System.Int32 length, System.Boolean hasTrilinear, System.Int64 trilinearSrcStart, System.Int32 trilinearLenght, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestLayerParameters layer) : System.Void`  
- `public static ReadTextureDataAsync(Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo vtSurfaceInfo, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, System.Int32 tileIndex) : System.Int32`  
- `public static ReadTextureDataAsync2(Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo vtSurfaceInfo, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, System.Int32 tileIndex) : System.Int32`  
- `public static ReadVTTextureDataAsync(System.String path, System.Int64 fileOffset, System.Int32 compressedSize, System.Int32 length, System.Boolean hasTrilinear, System.Int32 trilinearLength, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestLayerParameters layer) : System.Void`  
- `public RefreshVT(Colossal.IO.AssetDatabase.ILocalAssetDatabase database) : System.Void`  
- `public RegisterTextureData(Colossal.Hash128 textureGuid, System.Int32 dataSize) : System.Boolean`  
- `public RegisterVTSurfaceTileInfo(System.Int32 stackGlobalIndex, System.Int32 atlassedIndex, System.String path, System.Int64 highMipDataOffset, System.Int32[] dataOffsets, System.Int32[] dataSizes, System.Int32 nbTiles, System.Collections.Generic.List<System.Int32> compressedTileOffsets, System.Int32 width, System.Int32 height) : System.Void`  
- `public RegisterVTTextureData(Colossal.Hash128 textureGuid, System.String preProcessedPath, System.Int64 fileOffset, System.Int64 preProcessedDataIndex, System.Int32 dataSize, System.Collections.Generic.List<System.Int32> tileOffsets, System.Int32 width, System.Int32 height) : System.Boolean`  
- `public Reload() : System.Void`  
- `public RequestRegion(System.Int32 stackGlobalIndex, System.Int32 textureIndex, System.Single maxPixel, Colossal.Mathematics.Bounds2 bounds) : System.Void`  
- `private RequestRegion(System.Int32 stackGlobalIndex, System.Int32 textureIndex, System.Int32 minMip, System.Int32 maxMip, Colossal.Mathematics.Bounds2 bounds) : System.Void`  
- `public ReserveMultipleTextureRect(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height, System.Int32 qty, System.Int32 alignment, System.Int32& stackGlobalIndex) : System.Collections.Generic.List<System.Int32>`  
- `public ReserveTextureRect(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height) : Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo`  
- `public ShouldResetVT(System.Int32 desiredMipBias, UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode) : System.Boolean`  
- `public TryGetMidMipMask(System.Int32 stackGlobalIndex, System.Int32 universalTextureIndex, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry& objectEntry) : System.Boolean`  
- `public UpdateWorkingSetMipBias() : System.Void`  

## Nested types

- `Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+ShaderID`  
- `Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+ShaderIDs`  
- `Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest`  
- `Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+<>c`  

