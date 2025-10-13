# Game.Effects.EffectControlSystem

**Assembly:** `Game`  
**Namespace:** `Game.Effects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class EffectControlSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.Effects.VFXSystem m_VFXSystem;
    private Game.Effects.SearchSystem m_SearchSystem;
    private Game.Effects.EffectFlagSystem m_EffectFlagSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Rendering.PreCullingSystem m_PreCullingSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Rendering.BatchDataSystem m_BatchDataSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Effects.EffectControlData m_EffectControlData;
    private Unity.Collections.NativeList<Game.Effects.EnabledEffectData> m_EnabledData;
    private Unity.Entities.EntityQuery m_UpdatedEffectsQuery;
    private Unity.Entities.EntityQuery m_AllEffectsQuery;
    private Unity.Jobs.JobHandle m_EnabledWriteDependencies;
    private Unity.Jobs.JobHandle m_EnabledReadDependencies;
    private Unity.Mathematics.float3 m_PrevCameraPosition;
    private Unity.Mathematics.float3 m_PrevCameraDirection;
    private Unity.Mathematics.float4 m_PrevLodParameters;
    private System.Boolean m_Loaded;
    private System.Boolean m_ResetPrevious;
    private Game.Effects.EffectControlSystem+TypeHandle __TypeHandle;

    public EffectControlSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddEnabledDataReader(Unity.Jobs.JobHandle dependencies);
    public System.Void AddEnabledDataWriter(Unity.Jobs.JobHandle dependencies);
    public Unity.Collections.NativeList<Game.Effects.EnabledEffectData> GetEnabledData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies);
    private System.Boolean GetLoaded();
    public System.Void GetLodParameters(Unity.Mathematics.float4& lodParameters, Unity.Mathematics.float3& cameraPosition, Unity.Mathematics.float3& cameraDirection);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
}
```


## Fields

- `private Game.Effects.VFXSystem m_VFXSystem`  

```csharp
private Game.Effects.VFXSystem m_VFXSystem;
```

- `private Game.Effects.SearchSystem m_SearchSystem`  

```csharp
private Game.Effects.SearchSystem m_SearchSystem;
```

- `private Game.Effects.EffectFlagSystem m_EffectFlagSystem`  

```csharp
private Game.Effects.EffectFlagSystem m_EffectFlagSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Rendering.PreCullingSystem m_PreCullingSystem`  

```csharp
private Game.Rendering.PreCullingSystem m_PreCullingSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Rendering.BatchDataSystem m_BatchDataSystem`  

```csharp
private Game.Rendering.BatchDataSystem m_BatchDataSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Effects.EffectControlData m_EffectControlData`  

```csharp
private Game.Effects.EffectControlData m_EffectControlData;
```

- `private Unity.Collections.NativeList<Game.Effects.EnabledEffectData> m_EnabledData`  

```csharp
private Unity.Collections.NativeList<Game.Effects.EnabledEffectData> m_EnabledData;
```

- `private Unity.Entities.EntityQuery m_UpdatedEffectsQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedEffectsQuery;
```

- `private Unity.Entities.EntityQuery m_AllEffectsQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllEffectsQuery;
```

- `private Unity.Jobs.JobHandle m_EnabledWriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_EnabledWriteDependencies;
```

- `private Unity.Jobs.JobHandle m_EnabledReadDependencies`  

```csharp
private Unity.Jobs.JobHandle m_EnabledReadDependencies;
```

- `private Unity.Mathematics.float3 m_PrevCameraPosition`  

```csharp
private Unity.Mathematics.float3 m_PrevCameraPosition;
```

- `private Unity.Mathematics.float3 m_PrevCameraDirection`  

```csharp
private Unity.Mathematics.float3 m_PrevCameraDirection;
```

- `private Unity.Mathematics.float4 m_PrevLodParameters`  

```csharp
private Unity.Mathematics.float4 m_PrevLodParameters;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private System.Boolean m_ResetPrevious`  

```csharp
private System.Boolean m_ResetPrevious;
```

- `private Game.Effects.EffectControlSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Effects.EffectControlSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public EffectControlSystem()`  

