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
[Preserve]
	public BatchManagerSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `public AddNativeBatchGroupsReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddNativeBatchGroupsReader(JobHandle jobHandle)
	{
		m_NativeBatchGroupsReadDependencies = JobHandle.CombineDependencies(m_NativeBatchGroupsReadDependencies, jobHandle);
	}
```

- `public AddNativeBatchGroupsWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddNativeBatchGroupsWriter(JobHandle jobHandle)
	{
		m_NativeBatchGroupsWriteDependencies = jobHandle;
	}
```

- `public AddNativeBatchInstancesReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddNativeBatchInstancesReader(JobHandle jobHandle)
	{
		m_NativeBatchInstancesReadDependencies = JobHandle.CombineDependencies(m_NativeBatchInstancesReadDependencies, jobHandle);
	}
```

- `public AddNativeBatchInstancesWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddNativeBatchInstancesWriter(JobHandle jobHandle)
	{
		m_NativeBatchInstancesWriteDependencies = jobHandle;
	}
```

- `public AddNativeSubBatchesReader(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddNativeSubBatchesReader(JobHandle jobHandle)
	{
		m_NativeSubBatchesReadDependencies = JobHandle.CombineDependencies(m_NativeSubBatchesReadDependencies, jobHandle);
	}
```

- `public AddNativeSubBatchesWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddNativeSubBatchesWriter(JobHandle jobHandle)
	{
		m_NativeSubBatchesWriteDependencies = jobHandle;
	}
```

- `public CheckPropertyUpdates() : System.Boolean`  

```csharp
public bool CheckPropertyUpdates()
	{
		bool motionVectors = m_RenderingSystem.motionVectors;
		if (motionVectors != m_LastMotionVectorsEnabled)
		{
			m_LastMotionVectorsEnabled = motionVectors;
			m_MotionVectorsChanged = true;
		}
		bool lodCrossFade = m_RenderingSystem.lodCrossFade;
		if (lodCrossFade != m_LastLodFadeEnabled)
		{
			m_LastLodFadeEnabled = lodCrossFade;
			m_LodFadeChanged = true;
		}
		if (!m_PropertiesChanged && !m_MotionVectorsChanged && !m_LodFadeChanged)
		{
			return m_VirtualTexturingChanged;
		}
		return true;
	}
```

- `public GetManagedBatches() : Colossal.Rendering.ManagedBatches<Game.Rendering.OptionalProperties>`  

```csharp
public ManagedBatches<OptionalProperties> GetManagedBatches()
	{
		return m_ManagedBatches;
	}
```

- `public GetNativeBatchGroups(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Rendering.NativeBatchGroups<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData>`  

```csharp
public NativeBatchGroups<CullingData, GroupData, BatchData, InstanceData> GetNativeBatchGroups(bool readOnly, out JobHandle dependencies)
	{
		dependencies = (readOnly ? m_NativeBatchGroupsWriteDependencies : JobHandle.CombineDependencies(m_NativeBatchGroupsReadDependencies, m_NativeBatchGroupsWriteDependencies));
		return m_NativeBatchGroups;
	}
```

- `public GetNativeBatchInstances(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Rendering.NativeBatchInstances<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData>`  

```csharp
public NativeBatchInstances<CullingData, GroupData, BatchData, InstanceData> GetNativeBatchInstances(bool readOnly, out JobHandle dependencies)
	{
		dependencies = (readOnly ? m_NativeBatchInstancesWriteDependencies : JobHandle.CombineDependencies(m_NativeBatchInstancesReadDependencies, m_NativeBatchInstancesWriteDependencies));
		return m_NativeBatchInstances;
	}
```

- `public GetNativeSubBatches(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Colossal.Rendering.NativeSubBatches<Game.Rendering.CullingData, Game.Rendering.GroupData, Game.Rendering.BatchData, Game.Rendering.InstanceData>`  

```csharp
public NativeSubBatches<CullingData, GroupData, BatchData, InstanceData> GetNativeSubBatches(bool readOnly, out JobHandle dependencies)
	{
		dependencies = (readOnly ? m_NativeSubBatchesWriteDependencies : JobHandle.CombineDependencies(m_NativeSubBatchesReadDependencies, m_NativeSubBatchesWriteDependencies));
		return m_NativeSubBatches;
	}
```

