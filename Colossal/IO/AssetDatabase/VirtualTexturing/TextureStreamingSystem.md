# Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem

**Assembly:** `Colossal.IO.AssetDatabase`  
**Namespace:** `Colossal.IO.AssetDatabase.VirtualTexturing`  

**Type:** class public  

**Base:** `Colossal.Entities.COSystemBase`  

## Code

```csharp
public class TextureStreamingSystem : Colossal.Entities.COSystemBase
{
    private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> m_BusyRequests;
    private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> m_AvailableRequests;
    private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.TexturesAsyncLoader> m_TexturesAsyncLoaders;
    private Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase m_VtDatabase;
    private Colossal.IO.AssetDatabase.VirtualTexturing.VTProceduralCPU m_VtProceduralCPU;
    private readonly System.Collections.Generic.Queue<Colossal.IO.AssetDatabase.SurfaceAsset> m_VTAssetsToInit;
    private readonly System.Collections.Generic.Queue<Colossal.IO.AssetDatabase.SurfaceAsset> m_VTAssetsShallowInit;
    private Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsDatabase m_AtlasMaterialsDatabase;
    private System.Int32 m_DatasetMipBias;
    private System.Int32 m_MidMipsCount;
    private System.Int32 m_MipBias;
    private System.Int32 m_VTMaterialsCountToLoad;
    private System.Int32 m_VTMaterialsDuplicatesCountToInit;
    private System.Boolean m_VTAssetsNeedRefresh;
    private System.Single <workingSetLodBias>k__BackingField;
    private UnityEngine.RenderTexture m_WorkingSetLodBiasRT;
    private UnityEngine.Material m_WorkingSetLodBiasMat;
    private readonly System.Collections.Generic.Queue<UnityEngine.Rendering.AsyncGPUReadbackRequest> m_MipBiasRequests;
    private static Unity.Profiling.ProfilerMarker s_OnUpdatePerfMarker;
    private static Unity.Profiling.ProfilerMarker s_ReadVTBiasPerfMarker;
    private static Unity.Profiling.ProfilerMarker s_LoadHeaderPerfMarker;
    private static Unity.Profiling.ProfilerMarker s_LoadVTAsyncPerfMarker;
    private static Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig s_VirtualTexturingConfig;
    private static System.String kMidMipCacheName;
    public static const System.String kLoadingTask;

    public System.Single workingSetLodBias { get; private set; }
    public Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig { get; }
    public System.Int32 tileSize { get; }
    public System.Int32 mipBias { get; }
    public Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase VTDatabase { get; }
    public System.Int32 dataSize { get; }
    public System.Int32 atlasDataSize { get; }
    public System.Int32 tilesFilledFromCPUCacheCount { get; }
    public System.Int32 perSurfaceAsyncTileReadCount { get; }
    public System.Int32 perTextureAsyncTileReadCount { get; }
    public System.Int32 midMipAsyncTextureReadCount { get; }
    public System.Int32 VTMaterialsLeftToLoadCount { get; }
    public System.Int32 VTMaterialsCountAssetsCount { get; }
    public System.Single VTMaterialAssetsProgression { get; }
    public System.Int32 midMipLevelsCount { get; }
    public System.Int32 VTMaterialsDuplicatesToProcessCount { get; }
    public System.Int32 VTMaterialsAssetsDuplicatesCount { get; }
    public System.Single VTMaterialDuplicatesProgression { get; }
    public System.Int32 bc7SrgbEntriesCount { get; }
    public System.Int32 bc7UNormEntriesCount { get; }
    public System.Int32 otherEntriesCount { get; }
    public System.Int32 busyRequestsCount { get; }
    public System.Int32 availableRequestsCount { get; }
    public System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> BusyRequests { get; }

    public TextureStreamingSystem();

    private System.Void <OnUpdate>g__ReportProgress|45_0();
    private System.Boolean <RefreshVT>b__42_0(Colossal.IO.AssetDatabase.MidMipCacheAsset x);
    public System.Void AddTextureAsyncLoader(Colossal.IO.AssetDatabase.TexturesAsyncLoader texturesAsyncLoader);
    public System.Void AddTextureToCache(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 textureIndex, System.Int32 textureWidth, System.Int32 textureHeight, Colossal.Hash128 guid, System.Int32 nbPreProcessedMidMipLevels);
    public System.Void BindMaterial(UnityEngine.Material material, System.Int32 stackGlobalIndex, System.Int32 stackConfigIndex, Colossal.IO.AssetDatabase.VirtualTexturing.VTTextureParamBlock textureParams);
    public System.Void BindMaterial(UnityEngine.Material material, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] vtAtlassingInfos, System.Int32 materialIndex);
    public System.Void BindStacksGlobally(System.Int32 stackGlobalIndex);
    public System.Void BindStacksGlobally();
    private System.Void CleanupVT();
    private System.Void CompletedRequests(System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> busyRequests, System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> availableRequests);
    public System.Void DoneLoading(Colossal.Hash128 textureGuid);
    public System.Void FillRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry objectEntry, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest);
    public System.Int32 GetNbReservedBlocks(System.Int32 stackGlobalIndex);
    public Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest GetRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+TextureStackRequestHandle<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters> request);
    public System.Int32 GetStackConfigIndex(System.Int32 stackGlobalIndex);
    public Unity.Collections.NativeArray<System.Byte> GetTextureData(Colossal.Hash128 textureGuid);
    public Colossal.IO.AssetDatabase.VirtualTexturing.VTTextureParamBlock GetTextureParamBlock(Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo vtAtlassingInfo);
    public System.Int32 GetTotalNbBlocks(System.Int32 stackGlobalIndex);
    public System.Int32 GetUniversalTileIndex(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req);
    public System.Void Initialize();
    public System.Void Initialize(System.Int32 desiredMipBias, UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode);
    public System.Void InvalidateRegion(System.Int32 stackGlobalIndex, System.Int32 textureIndex);
    public System.Boolean IsDoneLoading(Colossal.Hash128 textureGuid);
    public System.Void MarkVTAssetsDirty();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public static System.Void ReadMidMipTextureDataAsync(System.String path, System.Int64 srcStart, System.Int32 length, System.Boolean hasTrilinear, System.Int64 trilinearSrcStart, System.Int32 trilinearLenght, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestLayerParameters layer);
    public static System.Int32 ReadTextureDataAsync(Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo vtSurfaceInfo, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, System.Int32 tileIndex);
    public static System.Int32 ReadTextureDataAsync2(Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo vtSurfaceInfo, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, System.Int32 tileIndex);
    public static System.Void ReadVTTextureDataAsync(System.String path, System.Int64 fileOffset, System.Int32 compressedSize, System.Int32 length, System.Boolean hasTrilinear, System.Int32 trilinearLength, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestLayerParameters layer);
    public System.Void RefreshVT(Colossal.IO.AssetDatabase.ILocalAssetDatabase database);
    public System.Boolean RegisterTextureData(Colossal.Hash128 textureGuid, System.Int32 dataSize);
    public System.Void RegisterVTSurfaceTileInfo(System.Int32 stackGlobalIndex, System.Int32 atlassedIndex, System.String path, System.Int64 highMipDataOffset, System.Int32[] dataOffsets, System.Int32[] dataSizes, System.Int32 nbTiles, System.Collections.Generic.List<System.Int32> compressedTileOffsets, System.Int32 width, System.Int32 height);
    public System.Boolean RegisterVTTextureData(Colossal.Hash128 textureGuid, System.String preProcessedPath, System.Int64 fileOffset, System.Int64 preProcessedDataIndex, System.Int32 dataSize, System.Collections.Generic.List<System.Int32> tileOffsets, System.Int32 width, System.Int32 height);
    public System.Void Reload();
    public System.Void RequestRegion(System.Int32 stackGlobalIndex, System.Int32 textureIndex, System.Single maxPixel, Colossal.Mathematics.Bounds2 bounds);
    private System.Void RequestRegion(System.Int32 stackGlobalIndex, System.Int32 textureIndex, System.Int32 minMip, System.Int32 maxMip, Colossal.Mathematics.Bounds2 bounds);
    public System.Collections.Generic.List<System.Int32> ReserveMultipleTextureRect(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height, System.Int32 qty, System.Int32 alignment, System.Int32& stackGlobalIndex);
    public Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo ReserveTextureRect(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height);
    public System.Boolean ShouldResetVT(System.Int32 desiredMipBias, UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode);
    public System.Boolean TryGetMidMipMask(System.Int32 stackGlobalIndex, System.Int32 universalTextureIndex, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry& objectEntry);
    public System.Void UpdateWorkingSetMipBias();
}
```


