# Game.Tools.GenerateEdgesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GenerateEdgesSystem : Game.GameSystemBase
{
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.WaterSystem m_WaterSystem;
    private Game.Tools.GenerateObjectsSystem m_GenerateObjectsSystem;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Common.ModificationBarrier2 m_TempEdgesBarrier;
    private Colossal.Collections.NativeValue<System.UInt32> m_BuildOrder;
    private Unity.Entities.EntityQuery m_CreatedEdgesQuery;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_DeletedQuery;
    private Game.Tools.GenerateEdgesSystem+TypeHandle __TypeHandle;

    public GenerateEdgesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public Colossal.Collections.NativeValue<System.UInt32> GetBuildOrder();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.WaterSystem m_WaterSystem`  

```csharp
private Game.Simulation.WaterSystem m_WaterSystem;
```

- `private Game.Tools.GenerateObjectsSystem m_GenerateObjectsSystem`  

```csharp
private Game.Tools.GenerateObjectsSystem m_GenerateObjectsSystem;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Common.ModificationBarrier2 m_TempEdgesBarrier`  

```csharp
private Game.Common.ModificationBarrier2 m_TempEdgesBarrier;
```

- `private Colossal.Collections.NativeValue<System.UInt32> m_BuildOrder`  

```csharp
private Colossal.Collections.NativeValue<System.UInt32> m_BuildOrder;
```

- `private Unity.Entities.EntityQuery m_CreatedEdgesQuery`  

```csharp
private Unity.Entities.EntityQuery m_CreatedEdgesQuery;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedQuery;
```

- `private Game.Tools.GenerateEdgesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.GenerateEdgesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GenerateEdgesSystem()`  

```csharp
[Preserve]
	public GenerateEdgesSystem()
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

- `public GetBuildOrder() : Colossal.Collections.NativeValue<System.UInt32>`  

```csharp
public NativeValue<uint> GetBuildOrder()
	{
		return m_BuildOrder;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_BuildOrder = new NativeValue<uint>(Allocator.Persistent);
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_WaterSystem = base.World.GetOrCreateSystemManaged<WaterSystem>();
		m_GenerateObjectsSystem = base.World.GetOrCreateSystemManaged<GenerateObjectsSystem>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_TempEdgesBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier2>();
		m_CreatedEdgesQuery = GetEntityQuery(ComponentType.ReadOnly<Created>(), ComponentType.ReadOnly<Edge>(), ComponentType.ReadOnly<Game.Net.BuildOrder>(), ComponentType.Exclude<Temp>());
		m_DefinitionQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<CreationDefinition>(),
				ComponentType.ReadOnly<NetCourse>(),
				ComponentType.ReadOnly<Updated>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Updated>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Node>(),
				ComponentType.ReadOnly<Edge>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() }
		});
		m_DeletedQuery = GetEntityQuery(ComponentType.ReadOnly<Edge>(), ComponentType.ReadOnly<Deleted>(), ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<PrefabRef>());
		RequireAnyForUpdate(m_CreatedEdgesQuery, m_DefinitionQuery);
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
		m_BuildOrder.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		JobHandle jobHandle = base.Dependency;
		if (!m_DefinitionQuery.IsEmptyIgnoreFilter)
		{
			NativeQueue<LocalConnectItem> localConnectQueue = new NativeQueue<LocalConnectItem>(Allocator.TempJob);
			NativeList<LocalConnectItem> localConnectList = new NativeList<LocalConnectItem>(Allocator.TempJob);
			NativeParallelMultiHashMap<NodeMapKey, Entity> nodeMap = new NativeParallelMultiHashMap<NodeMapKey, Entity>(m_DefinitionQuery.CalculateEntityCount(), Allocator.TempJob);
			NativeHashMap<OldEdgeKey, Entity> oldEdgeMap = new NativeHashMap<OldEdgeKey, Entity>(32, Allocator.TempJob);
			JobHandle dependencies;
			NativeHashMap<OwnerDefinition, Entity> reusedOwnerMap = m_GenerateObjectsSystem.GetReusedOwnerMap(out dependencies);
			TerrainHeightData heightData = m_TerrainSystem.GetHeightData();
			JobHandle deps;
			WaterSurfaceData surfaceData = m_WaterSystem.GetSurfaceData(out deps);
			CheckNodesJob jobData = new CheckNodesJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EditorContainerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_LocalConnectType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_LocalConnect_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ElevationType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_NodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Node_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_LocalConnectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LocalConnectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TerrainHeightData = heightData,
				m_NodeMap = nodeMap.AsParallelWriter(),
				m_LocalConnectQueue = localConnectQueue.AsParallelWriter()
			};
			FillOldEdgesJob jobData2 = new FillOldEdgesJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EditorContainerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OldEdgeMap = oldEdgeMap
			};
			CheckDefinitionsJob jobData3 = new CheckDefinitionsJob
			{
				m_CreationDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_CreationDefinition_RW_ComponentTypeHandle, ref base.CheckedStateRef),
				m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NodeMap = nodeMap.AsParallelWriter()
			};
			CollectLocalConnectItemsJob jobData4 = new CollectLocalConnectItemsJob
			{
				m_LocalConnectQueue = localConnectQueue,
				m_LocalConnectList = localConnectList
			};
			JobHandle dependsOn = JobChunkExtensions.ScheduleParallel(jobData, m_DefinitionQuery, base.Dependency);
			JobHandle job = JobChunkExtensions.Schedule(jobData2, m_DeletedQuery, base.Dependency);
			JobHandle job2 = JobChunkExtensions.ScheduleParallel(jobData3, m_DefinitionQuery, dependsOn);
			JobHandle jobHandle2 = IJobExtensions.Schedule(jobData4, dependsOn);
			JobHandle outJobHandle;
			NativeArray<int> chunkBaseEntityIndices = m_DefinitionQuery.CalculateBaseEntityIndexArrayAsync(Allocator.TempJob, JobHandle.CombineDependencies(job2, jobHandle2, deps), out outJobHandle);
			JobHandle jobHandle3 = JobChunkExtensions.ScheduleParallel(new GenerateEdgesJob
			{
				m_ChunkBaseEntityIndices = chunkBaseEntityIndices,
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_CreationDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_CreationDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_OwnerDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_OwnerDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_NetCourseType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_NetCourse_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_LocalCurveCacheType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_LocalCurveCache_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_UpgradedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Upgraded_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_EdgeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Edge_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SubReplacementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubReplacement_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NativeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Native_RO_ComponentLookup, ref base.CheckedStateRef),
				m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_UpgradedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Upgraded_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildOrderData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_BuildOrder_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TramTrackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_TramTrack_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EditorContainerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentLookup, ref base.CheckedStateRef),
				m_RoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Road_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConditionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_NetCondition_RO_ComponentLookup, ref base.CheckedStateRef),
				m_FixedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Fixed_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AggregatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Aggregated_RO_ComponentLookup, ref base.CheckedStateRef),
				m_RoundaboutData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Roundabout_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElectricityConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ElectricityConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PseudoRandomSeedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ServiceUpgradeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ServiceUpgrade_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LocalConnectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LocalConnectData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabTrackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TrackData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RoadData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabElectricityConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ElectricityConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectedNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedNode_RO_BufferLookup, ref base.CheckedStateRef),
				m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubReplacements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubReplacement_RO_BufferLookup, ref base.CheckedStateRef),
				m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
				m_BuildOrder = m_BuildOrder.value,
				m_NodeMap = nodeMap,
				m_ReusedOwnerMap = reusedOwnerMap,
				m_OldEdgeMap = oldEdgeMap,
				m_LocalConnectList = localConnectList.AsDeferredJobArray(),
				m_TerrainHeightData = heightData,
				m_WaterSurfaceData = surfaceData,
				m_CommandBuffer = m_TempEdgesBarrier.CreateCommandBuffer().AsParallelWriter()
			}, m_DefinitionQuery, JobHandle.CombineDependencies(outJobHandle, job, dependencies));
			localConnectQueue.Dispose(jobHandle2);
			localConnectList.Dispose(jobHandle3);
			nodeMap.Dispose(jobHandle3);
			oldEdgeMap.Dispose(jobHandle3);
			m_TerrainSystem.AddCPUHeightReader(jobHandle3);
			m_WaterSystem.AddSurfaceReader(jobHandle3);
			m_GenerateObjectsSystem.AddOwnerMapReader(jobHandle3);
			m_TempEdgesBarrier.AddJobHandleForProducer(jobHandle3);
			jobHandle = jobHandle3;
		}
		if (!m_CreatedEdgesQuery.IsEmptyIgnoreFilter)
		{
			JobHandle outJobHandle2;
			NativeList<ArchetypeChunk> chunks = m_CreatedEdgesQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle2);
			JobHandle jobHandle4 = IJobExtensions.Schedule(new UpdateBuildOrderJob
			{
				m_Chunks = chunks,
				m_BuildOrderType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_BuildOrder_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_BuildOrder = m_BuildOrder
			}, JobHandle.CombineDependencies(base.Dependency, outJobHandle2));
			chunks.Dispose(jobHandle4);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle4);
		}
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Tools.GenerateEdgesSystem+NodeMapKey`  
- `Game.Tools.GenerateEdgesSystem+LocalConnectItem`  
- `Game.Tools.GenerateEdgesSystem+OldEdgeKey`  
- `Game.Tools.GenerateEdgesSystem+CheckNodesJob`  
- `Game.Tools.GenerateEdgesSystem+FillOldEdgesJob`  
- `Game.Tools.GenerateEdgesSystem+CheckDefinitionsJob`  
- `Game.Tools.GenerateEdgesSystem+CollectLocalConnectItemsJob`  
- `Game.Tools.GenerateEdgesSystem+GenerateEdgesJob`  
- `Game.Tools.GenerateEdgesSystem+UpdateBuildOrderJob`  
- `Game.Tools.GenerateEdgesSystem+TypeHandle`  

