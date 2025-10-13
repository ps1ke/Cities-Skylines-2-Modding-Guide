# Game.Net.OverrideSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class OverrideSystem : Game.GameSystemBase
{
    private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Tools.ToolSystem m_ToolSystem;
    private Game.Net.OverrideSystem+TypeHandle __TypeHandle;
    private static const System.Single MIN_PARALLEL_FENCE_DISTANCE;

    public OverrideSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle CollectUpdatedLanes(Unity.Collections.NativeList<Unity.Entities.Entity> updateLanesList);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem`  

```csharp
private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Game.Tools.ToolSystem m_ToolSystem`  

```csharp
private Game.Tools.ToolSystem m_ToolSystem;
```

- `private Game.Net.OverrideSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.OverrideSystem+TypeHandle __TypeHandle;
```

- `private static const System.Single MIN_PARALLEL_FENCE_DISTANCE`  

```csharp
private static const System.Single MIN_PARALLEL_FENCE_DISTANCE;
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

- `private CollectUpdatedLanes(Unity.Collections.NativeList<Unity.Entities.Entity> updateLanesList) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle CollectUpdatedLanes(NativeList<Entity> updateLanesList)
	{
		NativeQueue<Entity> queue = new NativeQueue<Entity>(Allocator.TempJob);
		JobHandle dependencies;
		NativeQuadTree<Entity, QuadTreeBoundsXZ> laneSearchTree = m_NetSearchSystem.GetLaneSearchTree(readOnly: true, out dependencies);
		JobHandle jobHandle = default(JobHandle);
		if (m_NetUpdateCollectSystem.lanesUpdated)
		{
			JobHandle dependencies2;
			NativeList<Bounds2> updatedLaneBounds = m_NetUpdateCollectSystem.GetUpdatedLaneBounds(out dependencies2);
			JobHandle jobHandle2 = new FindUpdatedLanesJob
			{
				m_Bounds = updatedLaneBounds.AsDeferredJobArray(),
				m_SearchTree = laneSearchTree,
				m_ResultQueue = queue.AsParallelWriter()
			}.Schedule(updatedLaneBounds, 1, JobHandle.CombineDependencies(dependencies2, dependencies));
			m_NetUpdateCollectSystem.AddLaneBoundsReader(jobHandle2);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
		}
		JobHandle jobHandle3 = IJobExtensions.Schedule(new CollectObjectsJob
		{
			m_Queue = queue,
			m_ResultList = updateLanesList
		}, jobHandle);
		queue.Dispose(jobHandle3);
		m_NetSearchSystem.AddLaneSearchTreeReader(jobHandle);
		return jobHandle3;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_NetUpdateCollectSystem = base.World.GetOrCreateSystemManaged<UpdateCollectSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_ToolSystem = base.World.GetOrCreateSystemManaged<ToolSystem>();
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
		if (m_NetUpdateCollectSystem.lanesUpdated)
		{
			NativeList<Entity> nativeList = new NativeList<Entity>(Allocator.TempJob);
			NativeQueue<TreeAction> actions = new NativeQueue<TreeAction>(Allocator.TempJob);
			base.Dependency = JobHandle.CombineDependencies(base.Dependency, CollectUpdatedLanes(nativeList));
			JobHandle dependencies;
			CheckLaneOverrideJob jobData = new CheckLaneOverrideJob
			{
				m_OverriddenData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Overridden_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_UtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_UtilityLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabUtilityLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_UtilityLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabLaneGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CutRanges = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_CutRange_RW_BufferLookup, ref base.CheckedStateRef),
				m_EditorMode = m_ToolSystem.actionMode.IsEditor(),
				m_LaneArray = nativeList.AsDeferredJobArray(),
				m_LaneSearchTree = m_NetSearchSystem.GetLaneSearchTree(readOnly: true, out dependencies),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter(),
				m_TreeActions = actions.AsParallelWriter()
			};
			JobHandle dependencies2;
			UpdateOverriddenLayersJob jobData2 = new UpdateOverriddenLayersJob
			{
				m_LaneSearchTree = m_NetSearchSystem.GetLaneSearchTree(readOnly: false, out dependencies2),
				m_Actions = actions
			};
			JobHandle jobHandle = jobData.Schedule(nativeList, 1, JobHandle.CombineDependencies(base.Dependency, dependencies));
			JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(jobHandle, dependencies2));
			nativeList.Dispose(jobHandle);
			actions.Dispose(jobHandle2);
			m_NetSearchSystem.AddLaneSearchTreeWriter(jobHandle2);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle);
			base.Dependency = jobHandle;
		}
	}
```


## Nested types

- `Game.Net.OverrideSystem+TreeAction`  
- `Game.Net.OverrideSystem+UpdateOverriddenLayersJob`  
- `Game.Net.OverrideSystem+FindUpdatedLanesJob`  
- `Game.Net.OverrideSystem+CollectObjectsJob`  
- `Game.Net.OverrideSystem+CheckLaneOverrideJob`  
- `Game.Net.OverrideSystem+TypeHandle`  

