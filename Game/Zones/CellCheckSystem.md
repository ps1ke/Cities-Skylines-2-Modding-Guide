# Game.Zones.CellCheckSystem

**Assembly:** `Game`  
**Namespace:** `Game.Zones`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CellCheckSystem : Game.GameSystemBase
{
    private Game.Zones.UpdateCollectSystem m_ZoneUpdateCollectSystem;
    private Game.Objects.UpdateCollectSystem m_ObjectUpdateCollectSystem;
    private Game.Net.UpdateCollectSystem m_NetUpdateCollectSystem;
    private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
    private Game.Zones.SearchSystem m_ZoneSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Prefabs.ZoneSystem m_ZonePrefabSystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_DeletedBlocksQuery;
    private Game.Zones.CellCheckSystem+TypeHandle __TypeHandle;

    public CellCheckSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private Unity.Jobs.JobHandle CollectUpdatedBlocks(Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+SortedEntity> updateBlocksList);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Zones.UpdateCollectSystem m_ZoneUpdateCollectSystem`  

```csharp
private Game.Zones.UpdateCollectSystem m_ZoneUpdateCollectSystem;
```

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

- `private Game.Zones.SearchSystem m_ZoneSearchSystem`  

```csharp
private Game.Zones.SearchSystem m_ZoneSearchSystem;
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

- `private Game.Prefabs.ZoneSystem m_ZonePrefabSystem`  

```csharp
private Game.Prefabs.ZoneSystem m_ZonePrefabSystem;
```

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_DeletedBlocksQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedBlocksQuery;
```

- `private Game.Zones.CellCheckSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Zones.CellCheckSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CellCheckSystem()`  

```csharp
[Preserve]
	public CellCheckSystem()
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

- `private CollectUpdatedBlocks(Unity.Collections.NativeList<Game.Zones.CellCheckHelpers+SortedEntity> updateBlocksList) : Unity.Jobs.JobHandle`  

```csharp
private JobHandle CollectUpdatedBlocks(NativeList<CellCheckHelpers.SortedEntity> updateBlocksList)
	{
		NativeQueue<Entity> queue = new NativeQueue<Entity>(Allocator.TempJob);
		NativeQueue<Entity> queue2 = new NativeQueue<Entity>(Allocator.TempJob);
		NativeQueue<Entity> queue3 = new NativeQueue<Entity>(Allocator.TempJob);
		NativeQueue<Entity> queue4 = new NativeQueue<Entity>(Allocator.TempJob);
		JobHandle dependencies;
		NativeQuadTree<Entity, Bounds2> searchTree = m_ZoneSearchSystem.GetSearchTree(readOnly: true, out dependencies);
		JobHandle jobHandle = default(JobHandle);
		if (m_ZoneUpdateCollectSystem.isUpdated)
		{
			JobHandle dependencies2;
			NativeList<Bounds2> updatedBounds = m_ZoneUpdateCollectSystem.GetUpdatedBounds(readOnly: true, out dependencies2);
			JobHandle jobHandle2 = new CellCheckHelpers.FindUpdatedBlocksSingleIterationJob
			{
				m_Bounds = updatedBounds.AsDeferredJobArray(),
				m_SearchTree = searchTree,
				m_ResultQueue = queue.AsParallelWriter()
			}.Schedule(updatedBounds, 1, JobHandle.CombineDependencies(dependencies2, dependencies));
			m_ZoneUpdateCollectSystem.AddBoundsReader(jobHandle2);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
		}
		if (m_ObjectUpdateCollectSystem.isUpdated)
		{
			JobHandle dependencies3;
			NativeList<Bounds2> updatedBounds2 = m_ObjectUpdateCollectSystem.GetUpdatedBounds(out dependencies3);
			JobHandle jobHandle3 = new CellCheckHelpers.FindUpdatedBlocksDoubleIterationJob
			{
				m_Bounds = updatedBounds2.AsDeferredJobArray(),
				m_SearchTree = searchTree,
				m_ResultQueue = queue2.AsParallelWriter()
			}.Schedule(updatedBounds2, 1, JobHandle.CombineDependencies(dependencies3, dependencies));
			m_ObjectUpdateCollectSystem.AddBoundsReader(jobHandle3);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle3);
		}
		if (m_NetUpdateCollectSystem.netsUpdated)
		{
			JobHandle dependencies4;
			NativeList<Bounds2> updatedNetBounds = m_NetUpdateCollectSystem.GetUpdatedNetBounds(out dependencies4);
			JobHandle jobHandle4 = new CellCheckHelpers.FindUpdatedBlocksDoubleIterationJob
			{
				m_Bounds = updatedNetBounds.AsDeferredJobArray(),
				m_SearchTree = searchTree,
				m_ResultQueue = queue3.AsParallelWriter()
			}.Schedule(updatedNetBounds, 1, JobHandle.CombineDependencies(dependencies4, dependencies));
			m_NetUpdateCollectSystem.AddNetBoundsReader(jobHandle4);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle4);
		}
		JobHandle job = dependencies;
		if (m_AreaUpdateCollectSystem.lotsUpdated)
		{
			JobHandle dependencies5;
			NativeList<Bounds2> updatedLotBounds = m_AreaUpdateCollectSystem.GetUpdatedLotBounds(out dependencies5);
			JobHandle jobHandle5 = new CellCheckHelpers.FindUpdatedBlocksDoubleIterationJob
			{
				m_Bounds = updatedLotBounds.AsDeferredJobArray(),
				m_SearchTree = searchTree,
				m_ResultQueue = queue4.AsParallelWriter()
			}.Schedule(updatedLotBounds, 1, JobHandle.CombineDependencies(dependencies5, dependencies));
			m_AreaUpdateCollectSystem.AddLotBoundsReader(jobHandle5);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle5);
			job = jobHandle5;
		}
		if (m_AreaUpdateCollectSystem.mapTilesUpdated)
		{
			JobHandle dependencies6;
			NativeList<Bounds2> updatedMapTileBounds = m_AreaUpdateCollectSystem.GetUpdatedMapTileBounds(out dependencies6);
			JobHandle jobHandle6 = new CellCheckHelpers.FindUpdatedBlocksDoubleIterationJob
			{
				m_Bounds = updatedMapTileBounds.AsDeferredJobArray(),
				m_SearchTree = searchTree,
				m_ResultQueue = queue4.AsParallelWriter()
			}.Schedule(updatedMapTileBounds, 1, JobHandle.CombineDependencies(dependencies6, job));
			m_AreaUpdateCollectSystem.AddMapTileBoundsReader(jobHandle6);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle6);
		}
		JobHandle jobHandle7 = IJobExtensions.Schedule(new CellCheckHelpers.CollectBlocksJob
		{
			m_Queue1 = queue,
			m_Queue2 = queue2,
			m_Queue3 = queue3,
			m_Queue4 = queue4,
			m_ResultList = updateBlocksList
		}, jobHandle);
		queue.Dispose(jobHandle7);
		queue2.Dispose(jobHandle7);
		queue3.Dispose(jobHandle7);
		queue4.Dispose(jobHandle7);
		m_ZoneSearchSystem.AddSearchTreeReader(jobHandle);
		return jobHandle7;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_ZoneUpdateCollectSystem = base.World.GetOrCreateSystemManaged<UpdateCollectSystem>();
		m_ObjectUpdateCollectSystem = base.World.GetOrCreateSystemManaged<Game.Objects.UpdateCollectSystem>();
		m_NetUpdateCollectSystem = base.World.GetOrCreateSystemManaged<Game.Net.UpdateCollectSystem>();
		m_AreaUpdateCollectSystem = base.World.GetOrCreateSystemManaged<Game.Areas.UpdateCollectSystem>();
		m_ZoneSearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_ZonePrefabSystem = base.World.GetOrCreateSystemManaged<ZoneSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_DeletedBlocksQuery = GetEntityQuery(ComponentType.ReadOnly<Block>(), ComponentType.ReadOnly<Deleted>(), ComponentType.Exclude<Temp>());
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
		if (m_ZoneUpdateCollectSystem.isUpdated || m_ObjectUpdateCollectSystem.isUpdated || m_NetUpdateCollectSystem.netsUpdated || m_AreaUpdateCollectSystem.lotsUpdated || m_AreaUpdateCollectSystem.mapTilesUpdated)
		{
			NativeList<CellCheckHelpers.SortedEntity> nativeList = new NativeList<CellCheckHelpers.SortedEntity>(Allocator.TempJob);
			NativeQueue<CellCheckHelpers.BlockOverlap> overlapQueue = new NativeQueue<CellCheckHelpers.BlockOverlap>(Allocator.TempJob);
			NativeList<CellCheckHelpers.BlockOverlap> blockOverlaps = new NativeList<CellCheckHelpers.BlockOverlap>(Allocator.TempJob);
			NativeList<CellCheckHelpers.OverlapGroup> nativeList2 = new NativeList<CellCheckHelpers.OverlapGroup>(Allocator.TempJob);
			NativeQueue<Bounds2> boundsQueue = new NativeQueue<Bounds2>(Allocator.TempJob);
			NativeArray<CellCheckHelpers.SortedEntity> blocks = nativeList.AsDeferredJobArray();
			base.Dependency = JobHandle.CombineDependencies(base.Dependency, CollectUpdatedBlocks(nativeList));
			JobHandle dependencies;
			NativeQuadTree<Entity, Bounds2> searchTree = m_ZoneSearchSystem.GetSearchTree(readOnly: true, out dependencies);
			JobHandle outJobHandle;
			NativeList<ArchetypeChunk> deletedBlockChunks = m_DeletedBlocksQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
			JobHandle dependencies2;
			JobHandle dependencies3;
			CellBlockJobs.BlockCellsJob jobData = new CellBlockJobs.BlockCellsJob
			{
				m_Blocks = blocks,
				m_BlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies2),
				m_AreaSearchTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies3),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_StartNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_StartNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EndNodeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EndNodeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Composition_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetCompositionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRoadCompositionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RoadComposition_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabAreaGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AreaGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_NativeData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Native_RO_ComponentLookup, ref base.CheckedStateRef),
				m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
				m_AreaTriangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
				m_Cells = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Zones_Cell_RW_BufferLookup, ref base.CheckedStateRef),
				m_ValidAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_ValidArea_RW_ComponentLookup, ref base.CheckedStateRef)
			};
			CellCheckHelpers.FindOverlappingBlocksJob jobData2 = new CellCheckHelpers.FindOverlappingBlocksJob
			{
				m_Blocks = blocks,
				m_SearchTree = searchTree,
				m_BlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ValidAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_ValidArea_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildOrderData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_BuildOrder_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ResultQueue = overlapQueue.AsParallelWriter()
			};
			CellCheckHelpers.GroupOverlappingBlocksJob jobData3 = new CellCheckHelpers.GroupOverlappingBlocksJob
			{
				m_Blocks = blocks,
				m_OverlapQueue = overlapQueue,
				m_BlockOverlaps = blockOverlaps,
				m_OverlapGroups = nativeList2
			};
			JobHandle dependencies4;
			CellOccupyJobs.ZoneAndOccupyCellsJob jobData4 = new CellOccupyJobs.ZoneAndOccupyCellsJob
			{
				m_Blocks = blocks,
				m_DeletedBlockChunks = deletedBlockChunks,
				m_ZonePrefabs = m_ZonePrefabSystem.GetPrefabs(),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_BlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ValidAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_ValidArea_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ObjectSearchTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies4),
				m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ElevationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Elevation_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabObjectGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ObjectGeometryData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabSpawnableBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabSignatureBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SignatureBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabPlaceholderBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PlaceholderBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabZoneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Cells = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Zones_Cell_RW_BufferLookup, ref base.CheckedStateRef)
			};
			CellOverlapJobs.CheckBlockOverlapJob jobData5 = new CellOverlapJobs.CheckBlockOverlapJob
			{
				m_BlockOverlaps = blockOverlaps.AsDeferredJobArray(),
				m_OverlapGroups = nativeList2.AsDeferredJobArray(),
				m_ZonePrefabs = m_ZonePrefabSystem.GetPrefabs(),
				m_BlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildOrderData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_BuildOrder_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ZoneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Cells = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Zones_Cell_RW_BufferLookup, ref base.CheckedStateRef),
				m_ValidAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_ValidArea_RW_ComponentLookup, ref base.CheckedStateRef)
			};
			CellCheckHelpers.UpdateBlocksJob jobData6 = new CellCheckHelpers.UpdateBlocksJob
			{
				m_Blocks = blocks,
				m_BlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Cells = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Zones_Cell_RW_BufferLookup, ref base.CheckedStateRef)
			};
			LotSizeJobs.UpdateLotSizeJob jobData7 = new LotSizeJobs.UpdateLotSizeJob
			{
				m_Blocks = blocks,
				m_ZonePrefabs = m_ZonePrefabSystem.GetPrefabs(),
				m_BlockData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_Block_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ValidAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_ValidArea_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildOrderData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Zones_BuildOrder_RO_ComponentLookup, ref base.CheckedStateRef),
				m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ZoneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Cells = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Zones_Cell_RO_BufferLookup, ref base.CheckedStateRef),
				m_SearchTree = searchTree,
				m_VacantLots = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Zones_VacantLot_RW_BufferLookup, ref base.CheckedStateRef),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter(),
				m_BoundsQueue = boundsQueue.AsParallelWriter()
			};
			JobHandle dependencies5;
			LotSizeJobs.UpdateBoundsJob jobData8 = new LotSizeJobs.UpdateBoundsJob
			{
				m_BoundsList = m_ZoneUpdateCollectSystem.GetUpdatedBounds(readOnly: false, out dependencies5),
				m_BoundsQueue = boundsQueue
			};
			JobHandle jobHandle = jobData.Schedule(nativeList, 1, JobHandle.CombineDependencies(base.Dependency, dependencies2, dependencies3));
			JobHandle dependsOn = jobData2.Schedule(nativeList, 1, JobHandle.CombineDependencies(jobHandle, dependencies));
			JobHandle jobHandle2 = IJobExtensions.Schedule(jobData3, dependsOn);
			JobHandle jobHandle3 = jobData4.Schedule(nativeList, 1, JobHandle.CombineDependencies(jobHandle, dependencies4, outJobHandle));
			JobHandle jobHandle4 = jobData5.Schedule(nativeList2, 1, JobHandle.CombineDependencies(jobHandle2, jobHandle3));
			JobHandle jobHandle5 = IJobParallelForDeferExtensions.Schedule(dependsOn: jobData6.Schedule(nativeList, 1, jobHandle4), jobData: jobData7, list: nativeList, innerloopBatchCount: 1);
			JobHandle jobHandle6 = IJobExtensions.Schedule(jobData8, JobHandle.CombineDependencies(jobHandle5, dependencies5));
			nativeList.Dispose(jobHandle5);
			overlapQueue.Dispose(jobHandle2);
			blockOverlaps.Dispose(jobHandle4);
			nativeList2.Dispose(jobHandle4);
			boundsQueue.Dispose(jobHandle6);
			deletedBlockChunks.Dispose(jobHandle3);
			m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
			m_AreaSearchSystem.AddSearchTreeReader(jobHandle);
			m_ZoneSearchSystem.AddSearchTreeReader(jobHandle5);
			m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle3);
			m_ZonePrefabSystem.AddPrefabsReader(jobHandle5);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle5);
			m_ZoneUpdateCollectSystem.AddBoundsWriter(jobHandle6);
			base.Dependency = jobHandle5;
		}
	}
```


## Nested types

- `Game.Zones.CellCheckSystem+TypeHandle`  

