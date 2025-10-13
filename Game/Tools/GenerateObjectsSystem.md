# Game.Tools.GenerateObjectsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class GenerateObjectsSystem : Game.GameSystemBase
{
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Common.ModificationBarrier1 m_ModificationBarrier;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Unity.Entities.EntityQuery m_DefinitionQuery;
    private Unity.Entities.EntityQuery m_DeletedQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.ComponentTypeSet m_SubTypes;
    private Unity.Entities.ComponentTypeSet m_StoppedUpdateFrameTypes;
    private Unity.Collections.NativeHashMap<Game.Tools.OwnerDefinition, Unity.Entities.Entity> m_ReusedOwnerMap;
    private Unity.Jobs.JobHandle m_OwnerMapReadDeps;
    private Unity.Jobs.JobHandle m_OwnerMapWriteDeps;
    private Game.Tools.GenerateObjectsSystem+TypeHandle __TypeHandle;

    public GenerateObjectsSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddOwnerMapReader(Unity.Jobs.JobHandle dependencies);
    public Unity.Collections.NativeHashMap<Game.Tools.OwnerDefinition, Unity.Entities.Entity> GetReusedOwnerMap(Unity.Jobs.JobHandle& dependencies);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Common.ModificationBarrier1 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier1 m_ModificationBarrier;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Unity.Entities.EntityQuery m_DefinitionQuery`  

```csharp
private Unity.Entities.EntityQuery m_DefinitionQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.ComponentTypeSet m_SubTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_SubTypes;
```

- `private Unity.Entities.ComponentTypeSet m_StoppedUpdateFrameTypes`  

```csharp
private Unity.Entities.ComponentTypeSet m_StoppedUpdateFrameTypes;
```

- `private Unity.Collections.NativeHashMap<Game.Tools.OwnerDefinition, Unity.Entities.Entity> m_ReusedOwnerMap`  

```csharp
private Unity.Collections.NativeHashMap<Game.Tools.OwnerDefinition, Unity.Entities.Entity> m_ReusedOwnerMap;
```

- `private Unity.Jobs.JobHandle m_OwnerMapReadDeps`  

```csharp
private Unity.Jobs.JobHandle m_OwnerMapReadDeps;
```

- `private Unity.Jobs.JobHandle m_OwnerMapWriteDeps`  

```csharp
private Unity.Jobs.JobHandle m_OwnerMapWriteDeps;
```

- `private Game.Tools.GenerateObjectsSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.GenerateObjectsSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public GenerateObjectsSystem()`  

```csharp
[Preserve]
	public GenerateObjectsSystem()
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

- `public AddOwnerMapReader(Unity.Jobs.JobHandle dependencies) : System.Void`  

```csharp
public void AddOwnerMapReader(JobHandle dependencies)
	{
		m_OwnerMapReadDeps = JobHandle.CombineDependencies(m_OwnerMapReadDeps, dependencies);
	}
```

- `public GetReusedOwnerMap(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeHashMap<Game.Tools.OwnerDefinition, Unity.Entities.Entity>`  

```csharp
public NativeHashMap<OwnerDefinition, Entity> GetReusedOwnerMap(out JobHandle dependencies)
	{
		dependencies = m_OwnerMapWriteDeps;
		return m_ReusedOwnerMap;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier1>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_ReusedOwnerMap = new NativeHashMap<OwnerDefinition, Entity>(32, Allocator.Persistent);
		m_DefinitionQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<CreationDefinition>(),
				ComponentType.ReadOnly<Updated>()
			},
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<ObjectDefinition>(),
				ComponentType.ReadOnly<NetCourse>()
			}
		});
		m_DeletedQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.Object>(), ComponentType.ReadOnly<Deleted>(), ComponentType.ReadOnly<Temp>(), ComponentType.ReadOnly<PrefabRef>());
		m_SubTypes = new ComponentTypeSet(ComponentType.ReadWrite<Game.Objects.SubObject>(), ComponentType.ReadWrite<Game.Net.SubNet>(), ComponentType.ReadWrite<Game.Areas.SubArea>());
		m_StoppedUpdateFrameTypes = new ComponentTypeSet(ComponentType.ReadWrite<Stopped>(), ComponentType.ReadWrite<ParkedCar>(), ComponentType.ReadWrite<ParkedTrain>(), ComponentType.ReadWrite<UpdateFrame>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		RequireForUpdate(m_DefinitionQuery);
		RequireForUpdate(m_EconomyParameterQuery);
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
		m_OwnerMapReadDeps.Complete();
		m_OwnerMapWriteDeps.Complete();
		m_ReusedOwnerMap.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		m_OwnerMapReadDeps.Complete();
		m_OwnerMapWriteDeps.Complete();
		m_ReusedOwnerMap.Clear();
		base.OnStopRunning();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		NativeQueue<CreationData> creationQueue = new NativeQueue<CreationData>(Allocator.TempJob);
		NativeList<CreationData> nativeList = new NativeList<CreationData>(Allocator.TempJob);
		NativeParallelMultiHashMap<OldObjectKey, OldObjectValue> oldObjectMap = new NativeParallelMultiHashMap<OldObjectKey, OldObjectValue>(32, Allocator.TempJob);
		m_OwnerMapReadDeps.Complete();
		m_OwnerMapWriteDeps.Complete();
		m_ReusedOwnerMap.Clear();
		JobHandle dependencies;
		FillCreationListJob jobData = new FillCreationListJob
		{
			m_CreationDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_CreationDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OwnerDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_OwnerDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ObjectDefinitionType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_ObjectDefinition_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_NetCourseType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_NetCourse_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_AttachedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DeletedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Deleted_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabLocalConnectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LocalConnectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoadData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RoadData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
			m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LocalConnectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LocalConnect_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RoundaboutData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Roundabout_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
			m_ConnectedNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedNode_RO_BufferLookup, ref base.CheckedStateRef),
			m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies),
			m_CreationQueue = creationQueue.AsParallelWriter()
		};
		FillOldObjectsJob jobData2 = new FillOldObjectsJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TempType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_EditorContainerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabRefType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_OldObjectMap = oldObjectMap
		};
		CollectCreationDataJob jobData3 = new CollectCreationDataJob
		{
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CreationQueue = creationQueue,
			m_CreationList = nativeList,
			m_OldObjectMap = oldObjectMap,
			m_ReusedOwnerMap = m_ReusedOwnerMap
		};
		CreateObjectsJob jobData4 = new CreateObjectsJob
		{
			m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_RandomSeed = RandomSeed.Next(),
			m_SubTypes = m_SubTypes,
			m_StoppedUpdateFrameTypes = m_StoppedUpdateFrameTypes,
			m_CreationList = nativeList.AsDeferredJobArray(),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_NativeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Native_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StoppedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Stopped_RO_ComponentLookup, ref base.CheckedStateRef),
			m_AttachedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RelativeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Relative_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RecentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Recent_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TreeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Tree_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DestroyedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DamagedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Damaged_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PseudoRandomSeedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_PseudoRandomSeed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SurfaceData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Surface_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Stack_RO_ComponentLookup, ref base.CheckedStateRef),
			m_UnderConstructionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_UnderConstruction_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PlaceableObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceableObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceUpgradeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ServiceUpgradeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MovingObjectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_MovingObjectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTreeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TreeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabEffectData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_EffectData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabStackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StackData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EconomyParameterData = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>()
		};
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_DefinitionQuery, JobHandle.CombineDependencies(base.Dependency, dependencies));
		JobHandle job = JobChunkExtensions.Schedule(jobData2, m_DeletedQuery, base.Dependency);
		JobHandle jobHandle2 = IJobExtensions.Schedule(jobData3, JobHandle.CombineDependencies(jobHandle, job));
		JobHandle jobHandle3 = jobData4.Schedule(nativeList, 1, jobHandle2);
		creationQueue.Dispose(jobHandle2);
		nativeList.Dispose(jobHandle3);
		oldObjectMap.Dispose(jobHandle2);
		m_ModificationBarrier.AddJobHandleForProducer(jobHandle3);
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
		m_OwnerMapWriteDeps = jobHandle2;
		base.Dependency = jobHandle3;
	}
```


## Nested types

- `Game.Tools.GenerateObjectsSystem+CreationData`  
- `Game.Tools.GenerateObjectsSystem+OldObjectKey`  
- `Game.Tools.GenerateObjectsSystem+OldObjectValue`  
- `Game.Tools.GenerateObjectsSystem+FillOldObjectsJob`  
- `Game.Tools.GenerateObjectsSystem+FillCreationListJob`  
- `Game.Tools.GenerateObjectsSystem+CollectCreationDataJob`  
- `Game.Tools.GenerateObjectsSystem+CreateObjectsJob`  
- `Game.Tools.GenerateObjectsSystem+TypeHandle`  