## Fields

- `private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> m_BusyRequests`  

```csharp
private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> m_BusyRequests;
```

- `private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> m_AvailableRequests`  

```csharp
private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> m_AvailableRequests;
```

- `private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.TexturesAsyncLoader> m_TexturesAsyncLoaders`  

```csharp
private readonly System.Collections.Generic.List<Colossal.IO.AssetDatabase.TexturesAsyncLoader> m_TexturesAsyncLoaders;
```

- `private Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase m_VtDatabase`  

```csharp
private Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase m_VtDatabase;
```

- `private Colossal.IO.AssetDatabase.VirtualTexturing.VTProceduralCPU m_VtProceduralCPU`  

```csharp
private Colossal.IO.AssetDatabase.VirtualTexturing.VTProceduralCPU m_VtProceduralCPU;
```

- `private readonly System.Collections.Generic.Queue<Colossal.IO.AssetDatabase.SurfaceAsset> m_VTAssetsToInit`  

```csharp
private readonly System.Collections.Generic.Queue<Colossal.IO.AssetDatabase.SurfaceAsset> m_VTAssetsToInit;
```

- `private readonly System.Collections.Generic.Queue<Colossal.IO.AssetDatabase.SurfaceAsset> m_VTAssetsShallowInit`  

```csharp
private readonly System.Collections.Generic.Queue<Colossal.IO.AssetDatabase.SurfaceAsset> m_VTAssetsShallowInit;
```