- `public GetPropertyData(Game.Rendering.MaterialProperty property) : Game.Rendering.PropertyData`  

```csharp
public PropertyData GetPropertyData(ZoneProperty property)
	{
		return m_ZoneProperties[(int)property];
	}
```

- `public GetPropertyData(Game.Rendering.ObjectProperty property) : Game.Rendering.PropertyData`  

```csharp
public PropertyData GetPropertyData(ZoneProperty property)
	{
		return m_ZoneProperties[(int)property];
	}
```

- `public GetPropertyData(Game.Rendering.NetProperty property) : Game.Rendering.PropertyData`  

```csharp
public PropertyData GetPropertyData(ZoneProperty property)
	{
		return m_ZoneProperties[(int)property];
	}
```

- `public GetPropertyData(Game.Rendering.LaneProperty property) : Game.Rendering.PropertyData`  

```csharp
public PropertyData GetPropertyData(ZoneProperty property)
	{
		return m_ZoneProperties[(int)property];
	}
```

- `public GetPropertyData(Game.Rendering.ZoneProperty property) : Game.Rendering.PropertyData`  

```csharp
public PropertyData GetPropertyData(ZoneProperty property)
	{
		return m_ZoneProperties[(int)property];
	}
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
public bool IsLodFadeEnabled()
	{
		return m_LastLodFadeEnabled;
	}
```

- `public IsMotionVectorsEnabled() : System.Boolean`  

```csharp
public bool IsMotionVectorsEnabled()
	{
		return m_LastMotionVectorsEnabled;
	}
```

- `public MergeGroups(Unity.Entities.Entity meshEntity, System.Int32 mergeIndex) : System.Void`  

```csharp
private void MergeGroups()
	{
		JobHandle dependencies;
		NativeBatchGroups<CullingData, GroupData, BatchData, InstanceData> nativeBatchGroups = GetNativeBatchGroups(readOnly: false, out dependencies);
		JobHandle dependencies2;
		NativeBatchInstances<CullingData, GroupData, BatchData, InstanceData> nativeBatchInstances = GetNativeBatchInstances(readOnly: false, out dependencies2);
		JobHandle dependencies3;
		NativeSubBatches<CullingData, GroupData, BatchData, InstanceData> nativeSubBatches = GetNativeSubBatches(readOnly: false, out dependencies3);
		NativeBatchGroups<CullingData, GroupData, BatchData, InstanceData>.GroupUpdater groupUpdater = nativeBatchGroups.BeginGroupUpdate(Allocator.TempJob);
		NativeBatchInstances<CullingData, GroupData, BatchData, InstanceData>.InstanceUpdater instanceUpdater = nativeBatchInstances.BeginInstanceUpdate(Allocator.TempJob);
		MergeGroupsJob jobData = new MergeGroupsJob
		{
			m_MeshBatches = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshBatch_RW_BufferLookup, ref base.CheckedStateRef),
			m_BatchGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_BatchGroup_RW_BufferLookup, ref base.CheckedStateRef),
			m_MergeMeshes = m_MergeMeshes,
			m_MergeGroups = m_MergeGroups,
			m_BatchGroupUpdater = groupUpdater.AsParallel(int.MaxValue),
			m_BatchInstanceUpdater = instanceUpdater.AsParallel(int.MaxValue)
		};
		MergeCleanupJob jobData2 = new MergeCleanupJob
		{
			m_MergeMeshes = m_MergeMeshes,
			m_MergeGroups = m_MergeGroups
		};
		JobHandle jobHandle = IJobParallelForExtensions.Schedule(jobData, m_MergeMeshes.Length, 1, JobHandle.CombineDependencies(base.Dependency, dependencies, dependencies2));
		JobHandle mergeDependencies = IJobExtensions.Schedule(jobData2, jobHandle);
		JobHandle jobHandle2 = nativeBatchGroups.EndGroupUpdate(groupUpdater, jobHandle);
		JobHandle jobHandle3 = nativeBatchInstances.EndInstanceUpdate(instanceUpdater, JobHandle.CombineDependencies(jobHandle, dependencies3), nativeSubBatches);
		AddNativeBatchGroupsWriter(jobHandle2);
		AddNativeBatchInstancesWriter(jobHandle3);
		AddNativeSubBatchesWriter(jobHandle3);
		base.Dependency = jobHandle;
		m_MergeDependencies = mergeDependencies;
	}
```

