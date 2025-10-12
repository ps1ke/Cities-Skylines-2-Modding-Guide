# Game.Rendering.BatchManagerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.Rendering.ManagedBatchSystem m_ManagedBatchSystem`  
- `private Game.Rendering.BatchDataSystem m_BatchDataSystem`  
- `private Colossal.IO.AssetDatabase.VirtualTexturing.TextureStreamingSystem m_TextureStreamingSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Colossal.Rendering.NativeBatchGroups<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> m_NativeBatchGroups`  
- `private Colossal.Rendering.NativeBatchInstances<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> m_NativeBatchInstances`  
- `private Colossal.Rendering.NativeSubBatches<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData> m_NativeSubBatches`  
- `private Colossal.Rendering.ManagedBatches<Game.Rendering.OptionalProperties> m_ManagedBatches`  
- `private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_MaterialProperties`  
- `private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_ObjectProperties`  
- `private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_NetProperties`  
- `private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_LaneProperties`  
- `private Unity.Collections.NativeList<Game.Rendering.PropertyData> m_ZoneProperties`  
- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_MergeMeshes`  
- `private Unity.Collections.NativeParallelMultiHashMap<Unity.Entities.Entity, System.Int32> m_MergeGroups`  
- `private Unity.Entities.EntityQuery m_MeshSettingsQuery`  
- `private System.Boolean m_LastMotionVectorsEnabled`  
- `private System.Boolean m_LastLodFadeEnabled`  
- `private System.Boolean m_PropertiesChanged`  
- `private System.Boolean m_MotionVectorsChanged`  
- `private System.Boolean m_LodFadeChanged`  
- `private System.Boolean m_VirtualTexturingChanged`  
- `private Unity.Jobs.JobHandle m_NativeBatchGroupsReadDependencies`  
- `private Unity.Jobs.JobHandle m_NativeBatchGroupsWriteDependencies`  
- `private Unity.Jobs.JobHandle m_NativeBatchInstancesReadDependencies`  
- `private Unity.Jobs.JobHandle m_NativeBatchInstancesWriteDependencies`  
- `private Unity.Jobs.JobHandle m_NativeSubBatchesReadDependencies`  
- `private Unity.Jobs.JobHandle m_NativeSubBatchesWriteDependencies`  
- `private Unity.Jobs.JobHandle m_MergeDependencies`  
- `private Game.Rendering.BatchManagerSystem+TypeHandle __TypeHandle`  
- `public static const System.UInt32 GPU_INSTANCE_MEMORY_DEFAULT`  
- `public static const System.UInt32 GPU_INSTANCE_MEMORY_INCREMENT`  
- `public static const System.UInt32 GPU_UPLOADER_CHUNK_SIZE`  
- `public static const System.UInt32 GPU_UPLOADER_OPERATION_SIZE`  
- `public static const System.Int32 MAX_GROUP_BATCH_COUNT`  

## Constructors

- `public BatchManagerSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddNativeBatchGroupsReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddNativeBatchGroupsWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddNativeBatchInstancesReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddNativeBatchInstancesWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddNativeSubBatchesReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public AddNativeSubBatchesWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public CheckPropertyUpdates() : System.Boolean`  
- `public GetManagedBatches() : Colossal.Rendering.ManagedBatches<Game.Rendering.OptionalProperties>`  
- `public GetNativeBatchGroups(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Rendering.NativeBatchGroups<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData>`  
- `public GetNativeBatchInstances(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Rendering.NativeBatchInstances<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData>`  
- `public GetNativeSubBatches(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Rendering.NativeSubBatches<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData>`  
- `public GetPropertyData(Game.Rendering.MaterialProperty property) : Game.Rendering.PropertyData`  
- `public GetPropertyData(Game.Rendering.ObjectProperty property) : Game.Rendering.PropertyData`  
- `public GetPropertyData(Game.Rendering.NetProperty property) : Game.Rendering.PropertyData`  
- `public GetPropertyData(Game.Rendering.LaneProperty property) : Game.Rendering.PropertyData`  
- `public GetPropertyData(Game.Rendering.ZoneProperty property) : Game.Rendering.PropertyData`  
- `public GetVTTextureParamBlockID(System.Int32 stackConfigIndex) : System.ValueTuple<System.Int32, System.Int32>`  
- `private InitializeInstanceProperties<T>(Unity.Collections.NativeList`1[[Game.Rendering.PropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& properties, Game.Prefabs.MeshType meshType) : System.Void`  
- `private InitializeMaterialProperties<T>(Unity.Collections.NativeList`1[[Game.Rendering.PropertyData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& properties) : System.Void`  
- `public IsLodFadeEnabled() : System.Boolean`  
- `public IsMotionVectorsEnabled() : System.Boolean`  
- `public MergeGroups(Unity.Entities.Entity meshEntity, System.Int32 mergeIndex) : System.Void`  
- `private MergeGroups() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `private OnPerformCulling(UnityEngine.Rendering.BatchRendererGroup rendererGroup, UnityEngine.Rendering.BatchCullingContext cullingContext, UnityEngine.Rendering.BatchCullingOutput cullingOutput, System.IntPtr userContext) : Unity.Jobs.JobHandle`  
- `protected virtual OnUpdate() : System.Void`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `private RefreshProperties(System.Boolean propertiesChanged, System.Boolean motionVectorsChanged, System.Boolean lodFadeChanged, System.Boolean virtualTexturingChanged) : System.Void`  
- `public VirtualTexturingUpdated() : System.Void`  

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