- `private Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsDatabase m_AtlasMaterialsDatabase`  

```csharp
private Colossal.IO.AssetDatabase.VirtualTexturing.AtlasMaterialsDatabase m_AtlasMaterialsDatabase;
```

- `private System.Int32 m_DatasetMipBias`  

```csharp
private System.Int32 m_DatasetMipBias;
```

- `private System.Int32 m_MidMipsCount`  

```csharp
private System.Int32 m_MidMipsCount;
```

- `private System.Int32 m_MipBias`  

```csharp
private System.Int32 m_MipBias;
```

- `private System.Int32 m_VTMaterialsCountToLoad`  

```csharp
private System.Int32 m_VTMaterialsCountToLoad;
```

- `private System.Int32 m_VTMaterialsDuplicatesCountToInit`  

```csharp
private System.Int32 m_VTMaterialsDuplicatesCountToInit;
```

- `private System.Boolean m_VTAssetsNeedRefresh`  

```csharp
private System.Boolean m_VTAssetsNeedRefresh;
```

- `private System.Single <workingSetLodBias>k__BackingField`  

```csharp
private System.Single <workingSetLodBias>k__BackingField;
```

- `private UnityEngine.RenderTexture m_WorkingSetLodBiasRT`  

```csharp
private UnityEngine.RenderTexture m_WorkingSetLodBiasRT;
```

- `private UnityEngine.Material m_WorkingSetLodBiasMat`  

```csharp
private UnityEngine.Material m_WorkingSetLodBiasMat;
```

- `private readonly System.Collections.Generic.Queue<UnityEngine.Rendering.AsyncGPUReadbackRequest> m_MipBiasRequests`  