- `private MergeGroups() : System.Void`  

```csharp
private void MergeGroups()
	{
		JobHandle dependencies;
		NativeBatchGroups<CullingData, GroupData, BatchData, InstanceData> nativeBatchGroups = GetNativeBatchGroups(readOnly: false, out dependencies);
		JobHandle dependencies2;
		NativeBatchInstances<CullingData, GroupData, BatchData, InstanceData> nativeBatchInstances = GetNativeBatchInstances(readOnly: false, out dependencies2);
		JobHandle dependencies3;
		NativeSubBatches<CullingData, GroupData, BatchData, InstanceData> nativeSubBatches = GetNativeSubBatches(readOnly: false, out dependencies3);
		NativeBatchGroups<CullingData, GroupData, BatchData, InstanceData>.GroupUpdater groupUpdater = nativeBatchGroups.BeginGroupUpdate(Allocator.TempJob);
		NativeBatchInstances<CullingData, GroupData, BatchData, InstanceData>.InstanceUpdater instanceUpdater = nativeBatchInstances.BeginInstanceUpdate(Allocator.TempJob);
		MergeGroupsJob jobData = new MergeGroupsJob
		{
			m_MeshBatches = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Rendering_MeshBatch_RW_BufferLookup, ref base.CheckedStateRef),
			m_BatchGroups = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_BatchGroup_RW_BufferLookup, ref base.CheckedStateRef),
			m_MergeMeshes = m_MergeMeshes,
			m_MergeGroups = m_MergeGroups,
			m_BatchGroupUpdater = groupUpdater.AsParallel(int.MaxValue),
			m_BatchInstanceUpdater = instanceUpdater.AsParallel(int.MaxValue)
		};
		MergeCleanupJob jobData2 = new MergeCleanupJob
		{
			m_MergeMeshes = m_MergeMeshes,
			m_MergeGroups = m_MergeGroups
		};
		JobHandle jobHandle = IJobParallelForExtensions.Schedule(jobData, m_MergeMeshes.Length, 1, JobHandle.CombineDependencies(base.Dependency, dependencies, dependencies2));
		JobHandle mergeDependencies = IJobExtensions.Schedule(jobData2, jobHandle);
		JobHandle jobHandle2 = nativeBatchGroups.EndGroupUpdate(groupUpdater, jobHandle);
		JobHandle jobHandle3 = nativeBatchInstances.EndInstanceUpdate(instanceUpdater, JobHandle.CombineDependencies(jobHandle, dependencies3), nativeSubBatches);
		AddNativeBatchGroupsWriter(jobHandle2);
		AddNativeBatchInstancesWriter(jobHandle3);
		AddNativeSubBatchesWriter(jobHandle3);
		base.Dependency = jobHandle;
		m_MergeDependencies = mergeDependencies;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_ManagedBatchSystem = base.World.GetOrCreateSystemManaged<ManagedBatchSystem>();
		m_BatchDataSystem = base.World.GetOrCreateSystemManaged<BatchDataSystem>();
		m_TextureStreamingSystem = base.World.GetOrCreateSystemManaged<TextureStreamingSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_NativeBatchGroups = new NativeBatchGroups<CullingData, GroupData, BatchData, InstanceData>(67108864u, 65536u, Allocator.Persistent);
		m_NativeBatchInstances = new NativeBatchInstances<CullingData, GroupData, BatchData, InstanceData>(m_NativeBatchGroups);
		m_NativeSubBatches = new NativeSubBatches<CullingData, GroupData, BatchData, InstanceData>(m_NativeBatchGroups);
		m_ManagedBatches = ManagedBatches<OptionalProperties>.Create(m_NativeBatchInstances, OnPerformCulling, 2097152u, new OptionalProperties(BatchFlags.MotionVectors, MeshType.Object));
		InitializeMaterialProperties<MaterialProperty>(out m_MaterialProperties);
		InitializeInstanceProperties<ObjectProperty>(out m_ObjectProperties, MeshType.Object);
		InitializeInstanceProperties<NetProperty>(out m_NetProperties, MeshType.Net);
		InitializeInstanceProperties<LaneProperty>(out m_LaneProperties, MeshType.Lane);
		InitializeInstanceProperties<ZoneProperty>(out m_ZoneProperties, MeshType.Zone);
		m_MergeMeshes = new NativeList<Entity>(10, Allocator.Persistent);
		m_MergeGroups = new NativeParallelMultiHashMap<Entity, int>(10, Allocator.Persistent);
		m_MeshSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<MeshSettingsData>());
		m_LastMotionVectorsEnabled = m_RenderingSystem.motionVectors;
		m_LastLodFadeEnabled = m_RenderingSystem.lodCrossFade;
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_NativeBatchGroupsReadDependencies.Complete();
		m_NativeBatchGroupsWriteDependencies.Complete();
		m_NativeBatchInstancesReadDependencies.Complete();
		m_NativeBatchInstancesWriteDependencies.Complete();
		m_NativeSubBatchesReadDependencies.Complete();
		m_NativeSubBatchesWriteDependencies.Complete();
		m_MergeDependencies.Complete();
		m_ManagedBatches.EndUpload(m_NativeBatchInstances);
		m_ManagedBatches.Dispose();
		m_NativeSubBatches.Dispose();
		m_NativeBatchInstances.Dispose();
		m_NativeBatchGroups.Dispose();
		m_MaterialProperties.Dispose();
		m_ObjectProperties.Dispose();
		m_NetProperties.Dispose();
		m_LaneProperties.Dispose();
		m_ZoneProperties.Dispose();
		m_MergeMeshes.Dispose();
		m_MergeGroups.Dispose();
		base.OnDestroy();
	}
```

