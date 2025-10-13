# Game.Tools.GenerateNodesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GenerateNodesSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Net.SearchSystem m_SearchSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Tools.GenerateObjectsSystem m_GenerateObjectsSystem;
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_DeletedQuery;
    private Game.Tools.GenerateNodesSystem+TypeHandle __TypeHandle;

    public GenerateNodesSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Net.SearchSystem m_SearchSystem`  

```csharp
private Game.Net.SearchSystem m_SearchSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Tools.GenerateObjectsSystem m_GenerateObjectsSystem`  

```csharp
private Game.Tools.GenerateObjectsSystem m_GenerateObjectsSystem;
```

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier1 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedQuery;
```

- `private Game.Tools.GenerateNodesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.GenerateNodesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GenerateNodesSystem()`  

```csharp
[Preserve]
	public GenerateNodesSystem()
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
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_SearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_GenerateObjectsSystem = base.World.GetOrCreateSystemManaged<GenerateObjectsSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier1>();
		m_DefinitionQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<CreationDefinition>(),
				ComponentType.ReadOnly<Updated>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<NetCourse>(),
				ComponentType.ReadOnly<ObjectDefinition>()
			}
		});
		m_DeletedQuery = GetEntityQuery(ComponentType.ReadOnly<Node>(), ComponentType.ReadOnly<Deleted>(), ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<PrefabRef>());
		RequireForUpdate(m_DefinitionQuery);
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
		NativeQueue<UpdateData> updateQueue = new NativeQueue<UpdateData>(Allocator.TempJob);
		NativeList<UpdateData> updateList = new NativeList<UpdateData>(Allocator.TempJob);
		NativeParallelHashMap<Entity, DefinitionData> definitionMap = new NativeParallelHashMap<Entity, DefinitionData>(m_DefinitionQuery.CalculateEntityCount(), Allocator.TempJob);
		NativeParallelMultiHashMap<OldNodeKey, OldNodeValue> oldNodeMap = new NativeParallelMultiHashMap<OldNodeKey, OldNodeValue>(32, Allocator.TempJob);
		JobHandle dependencies;
		NativeHashMap<OwnerDefinition, Entity> reusedOwnerMap = m_GenerateObjectsSystem.GetReusedOwnerMap(out dependencies);
		TerrainHeightData data = m_TerrainSystem.GetHeightData();
		Bounds3 bounds = TerrainUtils.GetBounds(ref data);
		JobHandle dependencies2;
		FillNodeMapJob jobData = new FillNodeMapJob
		{
			m_CreationDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_CreationDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_OwnerDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetCourseType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_NetCourse_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_LocalCurveCacheType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_LocalCurveCache_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_UpgradedType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Upgraded_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LocalConnectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LocalConnect_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoundaboutData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Roundabout_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabLocalConnectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LocalConnectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RoadData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Edges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_Nodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedNode_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
			m_NodeQueue = updateQueue.AsParallelWriter(),
			m_DefinitionMap = definitionMap.AsParallelWriter(),
			m_NetSearchTree = m_SearchSystem.GetNetSearchTree(readOnly: true, out dependencies2)
		};
		FillOldNodesJob jobData2 = new FillOldNodesJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NodeType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_Node_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EditorContainerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OutsideConnectionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_OutsideConnection_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OldNodeMap = oldNodeMap
		};
		CollectUpdatesJob jobData3 = new CollectUpdatesJob
		{
			m_UpdateQueue = updateQueue,
			m_UpdateList = updateList
		};
		CreateNodesJob jobData4 = new CreateNodesJob
		{
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabLocalConnectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LocalConnectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RoadData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LocalConnectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LocalConnect_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EditorContainerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StandaloneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Standalone_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NativeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Native_RO_ComponentLookup, ref base.CheckedStateRef),
			m_FixedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Fixed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UpgradedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Upgraded_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ConditionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_NetCondition_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Road_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PseudoRandomSeedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceUpgradeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ServiceUpgrade_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Edges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_TerrainBounds = bounds,
			m_UpdateList = updateList,
			m_DefinitionMap = definitionMap,
			m_ReusedOwnerMap = reusedOwnerMap,
			m_OldNodeMap = oldNodeMap,
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_DefinitionQuery, JobHandle.CombineDependencies(base.Dependency, dependencies2));
		JobHandle job = JobChunkExtensions.Schedule(jobData2, m_DeletedQuery, base.Dependency);
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData3, jobHandle);
		JobHandle jobHandle3 = IJobExtensions.Schedule(jobData4, JobHandle.CombineDependencies(jobHandle2, job, dependencies));
		updateQueue.Dispose(jobHandle2);
		updateList.Dispose(jobHandle3);
		definitionMap.Dispose(jobHandle3);
		oldNodeMap.Dispose(jobHandle3);
		m_SearchSystem.AddNetSearchTreeReader(jobHandle);
		m_GenerateObjectsSystem.AddOwnerMapReader(jobHandle3);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle3);
		base.Dependency = jobHandle3;
	}
```


## Nested types

- `Game.Tools.GenerateNodesSystem+UpdateData`  
- `Game.Tools.GenerateNodesSystem+NodeKey`  
- `Game.Tools.GenerateNodesSystem+DefinitionData`  
- `Game.Tools.GenerateNodesSystem+OldNodeKey`  
- `Game.Tools.GenerateNodesSystem+OldNodeValue`  
- `Game.Tools.GenerateNodesSystem+FillOldNodesJob`  
- `Game.Tools.GenerateNodesSystem+FillNodeMapJob`  
- `Game.Tools.GenerateNodesSystem+CollectUpdatesJob`  
- `Game.Tools.GenerateNodesSystem+CreateNodesJob`  
- `Game.Tools.GenerateNodesSystem+TypeHandle`  

