# Game.Rendering.BatchMeshSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.UInt64 <memoryBudget>k__BackingField`  
- `private System.Boolean <strictMemoryBudget>k__BackingField`  
- `private System.Boolean <enableMeshLoading>k__BackingField`  
- `private System.Boolean <forceMeshUnloading>k__BackingField`  
- `private System.UInt64 <totalSizeInMemory>k__BackingField`  
- `private System.Int32 <loadingRemaining>k__BackingField`  
- `private Colossal.IO.AssetDatabase.GeometryAssetLoadingSystem m_GeometryLoadingSystem`  
- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private UnityEngine.Mesh m_DefaultObjectMesh`  
- `private UnityEngine.Mesh m_DefaultBaseMesh`  
- `private UnityEngine.Mesh m_DefaultLaneMesh`  
- `private UnityEngine.Mesh m_ZoneBlockMesh`  
- `private UnityEngine.Mesh m_ZoneLodMesh`  
- `private UnityEngine.Mesh m_DefaultEdgeMesh`  
- `private UnityEngine.Mesh m_DefaultNodeMesh`  
- `private UnityEngine.Mesh m_DefaultRoundaboutMesh`  
- `private System.Collections.Generic.List<UnityEngine.Mesh> m_GeneratedMeshes`  
- `private System.Collections.Generic.List<System.Int32> m_FreeMeshIndices`  
- `private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.GeometryAsset> m_UnloadGeometryAssets`  
- `private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.GeometryAsset> m_LoadingGeometries`  
- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Rendering.BatchMeshSystem+CacheInfo> m_CachingMeshes`  
- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Rendering.BatchMeshSystem+MeshInfo> m_MeshInfos`  
- `private Unity.Collections.NativeList<System.Int32> m_BatchPriority`  
- `private Unity.Collections.NativeList<Game.Rendering.MeshLoadingState> m_LoadingState`  
- `private Unity.Collections.NativeList<Game.Rendering.BatchMeshSystem+LoadingData> m_LoadingData`  
- `private Unity.Collections.NativeList<Game.Rendering.BatchMeshSystem+LoadingData> m_UnloadingData`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_GenerateMeshEntities`  
- `private Colossal.Collections.NativeHeapAllocator m_ShapeAllocator`  
- `private Unity.Jobs.JobHandle m_PriorityDeps`  
- `private Unity.Jobs.JobHandle m_StateDeps`  
- `private Unity.Jobs.JobHandle m_GenerateMeshDeps`  
- `private UnityEngine.GraphicsBuffer m_ShapeBuffer`  
- `private UnityEngine.Mesh+MeshDataArray m_GenerateMeshDataArray`  
- `private System.Int32 m_ShapeCount`  
- `private System.Int32 m_PriorityLimit`  
- `private System.Boolean m_AddMeshes`  
- `public static const System.String kDisableMeshLoadingKey`  
- `public static const System.String kForceMeshUnloadingKey`  
- `public static const System.UInt32 MAX_LOADING_COUNT`  
- `public static const System.Int32 MIN_BATCH_PRIORITY`  
- `public static const System.Int32 SHAPEBUFFER_ELEMENT_SIZE`  
- `public static const System.UInt32 SHAPEBUFFER_MEMORY_DEFAULT`  
- `public static const System.UInt32 SHAPEBUFFER_MEMORY_INCREMENT`  
- `public static const System.UInt64 DEFAULT_MEMORY_BUDGET`  
- `public static const System.Boolean DEFAULT_MEMORY_BUDGET_IS_STRICT`  

## Properties

- `public System.UInt64 memoryBudget { get; set }`  
- `public System.Boolean strictMemoryBudget { get; set }`  
- `public System.Boolean enableMeshLoading { get; set }`  
- `public System.Boolean forceMeshUnloading { get; set }`  
- `public System.UInt64 totalSizeInMemory { get; private set }`  
- `public System.Int32 loadedMeshCount { get }`  
- `public System.Int32 loadingRemaining { get; private set }`  

## Constructors

- `public BatchMeshSystem()`  

## Methods