```csharp
private readonly System.Collections.Generic.Queue<UnityEngine.Rendering.AsyncGPUReadbackRequest> m_MipBiasRequests;
```

- `private static Unity.Profiling.ProfilerMarker s_OnUpdatePerfMarker`  

```csharp
private static Unity.Profiling.ProfilerMarker s_OnUpdatePerfMarker;
```

- `private static Unity.Profiling.ProfilerMarker s_ReadVTBiasPerfMarker`  

```csharp
private static Unity.Profiling.ProfilerMarker s_ReadVTBiasPerfMarker;
```

- `private static Unity.Profiling.ProfilerMarker s_LoadHeaderPerfMarker`  

```csharp
private static Unity.Profiling.ProfilerMarker s_LoadHeaderPerfMarker;
```

- `private static Unity.Profiling.ProfilerMarker s_LoadVTAsyncPerfMarker`  

```csharp
private static Unity.Profiling.ProfilerMarker s_LoadVTAsyncPerfMarker;
```

- `private static Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig s_VirtualTexturingConfig`  

```csharp
private static Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig s_VirtualTexturingConfig;
```

- `private static System.String kMidMipCacheName`  

```csharp
private static System.String kMidMipCacheName;
```

- `public static const System.String kLoadingTask`  

```csharp
public static const System.String kLoadingTask;
```


## Properties

- `public System.Single workingSetLodBias { get; private set }`  

```csharp
public System.Single workingSetLodBias { get; private set; }
```

- `public Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig { get }`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.VirtualTexturingConfig virtualTexturingConfig { get; }
```

- `public System.Int32 tileSize { get }`  

```csharp
public System.Int32 tileSize { get; }
```

- `public System.Int32 mipBias { get }`  

```csharp
public System.Int32 mipBias { get; }
```

- `public Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase VTDatabase { get }`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase VTDatabase { get; }
```

- `public System.Int32 dataSize { get }`  

```csharp
public System.Int32 dataSize { get; }
```

- `public System.Int32 atlasDataSize { get }`  

```csharp
public System.Int32 atlasDataSize { get; }
```

- `public System.Int32 tilesFilledFromCPUCacheCount { get }`  

```csharp
public System.Int32 tilesFilledFromCPUCacheCount { get; }
```

- `public System.Int32 perSurfaceAsyncTileReadCount { get }`  

```csharp
public System.Int32 perSurfaceAsyncTileReadCount { get; }
```

- `public System.Int32 perTextureAsyncTileReadCount { get }`  

```csharp
public System.Int32 perTextureAsyncTileReadCount { get; }
```

- `public System.Int32 midMipAsyncTextureReadCount { get }`  

```csharp
public System.Int32 midMipAsyncTextureReadCount { get; }
```

- `public System.Int32 VTMaterialsLeftToLoadCount { get }`  

```csharp
public System.Int32 VTMaterialsLeftToLoadCount { get; }
```

- `public System.Int32 VTMaterialsCountAssetsCount { get }`  

```csharp
public System.Int32 VTMaterialsCountAssetsCount { get; }
```

- `public System.Single VTMaterialAssetsProgression { get }`  

```csharp
public System.Single VTMaterialAssetsProgression { get; }
```

- `public System.Int32 midMipLevelsCount { get }`  

```csharp
public System.Int32 midMipLevelsCount { get; }
```

- `public System.Int32 VTMaterialsDuplicatesToProcessCount { get }`  

```csharp
public System.Int32 VTMaterialsDuplicatesToProcessCount { get; }
```

- `public System.Int32 VTMaterialsAssetsDuplicatesCount { get }`  

```csharp
public System.Int32 VTMaterialsAssetsDuplicatesCount { get; }
```

- `public System.Single VTMaterialDuplicatesProgression { get }`  