- `private OnPerformCulling(UnityEngine.Rendering.BatchRendererGroup rendererGroup, UnityEngine.Rendering.BatchCullingContext cullingContext, UnityEngine.Rendering.BatchCullingOutput cullingOutput, System.IntPtr userContext) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle OnPerformCulling(BatchRendererGroup rendererGroup, BatchCullingContext cullingContext, BatchCullingOutput cullingOutput, IntPtr userContext)
	{
		JobHandle dependencies;
		NativeBatchGroups<CullingData, GroupData, BatchData, InstanceData> nativeBatchGroups = GetNativeBatchGroups(readOnly: true, out dependencies);
		JobHandle dependencies2;
		NativeBatchInstances<CullingData, GroupData, BatchData, InstanceData> nativeBatchInstances = GetNativeBatchInstances(readOnly: true, out dependencies2);
		JobHandle dependencies3;
		NativeSubBatches<CullingData, GroupData, BatchData, InstanceData> nativeSubBatches = GetNativeSubBatches(readOnly: true, out dependencies3);
		dependencies2.Complete();
		int activeGroupCount = nativeBatchInstances.GetActiveGroupCount();
		int maxSplitBatchCount = (cullingContext.cullingSplits.Length << 1) - 1;
		NativeArray<ActiveGroupData> activeGroupData = new NativeArray<ActiveGroupData>(activeGroupCount, Allocator.TempJob, NativeArrayOptions.UninitializedMemory);
		NativeList<CullingSplitData> splitData = new NativeList<CullingSplitData>(cullingContext.cullingSplits.Length, Allocator.TempJob);
		NativeList<FrustumPlanes.PlanePacket4> nativeList = new NativeList<FrustumPlanes.PlanePacket4>(FrustumPlanes.GetPacketCount(cullingContext.cullingPlanes.Length), Allocator.TempJob);
		BatchRenderFlags batchRenderFlags = BatchRenderFlags.IsEnabled;
		BatchRenderFlags batchRenderFlags2 = BatchRenderFlags.All;
		if (cullingContext.viewType == BatchCullingViewType.Light)
		{
			batchRenderFlags |= BatchRenderFlags.CastShadows;
		}
		if (!IsMotionVectorsEnabled())
		{
			batchRenderFlags2 &= ~BatchRenderFlags.MotionVectors;
		}
		AllocateCullingJob jobData = new AllocateCullingJob
		{
			m_NativeBatchGroups = nativeBatchGroups,
			m_NativeBatchInstances = nativeBatchInstances,
			m_RequiredFlagMask = batchRenderFlags,
			m_MaxSplitBatchCount = maxSplitBatchCount,
			m_CullingOutput = cullingOutput,
			m_ActiveGroupData = activeGroupData
		};
		bool flag = cullingContext.projectionType == BatchCullingProjectionType.Orthographic && cullingContext.viewType == BatchCullingViewType.Light && cullingContext.cullingSplits.Length == 4;
		CullingPlanesJob jobData2 = new CullingPlanesJob
		{
			m_CullingPlanes = cullingContext.cullingPlanes,
			m_CullingSplits = cullingContext.cullingSplits,
			m_ShadowCullingData = (flag ? m_RenderingSystem.GetShadowCullingData() : float3.zero),
			m_SplitData = splitData,
			m_PlanePackets = nativeList
		};
		BatchCullingJob jobData3 = new BatchCullingJob
		{
			m_NativeBatchGroups = nativeBatchGroups,
			m_NativeBatchInstances = nativeBatchInstances,
			m_NativeSubBatches = nativeSubBatches,
			m_RequiredFlagMask = batchRenderFlags,
			m_RenderFlagMask = batchRenderFlags2,
			m_MaxSplitBatchCount = maxSplitBatchCount,
			m_IsShadowCulling = (cullingContext.viewType == BatchCullingViewType.Light),
			m_ActiveGroupData = activeGroupData,
			m_SplitData = splitData,
			m_CullingPlanePackets = nativeList,
			m_CullingOutput = cullingOutput
		};
		FinalizeCullingJob jobData4 = new FinalizeCullingJob
		{
			m_CullingOutput = cullingOutput
		};
		JobHandle job = IJobExtensions.Schedule(jobData, dependencies);
		JobHandle job2 = IJobExtensions.Schedule(jobData2);
		JobHandle jobHandle = IJobParallelForExtensions.Schedule(jobData3, activeGroupCount, 1, JobHandle.CombineDependencies(job, job2, dependencies3));
		JobHandle result = IJobExtensions.Schedule(jobData4, jobHandle);
		splitData.Dispose(jobHandle);
		nativeList.Dispose(jobHandle);
		AddNativeBatchInstancesReader(jobHandle);
		AddNativeBatchGroupsReader(jobHandle);
		AddNativeSubBatchesReader(jobHandle);
		return result;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_PropertiesChanged || m_MotionVectorsChanged || m_LodFadeChanged || m_VirtualTexturingChanged)
		{
			try
			{
				RefreshProperties(m_PropertiesChanged, m_MotionVectorsChanged, m_LodFadeChanged, m_VirtualTexturingChanged);
			}
			finally
			{
				m_PropertiesChanged = false;
				m_MotionVectorsChanged = false;
				m_LodFadeChanged = false;
				m_VirtualTexturingChanged = false;
			}
		}
		m_MergeDependencies.Complete();
		if (m_MergeMeshes.Length != 0)
		{
			MergeGroups();
		}
		JobHandle dependencies;
		JobHandle dependencies2;
		AllocateBuffersJob jobData = new AllocateBuffersJob
		{
			m_ObjectProperties = m_ObjectProperties,
			m_NetProperties = m_NetProperties,
			m_LaneProperties = m_LaneProperties,
			m_ZoneProperties = m_ZoneProperties,
			m_NativeBatchGroups = GetNativeBatchGroups(readOnly: false, out dependencies),
			m_NativeBatchInstances = GetNativeBatchInstances(readOnly: false, out dependencies2)
		};
		JobHandle dependencies3;
		GenerateSubBatchesJob jobData2 = new GenerateSubBatchesJob
		{
			m_NativeSubBatches = GetNativeSubBatches(readOnly: false, out dependencies3)
		};
		JobHandle jobHandle = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(dependencies, dependencies2));
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, dependencies3);
		AddNativeBatchGroupsWriter(jobHandle);
		AddNativeBatchInstancesWriter(jobHandle);
		AddNativeSubBatchesWriter(jobHandle2);
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		m_NativeBatchGroupsReadDependencies.Complete();
		m_NativeBatchGroupsWriteDependencies.Complete();
		m_NativeBatchInstancesReadDependencies.Complete();
		m_NativeBatchInstancesWriteDependencies.Complete();
		m_NativeSubBatchesReadDependencies.Complete();
		m_NativeSubBatchesWriteDependencies.Complete();
		m_ManagedBatches.EndUpload(m_NativeBatchInstances);
		int groupCount = m_NativeBatchGroups.GetGroupCount();
		for (int i = 0; i < groupCount; i++)
		{
			if (m_NativeBatchGroups.IsValidGroup(i))
			{
				m_NativeBatchInstances.RemoveInstances(i, m_NativeSubBatches);
			}
		}
	}
```

