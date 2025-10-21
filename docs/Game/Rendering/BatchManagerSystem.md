# Game.Rendering.BatchManagerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class BatchManagerSystem : Game.GameSystemBase, Game.Serialization.IPreDeserialize
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
    private Game.Rendering.BatchDataSystem m_BatchDataSystem;
    private Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem m_TextureStreamingSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Colossal.Rendering.NativeBatchGroups<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> m_NativeBatchGroups;
    private Colossal.Rendering.NativeBatchInstances<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> m_NativeBatchInstances;
    private Colossal.Rendering.NativeSubBatches<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> m_NativeSubBatches;
    private Colossal.Rendering.ManagedBatches<Game.Rendering.OptionalProperties> m_ManagedBatches;
    private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_MaterialProperties;
    private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_ObjectProperties;
    private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_NetProperties;
    private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_LaneProperties;
    private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_ZoneProperties;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_MergeMeshes;
    private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.Int32> m_MergeGroups;
    private Unity.Entities.EntityQuery m_MeshSettingsQuery;
    private System.Boolean m_LastMotionVectorsEnabled;
    private System.Boolean m_LastLodFadeEnabled;
    private System.Boolean m_PropertiesChanged;
    private System.Boolean m_MotionVectorsChanged;
    private System.Boolean m_LodFadeChanged;
    private System.Boolean m_VirtualTexturingChanged;
    private Unity.Jobs.JobHandle m_NativeBatchGroupsReadDependencies;
    private Unity.Jobs.JobHandle m_NativeBatchGroupsWriteDependencies;
    private Unity.Jobs.JobHandle m_NativeBatchInstancesReadDependencies;
    private Unity.Jobs.JobHandle m_NativeBatchInstancesWriteDependencies;
    private Unity.Jobs.JobHandle m_NativeSubBatchesReadDependencies;
    private Unity.Jobs.JobHandle m_NativeSubBatchesWriteDependencies;
    private Unity.Jobs.JobHandle m_MergeDependencies;
    private Game.Rendering.BatchManagerSystem+TypeHandle __TypeHandle;
    public static const System.UInt32 GPU_INSTANCE_MEMORY_DEFAULT;
    public static const System.UInt32 GPU_INSTANCE_MEMORY_INCREMENT;
    public static const System.UInt32 GPU_UPLOADER_CHUNK_SIZE;
    public static const System.UInt32 GPU_UPLOADER_OPERATION_SIZE;
    public static const System.Int32 MAX_GROUP_BATCH_COUNT;

    public BatchManagerSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddNativeBatchGroupsReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddNativeBatchGroupsWriter(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddNativeBatchInstancesReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddNativeBatchInstancesWriter(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddNativeSubBatchesReader(Unity.Jobs.JobHandle jobHandle);
    public System.Void AddNativeSubBatchesWriter(Unity.Jobs.JobHandle jobHandle);
    public System.Boolean CheckPropertyUpdates();
    public Colossal.Rendering.ManagedBatches<Game.Rendering.OptionalProperties> GetManagedBatches();
    public Colossal.Rendering.NativeBatchGroups<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> GetNativeBatchGroups(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    public Colossal.Rendering.NativeBatchInstances<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> GetNativeBatchInstances(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    public Colossal.Rendering.NativeSubBatches<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> GetNativeSubBatches(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    public Game.Rendering.PropertyData GetPropertyData(Game.Rendering.MaterialProperty property);
    public Game.Rendering.PropertyData GetPropertyData(Game.Rendering.ObjectProperty property);
    public Game.Rendering.PropertyData GetPropertyData(Game.Rendering.NetProperty property);
    public Game.Rendering.PropertyData GetPropertyData(Game.Rendering.LaneProperty property);
    public Game.Rendering.PropertyData GetPropertyData(Game.Rendering.ZoneProperty property);
    public System.ValueTuple<System.Int32, System.Int32> GetVTTextureParamBlockID(System.Int32 stackConfigIndex);
    private System.Void InitializeInstanceProperties<T>(Unity.Collections.NativeList`1[[Game.Rendering.PropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& properties, Game.Prefabs.MeshType meshType);
    private System.Void InitializeMaterialProperties<T>(Unity.Collections.NativeList`1[[Game.Rendering.PropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& properties);
    public System.Boolean IsLodFadeEnabled();
    public System.Boolean IsMotionVectorsEnabled();
    public System.Void MergeGroups(Unity.Entities.Entity meshEntity, System.Int32 mergeIndex);
    private System.Void MergeGroups();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    private Unity.Jobs.JobHandle OnPerformCulling(UnityEngine.Rendering.BatchRendererGroup rendererGroup, UnityEngine.Rendering.BatchCullingContext cullingContext, UnityEngine.Rendering.BatchCullingOutput cullingOutput, System.IntPtr userContext);
    protected virtual System.Void OnUpdate();
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void RefreshProperties(System.Boolean propertiesChanged, System.Boolean motionVectorsChanged, System.Boolean lodFadeChanged, System.Boolean virtualTexturingChanged);
    public System.Void VirtualTexturingUpdated();
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem`  

```csharp
private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem;
```

- `private Game.Rendering.BatchDataSystem m_BatchDataSystem`  

```csharp
private Game.Rendering.BatchDataSystem m_BatchDataSystem;
```

- `private Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem m_TextureStreamingSystem`  

```csharp
private Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem m_TextureStreamingSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Colossal.Rendering.NativeBatchGroups<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> m_NativeBatchGroups`  

```csharp
private Colossal.Rendering.NativeBatchGroups<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> m_NativeBatchGroups;
```

- `private Colossal.Rendering.NativeBatchInstances<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> m_NativeBatchInstances`  

```csharp
private Colossal.Rendering.NativeBatchInstances<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> m_NativeBatchInstances;
```

- `private Colossal.Rendering.NativeSubBatches<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> m_NativeSubBatches`  

```csharp
private Colossal.Rendering.NativeSubBatches<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> m_NativeSubBatches;
```

- `private Colossal.Rendering.ManagedBatches<Game.Rendering.OptionalProperties> m_ManagedBatches`  

```csharp
private Colossal.Rendering.ManagedBatches<Game.Rendering.OptionalProperties> m_ManagedBatches;
```

- `private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_MaterialProperties`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_MaterialProperties;
```

- `private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_ObjectProperties`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_ObjectProperties;
```

- `private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_NetProperties`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_NetProperties;
```

- `private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_LaneProperties`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_LaneProperties;
```

- `private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_ZoneProperties`  

```csharp
private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_ZoneProperties;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_MergeMeshes`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_MergeMeshes;
```

- `private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.Int32> m_MergeGroups`  

```csharp
private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.Int32> m_MergeGroups;
```

- `private Unity.Entities.EntityQuery m_MeshSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_MeshSettingsQuery;
```

- `private System.Boolean m_LastMotionVectorsEnabled`  

```csharp
private System.Boolean m_LastMotionVectorsEnabled;
```

- `private System.Boolean m_LastLodFadeEnabled`  

```csharp
private System.Boolean m_LastLodFadeEnabled;
```

- `private System.Boolean m_PropertiesChanged`  

```csharp
private System.Boolean m_PropertiesChanged;
```

- `private System.Boolean m_MotionVectorsChanged`  

```csharp
private System.Boolean m_MotionVectorsChanged;
```

- `private System.Boolean m_LodFadeChanged`  

```csharp
private System.Boolean m_LodFadeChanged;
```

- `private System.Boolean m_VirtualTexturingChanged`  

```csharp
private System.Boolean m_VirtualTexturingChanged;
```

- `private Unity.Jobs.JobHandle m_NativeBatchGroupsReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_NativeBatchGroupsReadDependencies;
```

- `private Unity.Jobs.JobHandle m_NativeBatchGroupsWriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_NativeBatchGroupsWriteDependencies;
```

- `private Unity.Jobs.JobHandle m_NativeBatchInstancesReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_NativeBatchInstancesReadDependencies;
```

- `private Unity.Jobs.JobHandle m_NativeBatchInstancesWriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_NativeBatchInstancesWriteDependencies;
```

- `private Unity.Jobs.JobHandle m_NativeSubBatchesReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_NativeSubBatchesReadDependencies;
```

- `private Unity.Jobs.JobHandle m_NativeSubBatchesWriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_NativeSubBatchesWriteDependencies;
```

- `private Unity.Jobs.JobHandle m_MergeDependencies`  

```csharp
private Unity.Jobs.JobHandle m_MergeDependencies;
```

- `private Game.Rendering.BatchManagerSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.BatchManagerSystem+TypeHandle __TypeHandle;
```

- `public static const System.UInt32 GPU_INSTANCE_MEMORY_DEFAULT`  

```csharp
public static const System.UInt32 GPU_INSTANCE_MEMORY_DEFAULT;
```

- `public static const System.UInt32 GPU_INSTANCE_MEMORY_INCREMENT`  

```csharp
public static const System.UInt32 GPU_INSTANCE_MEMORY_INCREMENT;
```

- `public static const System.UInt32 GPU_UPLOADER_CHUNK_SIZE`  

```csharp
public static const System.UInt32 GPU_UPLOADER_CHUNK_SIZE;
```

- `public static const System.UInt32 GPU_UPLOADER_OPERATION_SIZE`  

```csharp
public static const System.UInt32 GPU_UPLOADER_OPERATION_SIZE;
```

- `public static const System.Int32 MAX_GROUP_BATCH_COUNT`  

```csharp
public static const System.Int32 MAX_GROUP_BATCH_COUNT;
```


## Constructors

- `public BatchManagerSystem()`  

```csharp
public BatchManagerSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddNativeBatchGroupsReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddNativeBatchGroupsReader(Unity.Jobs.JobHandle jobHandle);
```

- `public AddNativeBatchGroupsWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddNativeBatchGroupsWriter(Unity.Jobs.JobHandle jobHandle);
```

- `public AddNativeBatchInstancesReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddNativeBatchInstancesReader(Unity.Jobs.JobHandle jobHandle);
```

- `public AddNativeBatchInstancesWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddNativeBatchInstancesWriter(Unity.Jobs.JobHandle jobHandle);
```

- `public AddNativeSubBatchesReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddNativeSubBatchesReader(Unity.Jobs.JobHandle jobHandle);
```

- `public AddNativeSubBatchesWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddNativeSubBatchesWriter(Unity.Jobs.JobHandle jobHandle);
```

- `public CheckPropertyUpdates() : System.Boolean`  

```csharp
public System.Boolean CheckPropertyUpdates();
```

- `public GetManagedBatches() : Colossal.Rendering.ManagedBatches<Game.Rendering.OptionalProperties>`  

```csharp
public Colossal.Rendering.ManagedBatches<Game.Rendering.OptionalProperties> GetManagedBatches();
```

- `public GetNativeBatchGroups(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Rendering.NativeBatchGroups<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData>`  

```csharp
public Colossal.Rendering.NativeBatchGroups<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> GetNativeBatchGroups(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
```

- `public GetNativeBatchInstances(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Rendering.NativeBatchInstances<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData>`  

```csharp
public Colossal.Rendering.NativeBatchInstances<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> GetNativeBatchInstances(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
```

- `public GetNativeSubBatches(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Rendering.NativeSubBatches<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData>`  

```csharp
public Colossal.Rendering.NativeSubBatches<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> GetNativeSubBatches(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
```

- `public GetPropertyData(Game.Rendering.MaterialProperty property) : Game.Rendering.PropertyData`  

```csharp
public Game.Rendering.PropertyData GetPropertyData(Game.Rendering.MaterialProperty property);
```

- `public GetPropertyData(Game.Rendering.ObjectProperty property) : Game.Rendering.PropertyData`  

```csharp
public Game.Rendering.PropertyData GetPropertyData(Game.Rendering.ObjectProperty property);
```

- `public GetPropertyData(Game.Rendering.NetProperty property) : Game.Rendering.PropertyData`  

```csharp
public Game.Rendering.PropertyData GetPropertyData(Game.Rendering.NetProperty property);
```

- `public GetPropertyData(Game.Rendering.LaneProperty property) : Game.Rendering.PropertyData`  

```csharp
public Game.Rendering.PropertyData GetPropertyData(Game.Rendering.LaneProperty property);
```

- `public GetPropertyData(Game.Rendering.ZoneProperty property) : Game.Rendering.PropertyData`  

```csharp
public Game.Rendering.PropertyData GetPropertyData(Game.Rendering.ZoneProperty property);
```

- `public GetVTTextureParamBlockID(System.Int32 stackConfigIndex) : System.ValueTuple<System.Int32, System.Int32>`  

```csharp
public System.ValueTuple<System.Int32, System.Int32> GetVTTextureParamBlockID(System.Int32 stackConfigIndex);
```

- `private InitializeInstanceProperties<T>(Unity.Collections.NativeList`1[[Game.Rendering.PropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& properties, Game.Prefabs.MeshType meshType) : System.Void`  

```csharp
private System.Void InitializeInstanceProperties<T>(Unity.Collections.NativeList`1[[Game.Rendering.PropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& properties, Game.Prefabs.MeshType meshType);
```

- `private InitializeMaterialProperties<T>(Unity.Collections.NativeList`1[[Game.Rendering.PropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& properties) : System.Void`  

```csharp
private System.Void InitializeMaterialProperties<T>(Unity.Collections.NativeList`1[[Game.Rendering.PropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& properties);
```

- `public IsLodFadeEnabled() : System.Boolean`  

```csharp
public System.Boolean IsLodFadeEnabled();
```

- `public IsMotionVectorsEnabled() : System.Boolean`  

```csharp
public System.Boolean IsMotionVectorsEnabled();
```

- `public MergeGroups(Unity.Entities.Entity meshEntity, System.Int32 mergeIndex) : System.Void`  

```csharp
public System.Void MergeGroups(Unity.Entities.Entity meshEntity, System.Int32 mergeIndex);
```

- `private MergeGroups() : System.Void`  

```csharp
private System.Void MergeGroups();
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `private OnPerformCulling(UnityEngine.Rendering.BatchRendererGroup rendererGroup, UnityEngine.Rendering.BatchCullingContext cullingContext, UnityEngine.Rendering.BatchCullingOutput cullingOutput, System.IntPtr userContext) : Unity.Jobs.JobHandle`  

```csharp
private Unity.Jobs.JobHandle OnPerformCulling(UnityEngine.Rendering.BatchRendererGroup rendererGroup, UnityEngine.Rendering.BatchCullingContext cullingContext, UnityEngine.Rendering.BatchCullingOutput cullingOutput, System.IntPtr userContext);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `private RefreshProperties(System.Boolean propertiesChanged, System.Boolean motionVectorsChanged, System.Boolean lodFadeChanged, System.Boolean virtualTexturingChanged) : System.Void`  

```csharp
private System.Void RefreshProperties(System.Boolean propertiesChanged, System.Boolean motionVectorsChanged, System.Boolean lodFadeChanged, System.Boolean virtualTexturingChanged);
```

- `public VirtualTexturingUpdated() : System.Void`  

```csharp
public System.Void VirtualTexturingUpdated();
```


## Nested types

- `Game.Rendering.BatchManagerSystem+MergeGroupsJob`  
- `Game.Rendering.BatchManagerSystem+MergeCleanupJob`  
- `Game.Rendering.BatchManagerSystem+InitializeLodFadeJob`  
- `Game.Rendering.BatchManagerSystem+AllocateBuffersJob`  
- `Game.Rendering.BatchManagerSystem+GenerateSubBatchesJob`  
- `Game.Rendering.BatchManagerSystem+ActiveGroupData`  
- `Game.Rendering.BatchManagerSystem+AllocateCullingJob`  
- `Game.Rendering.BatchManagerSystem+CullingSplitData`  
- `Game.Rendering.BatchManagerSystem+CullingPlanesJob`  
- `Game.Rendering.BatchManagerSystem+FinalizeCullingJob`  
- `Game.Rendering.BatchManagerSystem+BatchCullingJob`  
- `Game.Rendering.BatchManagerSystem+TypeHandle`  