```csharp
public System.Single VTMaterialDuplicatesProgression { get; }
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

- `public System.Int32 busyRequestsCount { get }`  

```csharp
public System.Int32 busyRequestsCount { get; }
```

- `public System.Int32 availableRequestsCount { get }`  

```csharp
public System.Int32 availableRequestsCount { get; }
```

- `public System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> BusyRequests { get }`  

```csharp
public System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> BusyRequests { get; }
```


## Constructors

- `public TextureStreamingSystem()`  

```csharp
public TextureStreamingSystem();
```


## Methods

- `private <OnUpdate>g__ReportProgress|45_0() : System.Void`  

```csharp
private System.Void <OnUpdate>g__ReportProgress|45_0();
```

- `private <RefreshVT>b__42_0(Colossal.IO.AssetDatabase.MidMipCacheAsset x) : System.Boolean`  

```csharp
private System.Boolean <RefreshVT>b__42_0(Colossal.IO.AssetDatabase.MidMipCacheAsset x);
```

- `public AddTextureAsyncLoader(Colossal.IO.AssetDatabase.TexturesAsyncLoader texturesAsyncLoader) : System.Void`  

```csharp
public System.Void AddTextureAsyncLoader(Colossal.IO.AssetDatabase.TexturesAsyncLoader texturesAsyncLoader);
```

- `public AddTextureToCache(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 textureIndex, System.Int32 textureWidth, System.Int32 textureHeight, Colossal.Hash128 guid, System.Int32 nbPreProcessedMidMipLevels) : System.Void`  

```csharp
public System.Void AddTextureToCache(System.Int32 stackGlobalIndex, System.Int32 layerIndex, System.Int32 textureIndex, System.Int32 textureWidth, System.Int32 textureHeight, Colossal.Hash128 guid, System.Int32 nbPreProcessedMidMipLevels);
```

- `public BindMaterial(UnityEngine.Material material, System.Int32 stackGlobalIndex, System.Int32 stackConfigIndex, Colossal.IO.AssetDatabase.VirtualTexturing.VTTextureParamBlock textureParams) : System.Void`  

```csharp
public System.Void BindMaterial(UnityEngine.Material material, System.Int32 stackGlobalIndex, System.Int32 stackConfigIndex, Colossal.IO.AssetDatabase.VirtualTexturing.VTTextureParamBlock textureParams);
```

- `public BindMaterial(UnityEngine.Material material, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] vtAtlassingInfos, System.Int32 materialIndex) : System.Void`  

```csharp
public System.Void BindMaterial(UnityEngine.Material material, Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo[] vtAtlassingInfos, System.Int32 materialIndex);
```

- `public BindStacksGlobally(System.Int32 stackGlobalIndex) : System.Void`  

```csharp
public System.Void BindStacksGlobally(System.Int32 stackGlobalIndex);
```

- `public BindStacksGlobally() : System.Void`  

```csharp
public System.Void BindStacksGlobally();
```

- `private CleanupVT() : System.Void`  

```csharp
private System.Void CleanupVT();
```

- `private CompletedRequests(System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> busyRequests, System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> availableRequests) : System.Void`  

```csharp
private System.Void CompletedRequests(System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> busyRequests, System.Collections.Generic.List<Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest> availableRequests);
```

- `public DoneLoading(Colossal.Hash128 textureGuid) : System.Void`  

```csharp
public System.Void DoneLoading(Colossal.Hash128 textureGuid);
```

- `public FillRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry objectEntry, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest) : System.Void`  

```csharp
public System.Void FillRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry objectEntry, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest);
```

- `public GetNbReservedBlocks(System.Int32 stackGlobalIndex) : System.Int32`  

```csharp
public System.Int32 GetNbReservedBlocks(System.Int32 stackGlobalIndex);
```

- `public GetRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+TextureStackRequestHandle<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters> request) : Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest GetRequest(UnityEngine.Rendering.VirtualTexturing.Procedural+TextureStackRequestHandle<UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters> request);
```

- `public GetStackConfigIndex(System.Int32 stackGlobalIndex) : System.Int32`  

```csharp
public System.Int32 GetStackConfigIndex(System.Int32 stackGlobalIndex);
```

- `public GetTextureData(Colossal.Hash128 textureGuid) : Unity.Collections.NativeArray<System.Byte>`  

```csharp
public Unity.Collections.NativeArray<System.Byte> GetTextureData(Colossal.Hash128 textureGuid);
```

- `public GetTextureParamBlock(Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo vtAtlassingInfo) : Colossal.IO.AssetDatabase.VirtualTexturing.VTTextureParamBlock`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.VTTextureParamBlock GetTextureParamBlock(Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo vtAtlassingInfo);
```

