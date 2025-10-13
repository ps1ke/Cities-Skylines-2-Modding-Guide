# Game.Objects.OverrideSystem

**Assembly:** `Game`  
**Namespace:** `Game.Objects`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class OverrideSystem : Game.GameSystemBase
{
    private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem;
    private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
    private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Unity.Entities.ComponentTypeSet m_OverriddenUpdatedSet;
    private Game.Objects.OverrideSystem+TypeHandle __TypeHandle;

    public OverrideSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle CollectUpdatedObjects(Unity.Collections.NativeList<Unity.Entities.Entity> updateObjectsList, Unity.Collections.NativeHashSet<Unity.Entities.Entity> objectSet);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem`  

```csharp
private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem;
```

- `private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem`  

```csharp
private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
```

- `private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem`  

```csharp
private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
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

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Unity.Entities.ComponentTypeSet m_OverriddenUpdatedSet`  

```csharp
private Unity.Entities.ComponentTypeSet m_OverriddenUpdatedSet;
```

- `private Game.Objects.OverrideSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Objects.OverrideSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public OverrideSystem()`  

```csharp
[Preserve]
	public OverrideSystem()
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

- `private CollectUpdatedObjects(Unity.Collections.NativeList<Unity.Entities.Entity> updateObjectsList, Unity.Collections.NativeHashSet<Unity.Entities.Entity> objectSet) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle CollectUpdatedObjects(NativeList<Entity> updateObjectsList, NativeHashSet<Entity> objectSet)
	{
		NativeQueue<Entity> queue = new NativeQueue<Entity>(Allocator.TempJob);
		NativeQueue<Entity> queue2 = new NativeQueue<Entity>(Allocator.TempJob);
		NativeQueue<Entity> queue3 = new NativeQueue<Entity>(Allocator.TempJob);
		JobHandle dependencies;
		NativeQuadTree<Entity, QuadTreeBoundsXZ> staticSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies);
		JobHandle jobHandle = default(JobHandle);
		if (m_ObjectUpdateCollectSystem.isUpdated)
		{
			JobHandle dependencies2;
			NativeList<Bounds2> updatedBounds = m_ObjectUpdateCollectSystem.GetUpdatedBounds(out dependencies2);
			JobHandle jobHandle2 = new FindUpdatedObjectsJob
			{
				m_Bounds = updatedBounds.AsDeferredJobArray(),
				m_SearchTree = staticSearchTree,
				m_ResultQueue = queue.AsParallelWriter()
			}.Schedule(updatedBounds, 1, JobHandle.CombineDependencies(dependencies2, dependencies));
			m_ObjectUpdateCollectSystem.AddBoundsReader(jobHandle2);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
		}
		if (m_NetUpdateCollectSystem.netsUpdated)
		{
			JobHandle dependencies3;
			NativeList<Bounds2> updatedNetBounds = m_NetUpdateCollectSystem.GetUpdatedNetBounds(out dependencies3);
			JobHandle jobHandle3 = new FindUpdatedObjectsJob
			{
				m_Bounds = updatedNetBounds.AsDeferredJobArray(),
				m_SearchTree = staticSearchTree,
				m_ResultQueue = queue2.AsParallelWriter()
			}.Schedule(updatedNetBounds, 1, JobHandle.CombineDependencies(dependencies3, dependencies));
			m_NetUpdateCollectSystem.AddNetBoundsReader(jobHandle3);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle3);
		}
		if (m_AreaUpdateCollectSystem.lotsUpdated)
		{
			JobHandle dependencies4;
			NativeList<Bounds2> updatedLotBounds = m_AreaUpdateCollectSystem.GetUpdatedLotBounds(out dependencies4);
			JobHandle jobHandle4 = new FindUpdatedObjectsJob
			{
				m_Bounds = updatedLotBounds.AsDeferredJobArray(),
				m_SearchTree = staticSearchTree,
				m_ResultQueue = queue3.AsParallelWriter()
			}.Schedule(updatedLotBounds, 1, JobHandle.CombineDependencies(dependencies4, dependencies));
			m_AreaUpdateCollectSystem.AddLotBoundsReader(jobHandle4);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle4);
		}
		JobHandle jobHandle5 = IJobExtensions.Schedule(new CollectObjectsJob
		{
			m_Queue1 = queue,
			m_Queue2 = queue2,
			m_Queue3 = queue3,
			m_ResultList = updateObjectsList,
			m_ObjectSet = objectSet
		}, jobHandle);
		queue.Dispose(jobHandle5);
		queue2.Dispose(jobHandle5);
		queue3.Dispose(jobHandle5);
		m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle);
		return jobHandle5;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ObjectUpdateCollectSystem = base.World.GetOrCreateSystemManaged<UpdateCollectSystem>();
		m_NetUpdateCollectSystem = base.World.GetOrCreateSystemManaged<Game.Net.UpdateCollectSystem>();
		m_AreaUpdateCollectSystem = base.World.GetOrCreateSystemManaged<Game.Areas.UpdateCollectSystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
		m_OverriddenUpdatedSet = new ComponentTypeSet(ComponentType.ReadWrite<Overridden>(), ComponentType.ReadWrite<Updated>());
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
		if (m_ObjectUpdateCollectSystem.isUpdated || m_NetUpdateCollectSystem.netsUpdated || m_AreaUpdateCollectSystem.lotsUpdated)
		{
			NativeList<Entity> nativeList = new NativeList<Entity>(Allocator.TempJob);
			NativeHashSet<Entity> objectSet = new NativeHashSet<Entity>(100, Allocator.TempJob);
			NativeQueue<TreeAction> actions = new NativeQueue<TreeAction>(Allocator.TempJob);
			NativeQueue<OverridableAction> overridableActions = new NativeQueue<OverridableAction>(Allocator.TempJob);
			base.Dependency = JobHandle.CombineDependencies(base.Dependency, CollectUpdatedObjects(nativeList, objectSet));
			JobHandle dependencies;
			JobHandle dependencies2;
			JobHandle dependencies3;
			CheckObjectOverrideJob jobData = new CheckObjectOverrideJob
			{
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CreatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Created_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OverriddenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Overridden_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AttachmentData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attachment_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AttachedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
				m_StackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Stack_RO_ComponentLookup, ref base.CheckedStateRef),
				m_MarkerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Marker_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OutsideConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_OutsideConnection_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_StartNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EndNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabAreaGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabStackData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_StackData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
				m_ConnectedEdges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedEdge_RO_BufferLookup, ref base.CheckedStateRef),
				m_ConnectedNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ConnectedNode_RO_BufferLookup, ref base.CheckedStateRef),
				m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
				m_AreaTriangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
				m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
				m_ObjectArray = nativeList.AsDeferredJobArray(),
				m_ObjectSet = objectSet,
				m_ObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies),
				m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies2),
				m_AreaSearchTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies3),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter(),
				m_TreeActions = actions.AsParallelWriter(),
				m_OverridableActions = overridableActions.AsParallelWriter()
			};
			JobHandle dependencies4;
			UpdateObjectOverrideJob jobData2 = new UpdateObjectOverrideJob
			{
				m_OverriddenUpdatedSet = m_OverriddenUpdatedSet,
				m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
				m_ObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: false, out dependencies4),
				m_Actions = actions,
				m_OverridableActions = overridableActions,
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
			};
			JobHandle jobHandle = jobData.Schedule(nativeList, 1, JobHandle.CombineDependencies(base.Dependency, JobHandle.CombineDependencies(dependencies, dependencies2, dependencies3)));
			JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(jobHandle, dependencies4));
			nativeList.Dispose(jobHandle);
			objectSet.Dispose(jobHandle);
			actions.Dispose(jobHandle2);
			overridableActions.Dispose(jobHandle2);
			m_ObjectSearchSystem.AddStaticSearchTreeWriter(jobHandle2);
			m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
			m_AreaSearchSystem.AddSearchTreeReader(jobHandle);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
			base.Dependency = jobHandle2;
		}
	}
```


## Nested types

- `Game.Objects.OverrideSystem+TreeAction`  
- `Game.Objects.OverrideSystem+OverridableAction`  
- `Game.Objects.OverrideSystem+UpdateObjectOverrideJob`  
- `Game.Objects.OverrideSystem+FindUpdatedObjectsJob`  
- `Game.Objects.OverrideSystem+CollectObjectsJob`  
- `Game.Objects.OverrideSystem+CheckObjectOverrideJob`  
- `Game.Objects.OverrideSystem+TypeHandle`  

