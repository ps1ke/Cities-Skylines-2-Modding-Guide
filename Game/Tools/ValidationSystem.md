# Game.Tools.ValidationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ValidationSystem : Game.GameSystemBase
{
    private Game.Common.ModificationEndBarrier m_ModificationBarrier;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Tools.ValidationSystem+Components m_Components;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Unity.Entities.EntityQuery m_UpdatedAreaQuery;
    private Unity.Entities.EntityQuery m_ToolErrorPrefabQuery;
    private Game.Tools.ValidationSystem+ChunkType m_ChunkType;
    private Game.Tools.ValidationSystem+EntityData m_EntityData;
    private Game.Tools.ValidationSystem+TypeHandle __TypeHandle;

    public ValidationSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationBarrier;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Tools.ValidationSystem+Components m_Components`  

```csharp
private Game.Tools.ValidationSystem+Components m_Components;
```

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem`  

```csharp
private Game.Prefabs.InstanceCountSystem m_InstanceCountSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.GroundWaterSystem m_GroundWaterSystem`  

```csharp
private Game.Simulation.GroundWaterSystem m_GroundWaterSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedAreaQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedAreaQuery;
```

- `private Unity.Entities.EntityQuery m_ToolErrorPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_ToolErrorPrefabQuery;
```

- `private Game.Tools.ValidationSystem+ChunkType m_ChunkType`  

```csharp
private Game.Tools.ValidationSystem+ChunkType m_ChunkType;
```

- `private Game.Tools.ValidationSystem+EntityData m_EntityData`  

```csharp
private Game.Tools.ValidationSystem+EntityData m_EntityData;
```

- `private Game.Tools.ValidationSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ValidationSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public ValidationSystem()`  

```csharp
[Preserve]
	public ValidationSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationEndBarrier>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_Components = base.World.GetOrCreateSystemManaged<Components>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_InstanceCountSystem = base.World.GetOrCreateSystemManaged<InstanceCountSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_GroundWaterSystem = base.World.GetOrCreateSystemManaged<GroundWaterSystem>();
		m_UpdatedQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<Updated>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Relative>(), ComponentType.Exclude<Moving>(), ComponentType.Exclude<Stopped>());
		m_UpdatedAreaQuery = GetEntityQuery(ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<Updated>(), ComponentType.ReadOnly<Area>(), ComponentType.Exclude<Deleted>());
		m_ToolErrorPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<NotificationIconData>(), ComponentType.ReadOnly<ToolErrorData>());
		m_ChunkType = new ChunkType(this);
		m_EntityData = new EntityData(this);
		RequireForUpdate(m_UpdatedQuery);
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

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		NativeList<BoundsData> edgeList = new NativeList<BoundsData>(Allocator.TempJob);
		NativeList<BoundsData> objectList = new NativeList<BoundsData>(Allocator.TempJob);
		NativeQueue<ErrorData> errorQueue = new NativeQueue<ErrorData>(Allocator.TempJob);
		NativeQueue<ErrorData> errorQueue2 = new NativeQueue<ErrorData>(Allocator.TempJob);
		NativeArray<Entity> errorPrefabs = new NativeArray<Entity>(28, Allocator.TempJob);
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> nativeList = m_UpdatedQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		m_ChunkType.Update(this);
		m_EntityData.Update(this);
		BoundsListJob jobData = new BoundsListJob
		{
			m_Chunks = nativeList.AsDeferredJobArray(),
			m_ChunkType = m_ChunkType,
			m_EntityData = m_EntityData,
			m_EdgeList = edgeList,
			m_ObjectList = objectList
		};
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle dependencies3;
		JobHandle dependencies4;
		JobHandle deps;
		JobHandle dependencies5;
		ValidationJob jobData2 = new ValidationJob
		{
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_Chunks = nativeList.AsDeferredJobArray(),
			m_ChunkType = m_ChunkType,
			m_EntityData = m_EntityData,
			m_EdgeList = edgeList,
			m_ObjectList = objectList,
			m_ObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies),
			m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies2),
			m_AreaSearchTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies3),
			m_InstanceCounts = m_InstanceCountSystem.GetInstanceCounts(readOnly: true, out dependencies4),
			m_WaterSurfaceData = m_WaterSystem.GetSurfaceData(out deps),
			m_TerrainHeightData = m_TerrainSystem.GetHeightData(),
			m_GroundWaterMap = m_GroundWaterSystem.GetMap(readOnly: true, out dependencies5),
			m_ErrorQueue = errorQueue.AsParallelWriter()
		};
		JobHandle job = JobUtils.CombineDependencies(dependencies, dependencies2, dependencies3, dependencies4, deps, dependencies5);
		JobHandle jobHandle = default(JobHandle);
		m_Components.m_ErrorMap = new NativeHashMap<Entity, ErrorSeverity>(32, Allocator.TempJob);
		if (!m_UpdatedAreaQuery.IsEmptyIgnoreFilter)
		{
			NativeList<AreaSearchItem> nativeList2 = new NativeList<AreaSearchItem>(Allocator.TempJob);
			CollectAreaTrianglesJob jobData3 = new CollectAreaTrianglesJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_NativeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Native_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TriangleType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_AreaTriangles = nativeList2
			};
			jobHandle = new ValidateAreaTrianglesJob
			{
				m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
				m_AreaTriangles = nativeList2.AsDeferredJobArray(),
				m_EntityData = jobData2.m_EntityData,
				m_ObjectSearchTree = jobData2.m_ObjectSearchTree,
				m_NetSearchTree = jobData2.m_NetSearchTree,
				m_AreaSearchTree = jobData2.m_AreaSearchTree,
				m_WaterSurfaceData = jobData2.m_WaterSurfaceData,
				m_TerrainHeightData = jobData2.m_TerrainHeightData,
				m_ErrorQueue = errorQueue2.AsParallelWriter()
			}.Schedule(dependsOn: JobHandle.CombineDependencies(JobChunkExtensions.Schedule(jobData3, m_UpdatedAreaQuery, base.Dependency), job), list: nativeList2, innerloopBatchCount: 1);
			nativeList2.Dispose(jobHandle);
		}
		FillErrorPrefabsJob jobData4 = new FillErrorPrefabsJob
		{
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_ToolErrorType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_ToolErrorData_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ErrorPrefabs = errorPrefabs
		};
		ProcessValidationResultsJob jobData5 = new ProcessValidationResultsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurveType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Curve_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BrushType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Brush_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlayerMoney = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_PlayerMoney_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_Chunks = nativeList,
			m_City = m_CitySystem.City,
			m_ErrorMap = m_Components.m_ErrorMap,
			m_ErrorPrefabs = errorPrefabs,
			m_ErrorQueue1 = errorQueue,
			m_ErrorQueue2 = errorQueue2,
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer(),
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer()
		};
		base.Dependency = JobHandle.CombineDependencies(base.Dependency, outJobHandle);
		JobHandle job2 = IJobParallelForDeferExtensions.Schedule(dependsOn: JobHandle.CombineDependencies(IJobExtensions.Schedule(jobData, base.Dependency), job), jobData: jobData2, list: nativeList, innerloopBatchCount: 1);
		job2 = JobHandle.CombineDependencies(job2, jobHandle);
		JobHandle job3 = JobChunkExtensions.Schedule(jobData4, m_ToolErrorPrefabQuery, base.Dependency);
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData5, JobHandle.CombineDependencies(job2, job3));
		edgeList.Dispose(job2);
		objectList.Dispose(job2);
		errorQueue.Dispose(jobHandle2);
		errorQueue2.Dispose(jobHandle2);
		nativeList.Dispose(jobHandle2);
		m_ObjectSearchSystem.AddStaticSearchTreeReader(job2);
		m_NetSearchSystem.AddNetSearchTreeReader(job2);
		m_AreaSearchSystem.AddSearchTreeReader(job2);
		m_InstanceCountSystem.AddCountReader(job2);
		m_WaterSystem.AddSurfaceReader(job2);
		m_TerrainSystem.AddCPUHeightReader(job2);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
		m_IconCommandSystem.AddCommandBufferWriter(jobHandle2);
		m_Components.m_ErrorMapDeps = jobHandle2;
		base.Dependency = jobHandle2;
	}
```


## Nested types

- `Game.Tools.ValidationSystem+ChunkType`  
- `Game.Tools.ValidationSystem+EntityData`  
- `Game.Tools.ValidationSystem+Components`  
- `Game.Tools.ValidationSystem+BoundsData`  
- `Game.Tools.ValidationSystem+BoundsComparerX`  
- `Game.Tools.ValidationSystem+BoundsComparerZ`  
- `Game.Tools.ValidationSystem+BoundsListJob`  
- `Game.Tools.ValidationSystem+ValidationJob`  
- `Game.Tools.ValidationSystem+CollectAreaTrianglesJob`  
- `Game.Tools.ValidationSystem+ValidateAreaTrianglesJob`  
- `Game.Tools.ValidationSystem+FillErrorPrefabsJob`  
- `Game.Tools.ValidationSystem+IconKey`  
- `Game.Tools.ValidationSystem+IconValue`  
- `Game.Tools.ValidationSystem+ProcessValidationResultsJob`  
- `Game.Tools.ValidationSystem+TypeHandle`  