- `public AddBatch(Game.Rendering.CustomBatch batch, System.Int32 batchIndex) : System.Void`  
- `public AddBatchPriorityWriter(Unity.Jobs.JobHandle dependencies) : System.Void`  
- `private AddCaching(Unity.Entities.Entity entity, Game.Rendering.BatchMeshSystem+CacheInfo cacheInfo) : System.Void`  
- `public AddLoadingStateReader(Unity.Jobs.JobHandle dependencies) : System.Void`  
- `private AddMeshes() : System.Void`  
- `private AddShapeData(Game.Prefabs.RenderPrefab meshPrefab) : Game.Rendering.BatchMeshSystem+ShapeAllocation[]`  
- `private BatchPropertyUpdated(Game.Rendering.CustomBatch batch) : System.Void`  
- `private CacheMeshData(Game.Prefabs.RenderPrefab meshPrefab, Colossal.IO.AssetDatabase.GeometryAsset asset, Unity.Entities.Entity entity, Game.Prefabs.MeshType type) : System.Void`  
- `private CacheMeshData(UnityEngine.Mesh mesh, Unity.Entities.Entity entity, Game.Prefabs.MeshType type) : System.Void`  
- `public CompleteCaching() : System.Void`  
- `private CompleteCaching(Unity.Entities.Entity entity) : System.Void`  
- `private CompleteCaching(Unity.Entities.Entity entity, Game.Rendering.BatchMeshSystem+CacheInfo cacheInfo) : System.Void`  
- `public CompleteMeshes() : System.Void`  
- `private EstimateSizeInMemory(Game.Prefabs.RenderPrefab meshPrefab) : System.UInt64`  
- `private GenerateMeshes() : System.Void`  
- `public GetBatchPriority(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<System.Int32>`  
- `public GetDefaultMesh(Game.Prefabs.MeshType type, Game.Rendering.BatchFlags flags, Game.Rendering.GeneratedType generatedType) : UnityEngine.Mesh`  
- `public GetLoadingState(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Rendering.MeshLoadingState>`  
- `public GetShapeStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count) : System.Void`  
- `private GetSizeInMemory(Colossal.IO.AssetDatabase.GeometryAsset geometryAsset) : System.UInt64`  
- `private LoadMeshes(System.UInt64& loadingMemorySize, System.UInt64& neededMemorySize) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public RemoveBatch(Game.Rendering.CustomBatch batch, System.Int32 batchIndex) : System.Void`  
- `private RemoveShapeData(Game.Rendering.BatchMeshSystem+ShapeAllocation[] allocations) : System.Void`  
- `public ReplaceMesh(Unity.Entities.Entity oldMesh, Unity.Entities.Entity newMesh) : System.Void`  
- `private ResizeShapeBuffer() : System.Void`  
- `public SetShapeParameters(UnityEngine.MaterialPropertyBlock customProps, Unity.Entities.Entity sharedMeshEntity, System.Int32 subMeshIndex) : System.Void`  
- `private SetShapeParameters(Game.Rendering.CustomBatch batch, Game.Rendering.BatchMeshSystem+ShapeAllocation[] allocations) : System.Void`  
- `private SetShapeParameters(UnityEngine.MaterialPropertyBlock customProps, Game.Rendering.BatchMeshSystem+ShapeAllocation allocation) : System.Void`  
- `private TryCopyBuffer<T>(Unity.Entities.Entity source, Unity.Entities.Entity target) : System.Void`  
- `private UncacheMeshData(Unity.Entities.Entity mesh, Game.Prefabs.MeshType type) : System.Void`  
- `private UnloadMeshAndGeometryAssets() : System.Void`  
- `private UnloadMeshes(System.UInt64 loadingMemorySize, System.UInt64 neededMemorySize) : System.Void`  
- `public UpdateBatchPriorities() : System.Void`  
- `public UpdateMeshes() : System.Void`  
- `private UpdateMeshesForAddedInstances() : System.Void`  

## Nested types

- `Game.Rendering.BatchMeshSystem+LoadingData`  
- `Game.Rendering.BatchMeshSystem+MeshInfo`  
- `Game.Rendering.BatchMeshSystem+CacheInfo`  
- `Game.Rendering.BatchMeshSystem+ShapeAllocation`  
- `Game.Rendering.BatchMeshSystem+LoadingPriorityJob`  