- `public GetTotalNbBlocks(System.Int32 stackGlobalIndex) : System.Int32`  

```csharp
public System.Int32 GetTotalNbBlocks(System.Int32 stackGlobalIndex);
```

- `public GetUniversalTileIndex(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req) : System.Int32`  

```csharp
public System.Int32 GetUniversalTileIndex(UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req);
```

- `public Initialize() : System.Void`  

```csharp
public System.Void Initialize();
```

- `public Initialize(System.Int32 desiredMipBias, UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode) : System.Void`  

```csharp
public System.Void Initialize(System.Int32 desiredMipBias, UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode);
```

- `public InvalidateRegion(System.Int32 stackGlobalIndex, System.Int32 textureIndex) : System.Void`  

```csharp
public System.Void InvalidateRegion(System.Int32 stackGlobalIndex, System.Int32 textureIndex);
```

- `public IsDoneLoading(Colossal.Hash128 textureGuid) : System.Boolean`  

```csharp
public System.Boolean IsDoneLoading(Colossal.Hash128 textureGuid);
```

- `public MarkVTAssetsDirty() : System.Void`  

```csharp
public System.Void MarkVTAssetsDirty();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public static ReadMidMipTextureDataAsync(System.String path, System.Int64 srcStart, System.Int32 length, System.Boolean hasTrilinear, System.Int64 trilinearSrcStart, System.Int32 trilinearLenght, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestLayerParameters layer) : System.Void`  

```csharp
public static System.Void ReadMidMipTextureDataAsync(System.String path, System.Int64 srcStart, System.Int32 length, System.Boolean hasTrilinear, System.Int64 trilinearSrcStart, System.Int32 trilinearLenght, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestLayerParameters layer);
```

- `public static ReadTextureDataAsync(Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo vtSurfaceInfo, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, System.Int32 tileIndex) : System.Int32`  

```csharp
public static System.Int32 ReadTextureDataAsync(Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo vtSurfaceInfo, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, System.Int32 tileIndex);
```

- `public static ReadTextureDataAsync2(Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo vtSurfaceInfo, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, System.Int32 tileIndex) : System.Int32`  

```csharp
public static System.Int32 ReadTextureDataAsync2(Colossal.IO.AssetDatabase.VirtualTexturing.VTDatabase+VTSurfaceInfo vtSurfaceInfo, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestParameters req, System.Int32 tileIndex);
```

- `public static ReadVTTextureDataAsync(System.String path, System.Int64 fileOffset, System.Int32 compressedSize, System.Int32 length, System.Boolean hasTrilinear, System.Int32 trilinearLength, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestLayerParameters layer) : System.Void`  

```csharp
public static System.Void ReadVTTextureDataAsync(System.String path, System.Int64 fileOffset, System.Int32 compressedSize, System.Int32 length, System.Boolean hasTrilinear, System.Int32 trilinearLength, Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest textureStreamingRequest, UnityEngine.Rendering.VirtualTexturing.Procedural+CPUTextureStackRequestLayerParameters layer);
```

- `public RefreshVT(Colossal.IO.AssetDatabase.ILocalAssetDatabase database) : System.Void`  

```csharp
public System.Void RefreshVT(Colossal.IO.AssetDatabase.ILocalAssetDatabase database);
```

- `public RegisterTextureData(Colossal.Hash128 textureGuid, System.Int32 dataSize) : System.Boolean`  

```csharp
public System.Boolean RegisterTextureData(Colossal.Hash128 textureGuid, System.Int32 dataSize);
```