```csharp
[Preserve]
	public EffectControlSystem()
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

- `public AddEnabledDataReader(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public void AddEnabledDataReader(JobHandle dependencies)
	{
		m_EnabledReadDependencies = JobHandle.CombineDependencies(m_EnabledReadDependencies, dependencies);
	}
```

- `public AddEnabledDataWriter(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public void AddEnabledDataWriter(JobHandle dependencies)
	{
		m_EnabledWriteDependencies = dependencies;
	}
```

- `public GetEnabledData(System.Boolean readOnly, Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeList<Game.Effects.EnabledEffectData>`  

```csharp
public NativeList<EnabledEffectData> GetEnabledData(bool readOnly, out JobHandle dependencies)
	{
		dependencies = (readOnly ? m_EnabledWriteDependencies : JobHandle.CombineDependencies(m_EnabledWriteDependencies, m_EnabledReadDependencies));
		return m_EnabledData;
	}
```

- `private GetLoaded() : System.Boolean`  

```csharp
private bool GetLoaded()
	{
		if (m_Loaded)
		{
			m_Loaded = false;
			return true;
		}
		return false;
	}
```

- `public GetLodParameters(Unity.Mathematics.float4& lodParameters, Unity.Mathematics.float3& cameraPosition, Unity.Mathematics.float3& cameraDirection) : System.Void`  

```csharp
public void GetLodParameters(out float4 lodParameters, out float3 cameraPosition, out float3 cameraDirection)
	{
		lodParameters = m_PrevLodParameters;
		cameraPosition = m_PrevCameraPosition;
		cameraDirection = m_PrevCameraDirection;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_VFXSystem = base.World.GetOrCreateSystemManaged<VFXSystem>();
		m_SearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_EffectFlagSystem = base.World.GetOrCreateSystemManaged<EffectFlagSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_PreCullingSystem = base.World.GetOrCreateSystemManaged<PreCullingSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_BatchDataSystem = base.World.GetOrCreateSystemManaged<BatchDataSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_EffectControlData = new EffectControlData(this);
		m_EnabledData = new NativeList<EnabledEffectData>(Allocator.Persistent);
		m_UpdatedEffectsQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<EnabledEffect>() },
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<EffectsUpdated>(),
				ComponentType.ReadOnly<BatchesUpdated>()
			}
		});
		m_AllEffectsQuery = GetEntityQuery(ComponentType.ReadOnly<EnabledEffect>());
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
		m_EnabledData.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool loaded = GetLoaded();
		EntityQuery query = (loaded ? m_AllEffectsQuery : m_UpdatedEffectsQuery);
		m_EffectControlData.Update(this, m_EffectFlagSystem.GetData(), m_SimulationSystem.frameIndex, m_ToolSystem.selected);
		m_EnabledWriteDependencies.Complete();
		m_EnabledReadDependencies.Complete();
		int length = m_EnabledData.Length;
		NativeParallelQueue<EnabledAction> nativeParallelQueue = new NativeParallelQueue<EnabledAction>(Allocator.TempJob);
		NativeQueue<OverflowAction> overflowActions = new NativeQueue<OverflowAction>(Allocator.TempJob);
		NativeReference<int> enabledDataIndex = new NativeReference<int>(length, Allocator.TempJob);
		float3 @float = m_PrevCameraPosition;
		float3 float2 = m_PrevCameraDirection;
		float4 float3 = m_PrevLodParameters;
		if (m_CameraUpdateSystem.TryGetLODParameters(out var lodParameters))
		{
			@float = lodParameters.cameraPosition;
			IGameCameraController activeCameraController = m_CameraUpdateSystem.activeCameraController;
			float3 = RenderingUtils.CalculateLodParameters(m_BatchDataSystem.GetLevelOfDetail(m_RenderingSystem.frameLod, activeCameraController), lodParameters);
			float2 = m_CameraUpdateSystem.activeViewer.forward;
		}
		if (m_ResetPrevious)
		{
			m_PrevCameraPosition = @float;
			m_PrevCameraDirection = float2;
			m_PrevLodParameters = float3;
		}
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new EffectControlJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_DeletedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CullingInfoType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Rendering_CullingInfo_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EditorContainerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ObjectType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Object_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_StaticType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Static_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EventType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_Event_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EffectOwnerType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Effects_EnabledEffect_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_PrefabEffectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_EffectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TrafficLightsData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_TrafficLights_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabLightEffectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LightEffectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabAudioEffectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AudioEffectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabEffects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_Effect_RO_BufferLookup, ref base.CheckedStateRef),
			m_LodParameters = float3,
			m_CameraPosition = @float,
			m_CameraDirection = float2,
			m_CullingData = m_PreCullingSystem.GetCullingData(readOnly: true, out dependencies),
			m_EnabledEffectData = m_EnabledData,
			m_ActionQueue = nativeParallelQueue.AsWriter()
		}, query, JobHandle.CombineDependencies(dependencies, base.Dependency));
		if (!loaded)
		{
			JobHandle dependencies2;
			NativeQuadTree<SourceInfo, QuadTreeBoundsXZ> searchTree = m_SearchSystem.GetSearchTree(readOnly: true, out dependencies2);
			NativeArray<int> nodeBuffer = new NativeArray<int>(256, Allocator.TempJob, NativeArrayOptions.UninitializedMemory);
			NativeArray<int> subDataBuffer = new NativeArray<int>(256, Allocator.TempJob, NativeArrayOptions.UninitializedMemory);
			TreeCullingJob1 jobData = new TreeCullingJob1
			{
				m_EffectSearchTree = searchTree,
				m_LodParameters = float3,
				m_PrevLodParameters = m_PrevLodParameters,
				m_CameraPosition = @float,
				m_PrevCameraPosition = m_PrevCameraPosition,
				m_CameraDirection = float2,
				m_PrevCameraDirection = m_PrevCameraDirection,
				m_NodeBuffer = nodeBuffer,
				m_SubDataBuffer = subDataBuffer,
				m_ActionQueue = nativeParallelQueue.AsWriter()
			};
			TreeCullingJob2 jobData2 = new TreeCullingJob2
			{
				m_EffectSearchTree = searchTree,
				m_LodParameters = float3,
				m_PrevLodParameters = m_PrevLodParameters,
				m_CameraPosition = @float,
				m_PrevCameraPosition = m_PrevCameraPosition,
				m_CameraDirection = float2,
				m_PrevCameraDirection = m_PrevCameraDirection,
				m_NodeBuffer = nodeBuffer,
				m_SubDataBuffer = subDataBuffer,
				m_ActionQueue = nativeParallelQueue.AsWriter()
			};
			JobHandle dependencies3;
			EffectCullingJob jobData3 = new EffectCullingJob
			{
				m_EditorContainerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_StaticData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Static_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabEffectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_EffectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EffectOwners = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Effects_EnabledEffect_RO_BufferLookup, ref base.CheckedStateRef),
				m_PrefabEffects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_Effect_RO_BufferLookup, ref base.CheckedStateRef),
				m_CullingData = m_PreCullingSystem.GetUpdatedData(readOnly: true, out dependencies3),
				m_EnabledEffectData = m_EnabledData,
				m_ActionQueue = nativeParallelQueue.AsWriter()
			};
			JobHandle jobHandle2 = IJobParallelForExtensions.Schedule(dependsOn: IJobExtensions.Schedule(jobData, dependencies2), jobData: jobData2, arrayLength: nodeBuffer.Length, innerloopBatchCount: 1);
			JobHandle job = jobData3.Schedule(jobData3.m_CullingData, 16, JobHandle.CombineDependencies(base.Dependency, dependencies3));
			nodeBuffer.Dispose(jobHandle2);
			subDataBuffer.Dispose(jobHandle2);
			m_SearchSystem.AddSearchTreeReader(jobHandle2);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2, job);
		}
		EnabledActionJob jobData4 = new EnabledActionJob
		{
			m_EditorContainerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_InterpolatedTransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Rendering_InterpolatedTransform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DestroyedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_VFXDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_VFXData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RandomTransformDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RandomTransformData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectGeometryDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AudioSourceDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AudioSourceData_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabEffects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_Effect_RO_BufferLookup, ref base.CheckedStateRef),
			m_EffectOwners = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Effects_EnabledEffect_RW_BufferLookup, ref base.CheckedStateRef),
			m_CullingActions = nativeParallelQueue.AsReader(),
			m_OverflowActions = overflowActions.AsParallelWriter(),
			m_VFXUpdateQueue = m_VFXSystem.GetSourceUpdateData().AsParallelWriter(),
			m_EnabledData = m_EnabledData,
			m_EnabledDataIndex = enabledDataIndex,
			m_EffectControlData = m_EffectControlData
		};
		ResizeEnabledDataJob jobData5 = new ResizeEnabledDataJob
		{
			m_EnabledDataIndex = enabledDataIndex,
			m_EnabledData = m_EnabledData,
			m_OverflowActions = overflowActions
		};
		JobHandle jobHandle3 = IJobParallelForExtensions.Schedule(jobData4, nativeParallelQueue.HashRange, 1, jobHandle);
		JobHandle inputDeps = (m_EnabledWriteDependencies = IJobExtensions.Schedule(jobData5, jobHandle3));
		nativeParallelQueue.Dispose(jobHandle3);
		overflowActions.Dispose(inputDeps);
		enabledDataIndex.Dispose(inputDeps);
		m_VFXSystem.AddSourceUpdateWriter(jobHandle3);
		m_PreCullingSystem.AddCullingDataReader(jobHandle);
		m_PrevCameraPosition = @float;
		m_PrevCameraDirection = float2;
		m_PrevLodParameters = float3;
		m_ResetPrevious = false;
		base.Dependency = jobHandle3;
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		m_EnabledWriteDependencies.Complete();
		m_EnabledReadDependencies.Complete();
		m_EnabledData.Clear();
		m_ResetPrevious = true;
		m_Loaded = true;
	}
```


## Nested types

- `Game.Effects.EffectControlSystem+EffectControlJob`  
- `Game.Effects.EffectControlSystem+EffectCullingJob`  
- `Game.Effects.EffectControlSystem+TreeCullingJob1`  
- `Game.Effects.EffectControlSystem+TreeCullingJob2`  
- `Game.Effects.EffectControlSystem+TreeCullingIterator`  
- `Game.Effects.EffectControlSystem+ActionFlags`  
- `Game.Effects.EffectControlSystem+EnabledAction`  
- `Game.Effects.EffectControlSystem+OverflowAction`  
- `Game.Effects.EffectControlSystem+EnabledActionJob`  
- `Game.Effects.EffectControlSystem+ResizeEnabledDataJob`  
- `Game.Effects.EffectControlSystem+TypeHandle`  

