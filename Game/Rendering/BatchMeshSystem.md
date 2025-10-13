# Game.Rendering.BatchMeshSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BatchMeshSystem : Game.GameSystemBase
{
    private System.UInt64 <memoryBudget>k__BackingField;
    private System.Boolean <strictMemoryBudget>k__BackingField;
    private System.Boolean <enableMeshLoading>k__BackingField;
    private System.Boolean <forceMeshUnloading>k__BackingField;
    private System.UInt64 <totalSizeInMemory>k__BackingField;
    private System.Int32 <loadingRemaining>k__BackingField;
    private Colossal.IO.AssetDatabase.GeometryAssetLoadingSystem m_GeometryLoadingSystem;
    private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private UnityEngine.Mesh m_DefaultObjectMesh;
    private UnityEngine.Mesh m_DefaultBaseMesh;
    private UnityEngine.Mesh m_DefaultLaneMesh;
    private UnityEngine.Mesh m_ZoneBlockMesh;
    private UnityEngine.Mesh m_ZoneLodMesh;
    private UnityEngine.Mesh m_DefaultEdgeMesh;
    private UnityEngine.Mesh m_DefaultNodeMesh;
    private UnityEngine.Mesh m_DefaultRoundaboutMesh;
    private System.Collections.Generic.List<UnityEngine.Mesh> m_GeneratedMeshes;
    private System.Collections.Generic.List<System.Int32> m_FreeMeshIndices;
    private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.GeometryAsset> m_UnloadGeometryAssets;
    private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.GeometryAsset> m_LoadingGeometries;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Rendering.BatchMeshSystem+CacheInfo> m_CachingMeshes;
    private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Rendering.BatchMeshSystem+MeshInfo> m_MeshInfos;
    private Unity.Collections.NativeList<System.Int32> m_BatchPriority;
    private Unity.Collections.NativeList<Game.Rendering.MeshLoadingState> m_LoadingState;
    private Unity.Collections.NativeList<Game.Rendering.BatchMeshSystem+LoadingData> m_LoadingData;
    private Unity.Collections.NativeList<Game.Rendering.BatchMeshSystem+LoadingData> m_UnloadingData;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_GenerateMeshEntities;
    private Colossal.Collections.NativeHeapAllocator m_ShapeAllocator;
    private Unity.Jobs.JobHandle m_PriorityDeps;
    private Unity.Jobs.JobHandle m_StateDeps;
    private Unity.Jobs.JobHandle m_GenerateMeshDeps;
    private UnityEngine.GraphicsBuffer m_ShapeBuffer;
    private UnityEngine.Mesh+MeshDataArray m_GenerateMeshDataArray;
    private System.Int32 m_ShapeCount;
    private System.Int32 m_PriorityLimit;
    private System.Boolean m_AddMeshes;
    public static const System.String kDisableMeshLoadingKey;
    public static const System.String kForceMeshUnloadingKey;
    public static const System.UInt32 MAX_LOADING_COUNT;
    public static const System.Int32 MIN_BATCH_PRIORITY;
    public static const System.Int32 SHAPEBUFFER_ELEMENT_SIZE;
    public static const System.UInt32 SHAPEBUFFER_MEMORY_DEFAULT;
    public static const System.UInt32 SHAPEBUFFER_MEMORY_INCREMENT;
    public static const System.UInt64 DEFAULT_MEMORY_BUDGET;
    public static const System.Boolean DEFAULT_MEMORY_BUDGET_IS_STRICT;

    public System.UInt64 memoryBudget { get; set; }
    public System.Boolean strictMemoryBudget { get; set; }
    public System.Boolean enableMeshLoading { get; set; }
    public System.Boolean forceMeshUnloading { get; set; }
    public System.UInt64 totalSizeInMemory { get; private set; }
    public System.Int32 loadedMeshCount { get; }
    public System.Int32 loadingRemaining { get; private set; }

    public BatchMeshSystem();

    public System.Void AddBatch(Game.Rendering.CustomBatch batch, System.Int32 batchIndex);
    public System.Void AddBatchPriorityWriter(Unity.Jobs.JobHandle dependencies);
    private System.Void AddCaching(Unity.Entities.Entity entity, Game.Rendering.BatchMeshSystem+CacheInfo cacheInfo);
    public System.Void AddLoadingStateReader(Unity.Jobs.JobHandle dependencies);
    private System.Void AddMeshes();
    private Game.Rendering.BatchMeshSystem+ShapeAllocation[] AddShapeData(Game.Prefabs.RenderPrefab meshPrefab);
    private System.Void BatchPropertyUpdated(Game.Rendering.CustomBatch batch);
    private System.Void CacheMeshData(Game.Prefabs.RenderPrefab meshPrefab, Colossal.IO.AssetDatabase.GeometryAsset asset, Unity.Entities.Entity entity, Game.Prefabs.MeshType type);
    private System.Void CacheMeshData(UnityEngine.Mesh mesh, Unity.Entities.Entity entity, Game.Prefabs.MeshType type);
    public System.Void CompleteCaching();
    private System.Void CompleteCaching(Unity.Entities.Entity entity);
    private System.Void CompleteCaching(Unity.Entities.Entity entity, Game.Rendering.BatchMeshSystem+CacheInfo cacheInfo);
    public System.Void CompleteMeshes();
    private System.UInt64 EstimateSizeInMemory(Game.Prefabs.RenderPrefab meshPrefab);
    private System.Void GenerateMeshes();
    public Unity.Collections.NativeList<System.Int32> GetBatchPriority(Unity.Jobs.JobHandle& dependencies);
    public UnityEngine.Mesh GetDefaultMesh(Game.Prefabs.MeshType type, Game.Rendering.BatchFlags flags, Game.Rendering.GeneratedType generatedType);
    public Unity.Collections.NativeList<Game.Rendering.MeshLoadingState> GetLoadingState(Unity.Jobs.JobHandle& dependencies);
    public System.Void GetShapeStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count);
    private System.UInt64 GetSizeInMemory(Colossal.IO.AssetDatabase.GeometryAsset geometryAsset);
    private System.Void LoadMeshes(System.UInt64& loadingMemorySize, System.UInt64& neededMemorySize);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void RemoveBatch(Game.Rendering.CustomBatch batch, System.Int32 batchIndex);
    private System.Void RemoveShapeData(Game.Rendering.BatchMeshSystem+ShapeAllocation[] allocations);
    public System.Void ReplaceMesh(Unity.Entities.Entity oldMesh, Unity.Entities.Entity newMesh);
    private System.Void ResizeShapeBuffer();
    public System.Void SetShapeParameters(UnityEngine.MaterialPropertyBlock customProps, Unity.Entities.Entity sharedMeshEntity, System.Int32 subMeshIndex);
    private System.Void SetShapeParameters(Game.Rendering.CustomBatch batch, Game.Rendering.BatchMeshSystem+ShapeAllocation[] allocations);
    private System.Void SetShapeParameters(UnityEngine.MaterialPropertyBlock customProps, Game.Rendering.BatchMeshSystem+ShapeAllocation allocation);
    private System.Void TryCopyBuffer<T>(Unity.Entities.Entity source, Unity.Entities.Entity target);
    private System.Void UncacheMeshData(Unity.Entities.Entity mesh, Game.Prefabs.MeshType type);
    private System.Void UnloadMeshAndGeometryAssets();
    private System.Void UnloadMeshes(System.UInt64 loadingMemorySize, System.UInt64 neededMemorySize);
    public System.Void UpdateBatchPriorities();
    public System.Void UpdateMeshes();
    private System.Void UpdateMeshesForAddedInstances();
}
```


## Fields

- `private System.UInt64 <memoryBudget>k__BackingField`  

```csharp
private System.UInt64 <memoryBudget>k__BackingField;
```

- `private System.Boolean <strictMemoryBudget>k__BackingField`  

```csharp
private System.Boolean <strictMemoryBudget>k__BackingField;
```

- `private System.Boolean <enableMeshLoading>k__BackingField`  

```csharp
private System.Boolean <enableMeshLoading>k__BackingField;
```

- `private System.Boolean <forceMeshUnloading>k__BackingField`  

```csharp
private System.Boolean <forceMeshUnloading>k__BackingField;
```

- `private System.UInt64 <totalSizeInMemory>k__BackingField`  

```csharp
private System.UInt64 <totalSizeInMemory>k__BackingField;
```

- `private System.Int32 <loadingRemaining>k__BackingField`  

```csharp
private System.Int32 <loadingRemaining>k__BackingField;
```

- `private Colossal.IO.AssetDatabase.GeometryAssetLoadingSystem m_GeometryLoadingSystem`  

```csharp
private Colossal.IO.AssetDatabase.GeometryAssetLoadingSystem m_GeometryLoadingSystem;
```

- `private Game.Rendering.BatchManagerSystem m_BatchManagerSystem`  

```csharp
private Game.Rendering.BatchManagerSystem m_BatchManagerSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private UnityEngine.Mesh m_DefaultObjectMesh`  

```csharp
private UnityEngine.Mesh m_DefaultObjectMesh;
```

- `private UnityEngine.Mesh m_DefaultBaseMesh`  

```csharp
private UnityEngine.Mesh m_DefaultBaseMesh;
```

- `private UnityEngine.Mesh m_DefaultLaneMesh`  

```csharp
private UnityEngine.Mesh m_DefaultLaneMesh;
```

- `private UnityEngine.Mesh m_ZoneBlockMesh`  

```csharp
private UnityEngine.Mesh m_ZoneBlockMesh;
```

- `private UnityEngine.Mesh m_ZoneLodMesh`  

```csharp
private UnityEngine.Mesh m_ZoneLodMesh;
```

- `private UnityEngine.Mesh m_DefaultEdgeMesh`  

```csharp
private UnityEngine.Mesh m_DefaultEdgeMesh;
```

- `private UnityEngine.Mesh m_DefaultNodeMesh`  

```csharp
private UnityEngine.Mesh m_DefaultNodeMesh;
```

- `private UnityEngine.Mesh m_DefaultRoundaboutMesh`  

```csharp
private UnityEngine.Mesh m_DefaultRoundaboutMesh;
```

- `private System.Collections.Generic.List<UnityEngine.Mesh> m_GeneratedMeshes`  

```csharp
private System.Collections.Generic.List<UnityEngine.Mesh> m_GeneratedMeshes;
```

- `private System.Collections.Generic.List<System.Int32> m_FreeMeshIndices`  

```csharp
private System.Collections.Generic.List<System.Int32> m_FreeMeshIndices;
```

- `private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.GeometryAsset> m_UnloadGeometryAssets`  

```csharp
private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.GeometryAsset> m_UnloadGeometryAssets;
```

- `private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.GeometryAsset> m_LoadingGeometries`  

```csharp
private System.Collections.Generic.HashSet<Colossal.IO.AssetDatabase.GeometryAsset> m_LoadingGeometries;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Rendering.BatchMeshSystem+CacheInfo> m_CachingMeshes`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Rendering.BatchMeshSystem+CacheInfo> m_CachingMeshes;
```