- `public RegisterVTSurfaceTileInfo(System.Int32 stackGlobalIndex, System.Int32 atlassedIndex, System.String path, System.Int64 highMipDataOffset, System.Int32[] dataOffsets, System.Int32[] dataSizes, System.Int32 nbTiles, System.Collections.Generic.List<System.Int32> compressedTileOffsets, System.Int32 width, System.Int32 height) : System.Void`  

```csharp
public System.Void RegisterVTSurfaceTileInfo(System.Int32 stackGlobalIndex, System.Int32 atlassedIndex, System.String path, System.Int64 highMipDataOffset, System.Int32[] dataOffsets, System.Int32[] dataSizes, System.Int32 nbTiles, System.Collections.Generic.List<System.Int32> compressedTileOffsets, System.Int32 width, System.Int32 height);
```

- `public RegisterVTTextureData(Colossal.Hash128 textureGuid, System.String preProcessedPath, System.Int64 fileOffset, System.Int64 preProcessedDataIndex, System.Int32 dataSize, System.Collections.Generic.List<System.Int32> tileOffsets, System.Int32 width, System.Int32 height) : System.Boolean`  

```csharp
public System.Boolean RegisterVTTextureData(Colossal.Hash128 textureGuid, System.String preProcessedPath, System.Int64 fileOffset, System.Int64 preProcessedDataIndex, System.Int32 dataSize, System.Collections.Generic.List<System.Int32> tileOffsets, System.Int32 width, System.Int32 height);
```

- `public Reload() : System.Void`  

```csharp
public System.Void Reload();
```

- `public RequestRegion(System.Int32 stackGlobalIndex, System.Int32 textureIndex, System.Single maxPixel, Colossal.Mathematics.Bounds2 bounds) : System.Void`  

```csharp
public System.Void RequestRegion(System.Int32 stackGlobalIndex, System.Int32 textureIndex, System.Single maxPixel, Colossal.Mathematics.Bounds2 bounds);
```

- `private RequestRegion(System.Int32 stackGlobalIndex, System.Int32 textureIndex, System.Int32 minMip, System.Int32 maxMip, Colossal.Mathematics.Bounds2 bounds) : System.Void`  

```csharp
private System.Void RequestRegion(System.Int32 stackGlobalIndex, System.Int32 textureIndex, System.Int32 minMip, System.Int32 maxMip, Colossal.Mathematics.Bounds2 bounds);
```

- `public ReserveMultipleTextureRect(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height, System.Int32 qty, System.Int32 alignment, System.Int32& stackGlobalIndex) : System.Collections.Generic.List<System.Int32>`  

```csharp
public System.Collections.Generic.List<System.Int32> ReserveMultipleTextureRect(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height, System.Int32 qty, System.Int32 alignment, System.Int32& stackGlobalIndex);
```

- `public ReserveTextureRect(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height) : Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo`  

```csharp
public Colossal.IO.AssetDatabase.VirtualTexturing.VTAtlassingInfo ReserveTextureRect(System.Int32 stackConfigIndex, System.Int32 width, System.Int32 height);
```

- `public ShouldResetVT(System.Int32 desiredMipBias, UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode) : System.Boolean`  

```csharp
public System.Boolean ShouldResetVT(System.Int32 desiredMipBias, UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode);
```

- `public TryGetMidMipMask(System.Int32 stackGlobalIndex, System.Int32 universalTextureIndex, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry& objectEntry) : System.Boolean`  

```csharp
public System.Boolean TryGetMidMipMask(System.Int32 stackGlobalIndex, System.Int32 universalTextureIndex, Colossal.IO.AssetDatabase.VirtualTexturing.ObjectEntry& objectEntry);
```

- `public UpdateWorkingSetMipBias() : System.Void`  

```csharp
public System.Void UpdateWorkingSetMipBias();
```


## Nested types

- `Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+ShaderID`  
- `Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+ShaderIDs`  
- `Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+TextureStreamingRequest`  
- `Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem+<>c`  