- `private RefreshProperties(System.Boolean propertiesChanged, System.Boolean motionVectorsChanged, System.Boolean lodFadeChanged, System.Boolean virtualTexturingChanged) : System.Void`  

```csharp
private void RefreshProperties(bool propertiesChanged, bool motionVectorsChanged, bool lodFadeChanged, bool virtualTexturingChanged)
	{
		JobHandle dependencies;
		NativeBatchGroups<CullingData, GroupData, BatchData, InstanceData> nativeBatchGroups = GetNativeBatchGroups(readOnly: false, out dependencies);
		JobHandle dependencies2;
		NativeBatchInstances<CullingData, GroupData, BatchData, InstanceData> nativeBatchInstances = GetNativeBatchInstances(readOnly: false, out dependencies2);
		JobHandle dependencies3;
		NativeSubBatches<CullingData, GroupData, BatchData, InstanceData> nativeSubBatches = GetNativeSubBatches(readOnly: false, out dependencies3);
		dependencies.Complete();
		dependencies2.Complete();
		dependencies3.Complete();
		int groupCount = nativeBatchGroups.GetGroupCount();
		bool flag = false;
		Dictionary<BatchPropertiesKey<OptionalProperties>, bool> dictionary = null;
		if (propertiesChanged)
		{
			dictionary = new Dictionary<BatchPropertiesKey<OptionalProperties>, bool>();
		}
		MeshSettingsData meshSettingsData = default(MeshSettingsData);
		if (!m_MeshSettingsQuery.IsEmptyIgnoreFilter)
		{
			meshSettingsData = m_MeshSettingsQuery.GetSingleton<MeshSettingsData>();
		}
		for (int i = 0; i < groupCount; i++)
		{
			if (!nativeBatchGroups.IsValidGroup(i))
			{
				continue;
			}
			int batchCount = nativeBatchGroups.GetBatchCount(i);
			GroupData groupData = nativeBatchGroups.GetGroupData(i);
			for (int j = 0; j < batchCount; j++)
			{
				int managedBatchIndex = nativeBatchGroups.GetManagedBatchIndex(i, j);
				if (managedBatchIndex < 0)
				{
					continue;
				}
				CustomBatch customBatch = (CustomBatch)m_ManagedBatches.GetBatch(managedBatchIndex);
				BatchFlags batchFlags = customBatch.sourceFlags;
				if (!IsMotionVectorsEnabled())
				{
					batchFlags &= ~BatchFlags.MotionVectors;
				}
				if (!IsLodFadeEnabled())
				{
					batchFlags &= ~BatchFlags.LodFade;
				}
				OptionalProperties optionalProperties = new OptionalProperties(batchFlags, customBatch.sourceType);
				bool flag2 = ((customBatch.sourceFlags & BatchFlags.MotionVectors) != 0 && motionVectorsChanged) || ((customBatch.sourceFlags & BatchFlags.LodFade) != 0 && lodFadeChanged);
				if ((customBatch.sourceType & (MeshType.Net | MeshType.Zone)) == 0)
				{
					RenderPrefab renderPrefab = m_PrefabSystem.GetPrefab<RenderPrefab>(customBatch.sourceMeshEntity);
					if (virtualTexturingChanged)
					{
						DecalProperties decalProperties = renderPrefab.GetComponent<DecalProperties>();
						if (decalProperties != null && groupData.m_Layer == MeshLayer.Outline)
						{
							decalProperties = null;
						}
						VTAtlassingInfo[] array = customBatch.sourceSurface.VTAtlassingInfos;
						if (array == null)
						{
							array = customBatch.sourceSurface.PreReservedAtlassingInfos;
						}
						if (array != null)
						{
							if (decalProperties != null || renderPrefab.manualVTRequired || renderPrefab.isImpostor)
							{
								BatchData batchData = nativeBatchGroups.GetBatchData(i, j);
								Bounds2 bounds = MathUtils.Bounds(new float2(0f, 0f), new float2(1f, 1f));
								batchData.m_VTIndex0 = -1;
								batchData.m_VTIndex1 = -1;
								if (decalProperties != null)
								{
									bounds = MathUtils.Bounds(decalProperties.m_TextureArea.min, decalProperties.m_TextureArea.max);
								}
								if (array.Length >= 1 && array[0].indexInStack >= 0)
								{
									batchData.m_VTIndex0 = m_ManagedBatchSystem.VTTextureRequester.RegisterTexture(0, array[0].stackGlobalIndex, array[0].indexInStack, bounds);
								}
								if (array.Length >= 2 && array[1].indexInStack >= 0)
								{
									batchData.m_VTIndex1 = m_ManagedBatchSystem.VTTextureRequester.RegisterTexture(1, array[1].stackGlobalIndex, array[1].indexInStack, bounds);
								}
								nativeBatchGroups.SetBatchData(i, j, batchData);
							}
							if (!renderPrefab.Has<DefaultMesh>())
							{
								for (int k = 0; k < 2; k++)
								{
									if (array.Length > k && array[k].indexInStack >= 0)
									{
										customBatch.customProps.SetTextureParamBlock(GetVTTextureParamBlockID(k), m_TextureStreamingSystem.GetTextureParamBlock(array[k]));
										flag2 = true;
									}
								}
							}
						}
					}
					if (customBatch.generatedType == GeneratedType.ObjectBase)
					{
						BaseProperties component = renderPrefab.GetComponent<BaseProperties>();
						if (component == null && (customBatch.sourceFlags & BatchFlags.Lod) != 0)
						{
							renderPrefab = m_PrefabSystem.GetPrefab<RenderPrefab>(groupData.m_Mesh);
							component = renderPrefab.GetComponent<BaseProperties>();
						}
						renderPrefab = ((!(component != null)) ? m_PrefabSystem.GetPrefab<RenderPrefab>(meshSettingsData.m_DefaultBaseMesh) : component.m_BaseType);
					}
					m_ManagedBatchSystem.SetupVT(renderPrefab, customBatch.material, customBatch.sourceSubMeshIndex);
				}
				if (propertiesChanged)
				{
					BatchPropertiesKey<OptionalProperties> key = new BatchPropertiesKey<OptionalProperties>(customBatch.material.shader, optionalProperties);
					if (!dictionary.TryGetValue(key, out var value))
					{
						value = m_ManagedBatches.RegenerateBatchProperties(customBatch.material.shader, optionalProperties);
						dictionary.Add(key, value);
					}
					flag2 = flag2 || value;
				}
				if (flag2)
				{
					NativeBatchProperties batchProperties = m_ManagedBatches.GetBatchProperties(customBatch.material.shader, optionalProperties);
					nativeBatchGroups.SetBatchProperties(i, j, batchProperties);
					nativeSubBatches.RecreateRenderers(i, j);
					WriteableBatchDefaultsAccessor batchDefaultsAccessor = nativeBatchGroups.GetBatchDefaultsAccessor(i, j);
					if (customBatch.sourceSurface != null)
					{
						m_ManagedBatches.SetDefaults(ManagedBatchSystem.GetTemplate(customBatch.sourceSurface), customBatch.sourceSurface.floats, customBatch.sourceSurface.ints, customBatch.sourceSurface.vectors, customBatch.sourceSurface.colors, customBatch.customProps, batchProperties, batchDefaultsAccessor);
					}
					else
					{
						m_ManagedBatches.SetDefaults(customBatch.sourceMaterial, customBatch.customProps, batchProperties, batchDefaultsAccessor);
					}
					flag |= nativeBatchInstances.GetInstanceCount(i) != 0;
				}
			}
		}
		if (flag)
		{
			m_BatchDataSystem.InstancePropertiesUpdated();
			if (IsLodFadeEnabled())
			{
				JobHandle jobHandle = IJobParallelForExtensions.Schedule(new InitializeLodFadeJob
				{
					m_NativeBatchInstances = nativeBatchInstances.AsParallelInstanceWriter()
				}, nativeBatchInstances.GetActiveGroupCount(), 1);
				AddNativeBatchInstancesWriter(jobHandle);
			}
		}
	}
```

- `public VirtualTexturingUpdated() : System.Void`  

```csharp
public void VirtualTexturingUpdated()
	{
		m_VirtualTexturingChanged = true;
	}
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