- `private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Rendering.BatchMeshSystem+MeshInfo> m_MeshInfos`  

```csharp
private System.Collections.Generic.Dictionary<Unity.Entities.Entity, Game.Rendering.BatchMeshSystem+MeshInfo> m_MeshInfos;
```

- `private Unity.Collections.NativeList<System.Int32> m_BatchPriority`  

```csharp
private Unity.Collections.NativeList<System.Int32> m_BatchPriority;
```

- `private Unity.Collections.NativeList<Game.Rendering.MeshLoadingState> m_LoadingState`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.MeshLoadingState> m_LoadingState;
```

- `private Unity.Collections.NativeList<Game.Rendering.BatchMeshSystem+LoadingData> m_LoadingData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.BatchMeshSystem+LoadingData> m_LoadingData;
```

- `private Unity.Collections.NativeList<Game.Rendering.BatchMeshSystem+LoadingData> m_UnloadingData`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.BatchMeshSystem+LoadingData> m_UnloadingData;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_GenerateMeshEntities`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_GenerateMeshEntities;
```

- `private Colossal.Collections.NativeHeapAllocator m_ShapeAllocator`  

```csharp
private Colossal.Collections.NativeHeapAllocator m_ShapeAllocator;
```

- `private Unity.Jobs.JobHandle m_PriorityDeps`  

```csharp
private Unity.Jobs.JobHandle m_PriorityDeps;
```

- `private Unity.Jobs.JobHandle m_StateDeps`  

```csharp
private Unity.Jobs.JobHandle m_StateDeps;
```

- `private Unity.Jobs.JobHandle m_GenerateMeshDeps`  

```csharp
private Unity.Jobs.JobHandle m_GenerateMeshDeps;
```

- `private UnityEngine.GraphicsBuffer m_ShapeBuffer`  

```csharp
private UnityEngine.GraphicsBuffer m_ShapeBuffer;
```

- `private UnityEngine.Mesh+MeshDataArray m_GenerateMeshDataArray`  

```csharp
private UnityEngine.Mesh+MeshDataArray m_GenerateMeshDataArray;
```

- `private System.Int32 m_ShapeCount`  

```csharp
private System.Int32 m_ShapeCount;
```

- `private System.Int32 m_PriorityLimit`  

```csharp
private System.Int32 m_PriorityLimit;
```

- `private System.Boolean m_AddMeshes`  

```csharp
private System.Boolean m_AddMeshes;
```

- `public static const System.String kDisableMeshLoadingKey`  

```csharp
public static const System.String kDisableMeshLoadingKey;
```

- `public static const System.String kForceMeshUnloadingKey`  

```csharp
public static const System.String kForceMeshUnloadingKey;
```

- `public static const System.UInt32 MAX_LOADING_COUNT`  

```csharp
public static const System.UInt32 MAX_LOADING_COUNT;
```

- `public static const System.Int32 MIN_BATCH_PRIORITY`  

```csharp
public static const System.Int32 MIN_BATCH_PRIORITY;
```

- `public static const System.Int32 SHAPEBUFFER_ELEMENT_SIZE`  

```csharp
public static const System.Int32 SHAPEBUFFER_ELEMENT_SIZE;
```

- `public static const System.UInt32 SHAPEBUFFER_MEMORY_DEFAULT`  

```csharp
public static const System.UInt32 SHAPEBUFFER_MEMORY_DEFAULT;
```

- `public static const System.UInt32 SHAPEBUFFER_MEMORY_INCREMENT`  

```csharp
public static const System.UInt32 SHAPEBUFFER_MEMORY_INCREMENT;
```

- `public static const System.UInt64 DEFAULT_MEMORY_BUDGET`  

```csharp
public static const System.UInt64 DEFAULT_MEMORY_BUDGET;
```

- `public static const System.Boolean DEFAULT_MEMORY_BUDGET_IS_STRICT`  

```csharp
public static const System.Boolean DEFAULT_MEMORY_BUDGET_IS_STRICT;
```


## Properties

- `public System.UInt64 memoryBudget { get; set }`  

```csharp
public System.UInt64 memoryBudget { get; set; }
```

- `public System.Boolean strictMemoryBudget { get; set }`  

```csharp
public System.Boolean strictMemoryBudget { get; set; }
```

- `public System.Boolean enableMeshLoading { get; set }`  

```csharp
public System.Boolean enableMeshLoading { get; set; }
```

- `public System.Boolean forceMeshUnloading { get; set }`  

```csharp
public System.Boolean forceMeshUnloading { get; set; }
```

- `public System.UInt64 totalSizeInMemory { get; private set }`  

```csharp
public System.UInt64 totalSizeInMemory { get; private set; }
```

- `public System.Int32 loadedMeshCount { get }`  

```csharp
public System.Int32 loadedMeshCount { get; }
```

- `public System.Int32 loadingRemaining { get; private set }`  

```csharp
public System.Int32 loadingRemaining { get; private set; }
```


## Constructors

- `public BatchMeshSystem()`  

```csharp
public BatchMeshSystem();
```


## Methods

- `public AddBatch(Game.Rendering.CustomBatch batch, System.Int32 batchIndex) : System.Void`  

```csharp
public System.Void AddBatch(Game.Rendering.CustomBatch batch, System.Int32 batchIndex);
```

- `public AddBatchPriorityWriter(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public System.Void AddBatchPriorityWriter(Unity.Jobs.JobHandle dependencies);
```

- `private AddCaching(Unity.Entities.Entity entity, Game.Rendering.BatchMeshSystem+CacheInfo cacheInfo) : System.Void`  

```csharp
private System.Void AddCaching(Unity.Entities.Entity entity, Game.Rendering.BatchMeshSystem+CacheInfo cacheInfo);
```

- `public AddLoadingStateReader(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public System.Void AddLoadingStateReader(Unity.Jobs.JobHandle dependencies);
```

- `private AddMeshes() : System.Void`  

```csharp
private System.Void AddMeshes();
```

- `private AddShapeData(Game.Prefabs.RenderPrefab meshPrefab) : Game.Rendering.BatchMeshSystem+ShapeAllocation[]`  

```csharp
private Game.Rendering.BatchMeshSystem+ShapeAllocation[] AddShapeData(Game.Prefabs.RenderPrefab meshPrefab);
```

- `private BatchPropertyUpdated(Game.Rendering.CustomBatch batch) : System.Void`  

```csharp
private System.Void BatchPropertyUpdated(Game.Rendering.CustomBatch batch);
```

- `private CacheMeshData(Game.Prefabs.RenderPrefab meshPrefab, Colossal.IO.AssetDatabase.GeometryAsset asset, Unity.Entities.Entity entity, Game.Prefabs.MeshType type) : System.Void`  

```csharp
private System.Void CacheMeshData(Game.Prefabs.RenderPrefab meshPrefab, Colossal.IO.AssetDatabase.GeometryAsset asset, Unity.Entities.Entity entity, Game.Prefabs.MeshType type);
```

- `private CacheMeshData(UnityEngine.Mesh mesh, Unity.Entities.Entity entity, Game.Prefabs.MeshType type) : System.Void`  

```csharp
private System.Void CacheMeshData(UnityEngine.Mesh mesh, Unity.Entities.Entity entity, Game.Prefabs.MeshType type);
```

- `public CompleteCaching() : System.Void`  

```csharp
public System.Void CompleteCaching();
```

- `private CompleteCaching(Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void CompleteCaching(Unity.Entities.Entity entity);
```

- `private CompleteCaching(Unity.Entities.Entity entity, Game.Rendering.BatchMeshSystem+CacheInfo cacheInfo) : System.Void`  

```csharp
private System.Void CompleteCaching(Unity.Entities.Entity entity, Game.Rendering.BatchMeshSystem+CacheInfo cacheInfo);
```

- `public CompleteMeshes() : System.Void`  

```csharp
public System.Void CompleteMeshes();
```

- `private EstimateSizeInMemory(Game.Prefabs.RenderPrefab meshPrefab) : System.UInt64`  

```csharp
private System.UInt64 EstimateSizeInMemory(Game.Prefabs.RenderPrefab meshPrefab);
```

- `private GenerateMeshes() : System.Void`  

```csharp
private System.Void GenerateMeshes();
```

- `public GetBatchPriority(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<System.Int32>`  

```csharp
public Unity.Collections.NativeList<System.Int32> GetBatchPriority(Unity.Jobs.JobHandle& dependencies);
```

- `public GetDefaultMesh(Game.Prefabs.MeshType type, Game.Rendering.BatchFlags flags, Game.Rendering.GeneratedType generatedType) : UnityEngine.Mesh`  

```csharp
public UnityEngine.Mesh GetDefaultMesh(Game.Prefabs.MeshType type, Game.Rendering.BatchFlags flags, Game.Rendering.GeneratedType generatedType);
```

- `public GetLoadingState(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Rendering.MeshLoadingState>`  

```csharp
public Unity.Collections.NativeList<Game.Rendering.MeshLoadingState> GetLoadingState(Unity.Jobs.JobHandle& dependencies);
```

- `public GetShapeStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count) : System.Void`  

```csharp
public System.Void GetShapeStats(System.UInt32& allocatedSize, System.UInt32& bufferSize, System.UInt32& count);
```

- `private GetSizeInMemory(Colossal.IO.AssetDatabase.GeometryAsset geometryAsset) : System.UInt64`  

```csharp
private System.UInt64 GetSizeInMemory(Colossal.IO.AssetDatabase.GeometryAsset geometryAsset);
```

- `private LoadMeshes(System.UInt64& loadingMemorySize, System.UInt64& neededMemorySize) : System.Void`  

```csharp
private System.Void LoadMeshes(System.UInt64& loadingMemorySize, System.UInt64& neededMemorySize);
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

- `public RemoveBatch(Game.Rendering.CustomBatch batch, System.Int32 batchIndex) : System.Void`  

```csharp
public System.Void RemoveBatch(Game.Rendering.CustomBatch batch, System.Int32 batchIndex);
```

- `private RemoveShapeData(Game.Rendering.BatchMeshSystem+ShapeAllocation[] allocations) : System.Void`  

```csharp
private System.Void RemoveShapeData(Game.Rendering.BatchMeshSystem+ShapeAllocation[] allocations);
```

- `public ReplaceMesh(Unity.Entities.Entity oldMesh, Unity.Entities.Entity newMesh) : System.Void`  

```csharp
public System.Void ReplaceMesh(Unity.Entities.Entity oldMesh, Unity.Entities.Entity newMesh);
```

- `private ResizeShapeBuffer() : System.Void`  

```csharp
private System.Void ResizeShapeBuffer();
```

- `public SetShapeParameters(UnityEngine.MaterialPropertyBlock customProps, Unity.Entities.Entity sharedMeshEntity, System.Int32 subMeshIndex) : System.Void`  

```csharp
public System.Void SetShapeParameters(UnityEngine.MaterialPropertyBlock customProps, Unity.Entities.Entity sharedMeshEntity, System.Int32 subMeshIndex);
```

- `private SetShapeParameters(Game.Rendering.CustomBatch batch, Game.Rendering.BatchMeshSystem+ShapeAllocation[] allocations) : System.Void`  

```csharp
private System.Void SetShapeParameters(Game.Rendering.CustomBatch batch, Game.Rendering.BatchMeshSystem+ShapeAllocation[] allocations);
```

- `private SetShapeParameters(UnityEngine.MaterialPropertyBlock customProps, Game.Rendering.BatchMeshSystem+ShapeAllocation allocation) : System.Void`  

```csharp
private System.Void SetShapeParameters(UnityEngine.MaterialPropertyBlock customProps, Game.Rendering.BatchMeshSystem+ShapeAllocation allocation);
```

- `private TryCopyBuffer<T>(Unity.Entities.Entity source, Unity.Entities.Entity target) : System.Void`  

```csharp
private System.Void TryCopyBuffer<T>(Unity.Entities.Entity source, Unity.Entities.Entity target);
```

- `private UncacheMeshData(Unity.Entities.Entity mesh, Game.Prefabs.MeshType type) : System.Void`  

```csharp
private System.Void UncacheMeshData(Unity.Entities.Entity mesh, Game.Prefabs.MeshType type);
```

- `private UnloadMeshAndGeometryAssets() : System.Void`  

```csharp
private System.Void UnloadMeshAndGeometryAssets();
```

- `private UnloadMeshes(System.UInt64 loadingMemorySize, System.UInt64 neededMemorySize) : System.Void`  

```csharp
private System.Void UnloadMeshes(System.UInt64 loadingMemorySize, System.UInt64 neededMemorySize);
```

- `public UpdateBatchPriorities() : System.Void`  

```csharp
public System.Void UpdateBatchPriorities();
```

- `public UpdateMeshes() : System.Void`  

```csharp
public System.Void UpdateMeshes();
```

- `private UpdateMeshesForAddedInstances() : System.Void`  

```csharp
private System.Void UpdateMeshesForAddedInstances();
```


## Nested types

- `Game.Rendering.BatchMeshSystem+LoadingData`  
- `Game.Rendering.BatchMeshSystem+MeshInfo`  
- `Game.Rendering.BatchMeshSystem+CacheInfo`  
- `Game.Rendering.BatchMeshSystem+ShapeAllocation`  
- `Game.Rendering.BatchMeshSystem+LoadingPriorityJob`  

