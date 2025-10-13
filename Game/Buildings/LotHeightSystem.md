# Game.Buildings.LotHeightSystem

**Assembly:** `Game`  
**Namespace:** `Game.Buildings`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LotHeightSystem : Game.GameSystemBase
{
    private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem;
    private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_UpdateQuery;
    private Unity.Entities.EntityQuery m_AllQuery;
    private System.Boolean m_Loaded;
    private Game.Buildings.LotHeightSystem+TypeHandle __TypeHandle;

    public LotHeightSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetLoaded();
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
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

- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  

```csharp
private Game.Objects.SearchSystem m_ObjectSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_UpdateQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdateQuery;
```

- `private Unity.Entities.EntityQuery m_AllQuery`  

```csharp
private Unity.Entities.EntityQuery m_AllQuery;
```

- `private System.Boolean m_Loaded`  

```csharp
private System.Boolean m_Loaded;
```

- `private Game.Buildings.LotHeightSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Buildings.LotHeightSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LotHeightSystem()`  

```csharp
[Preserve]
	public LotHeightSystem()
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

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ObjectUpdateCollectSystem = base.World.GetOrCreateSystemManaged<Game.Objects.UpdateCollectSystem>();
		m_NetUpdateCollectSystem = base.World.GetOrCreateSystemManaged<Game.Net.UpdateCollectSystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_UpdateQuery = GetEntityQuery(ComponentType.ReadWrite<Lot>(), ComponentType.ReadOnly<Updated>(), ComponentType.Exclude<Deleted>());
		m_AllQuery = GetEntityQuery(ComponentType.ReadWrite<Lot>(), ComponentType.Exclude<Deleted>());
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		m_Loaded = true;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		bool loaded = GetLoaded();
		EntityQuery query = (loaded ? m_AllQuery : m_UpdateQuery);
		bool flag = !query.IsEmptyIgnoreFilter;
		if (m_ObjectUpdateCollectSystem.isUpdated || m_NetUpdateCollectSystem.netsUpdated || flag)
		{
			JobHandle dependencies;
			NativeQuadTree<Entity, QuadTreeBoundsXZ> staticSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies);
			NativeList<Entity> nativeList = new NativeList<Entity>(Allocator.TempJob);
			NativeQueue<Entity> queue = default(NativeQueue<Entity>);
			NativeQueue<Entity> queue2 = default(NativeQueue<Entity>);
			JobHandle jobHandle = default(JobHandle);
			if (flag)
			{
				JobHandle job = JobChunkExtensions.Schedule(new AddUpdatedLotsJob
				{
					m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
					m_ResultList = nativeList
				}, query, base.Dependency);
				jobHandle = JobHandle.CombineDependencies(jobHandle, job);
			}
			if (m_ObjectUpdateCollectSystem.isUpdated)
			{
				JobHandle dependencies2;
				NativeList<Bounds2> updatedBounds = m_ObjectUpdateCollectSystem.GetUpdatedBounds(out dependencies2);
				queue = new NativeQueue<Entity>(Allocator.TempJob);
				JobHandle jobHandle2 = new FindUpdatedLotsJob
				{
					m_Bounds = updatedBounds.AsDeferredJobArray(),
					m_SearchTree = staticSearchTree,
					m_LotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Lot_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ResultQueue = queue.AsParallelWriter()
				}.Schedule(updatedBounds, 1, JobHandle.CombineDependencies(base.Dependency, dependencies2, dependencies));
				m_ObjectUpdateCollectSystem.AddBoundsReader(jobHandle2);
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
			}
			if (m_NetUpdateCollectSystem.netsUpdated)
			{
				JobHandle dependencies3;
				NativeList<Bounds2> updatedNetBounds = m_NetUpdateCollectSystem.GetUpdatedNetBounds(out dependencies3);
				queue2 = new NativeQueue<Entity>(Allocator.TempJob);
				JobHandle jobHandle3 = new FindUpdatedLotsJob
				{
					m_Bounds = updatedNetBounds.AsDeferredJobArray(),
					m_SearchTree = staticSearchTree,
					m_LotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Lot_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ResultQueue = queue2.AsParallelWriter()
				}.Schedule(updatedNetBounds, 1, JobHandle.CombineDependencies(base.Dependency, dependencies3, dependencies));
				m_NetUpdateCollectSystem.AddNetBoundsReader(jobHandle3);
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle3);
			}
			CollectLotsJob jobData = new CollectLotsJob
			{
				m_Queue1 = queue,
				m_Queue2 = queue2,
				m_ResultList = nativeList
			};
			JobHandle dependencies4;
			UpdateLotHeightsJob jobData2 = new UpdateLotHeightsJob
			{
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_StartNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EndNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OrphanData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Orphan_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NodeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Node_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Edge_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabBuildingExtensionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingExtensionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabBuildingTerraformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingTerraformData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Lot_RW_ComponentLookup, ref base.CheckedStateRef),
				m_IsLoaded = loaded,
				m_LotList = nativeList,
				m_StaticObjectSearchTree = staticSearchTree,
				m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies4),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			JobHandle jobHandle4 = IJobExtensions.Schedule(jobData, jobHandle);
			JobHandle jobHandle5 = jobData2.Schedule(nativeList, 1, JobHandle.CombineDependencies(jobHandle4, dependencies, dependencies4));
			if (queue.IsCreated)
			{
				queue.Dispose(jobHandle4);
			}
			if (queue2.IsCreated)
			{
				queue2.Dispose(jobHandle4);
			}
			nativeList.Dispose(jobHandle5);
			m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle5);
			m_NetSearchSystem.AddNetSearchTreeReader(jobHandle5);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle5);
			base.Dependency = jobHandle5;
		}
	}
```


## Nested types

- `Game.Buildings.LotHeightSystem+AddUpdatedLotsJob`  
- `Game.Buildings.LotHeightSystem+FindUpdatedLotsJob`  
- `Game.Buildings.LotHeightSystem+CollectLotsJob`  
- `Game.Buildings.LotHeightSystem+Heights`  
- `Game.Buildings.LotHeightSystem+UpdateLotHeightsJob`  
- `Game.Buildings.LotHeightSystem+TypeHandle`  

