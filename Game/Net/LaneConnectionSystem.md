# Game.Net.LaneConnectionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Net`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LaneConnectionSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
    private Unity.Entities.EntityQuery m_UpdatedQuery;
    private Game.Net.LaneConnectionSystem+TypeHandle __TypeHandle;

    public LaneConnectionSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Common.ModificationBarrier5 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_ModificationBarrier;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem`  

```csharp
private Game.Areas.UpdateCollectSystem m_AreaUpdateCollectSystem;
```

- `private Unity.Entities.EntityQuery m_UpdatedQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedQuery;
```

- `private Game.Net.LaneConnectionSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Net.LaneConnectionSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LaneConnectionSystem()`  

```csharp
[Preserve]
	public LaneConnectionSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_AreaUpdateCollectSystem = base.World.GetOrCreateSystemManaged<Game.Areas.UpdateCollectSystem>();
		m_UpdatedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Updated>(),
				ComponentType.ReadOnly<SubLane>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Edge>(),
				ComponentType.ReadOnly<Node>(),
				ComponentType.ReadOnly<Object>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
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
		bool flag = !m_UpdatedQuery.IsEmptyIgnoreFilter;
		if (flag || m_AreaUpdateCollectSystem.lotsUpdated || m_AreaUpdateCollectSystem.spacesUpdated)
		{
			NativeQueue<Entity> updatedQueue = new NativeQueue<Entity>(Allocator.TempJob);
			NativeQueue<Entity> updatedQueue2 = new NativeQueue<Entity>(Allocator.TempJob);
			NativeQueue<Entity> nativeQueue = new NativeQueue<Entity>(Allocator.TempJob);
			NativeList<Entity> nativeList = new NativeList<Entity>(Allocator.TempJob);
			JobHandle jobHandle = default(JobHandle);
			if (m_AreaUpdateCollectSystem.lotsUpdated)
			{
				JobHandle dependencies;
				NativeList<Bounds2> updatedLotBounds = m_AreaUpdateCollectSystem.GetUpdatedLotBounds(out dependencies);
				JobHandle dependencies2;
				JobHandle jobHandle2 = new FindUpdatedLanesJob
				{
					m_Bounds = updatedLotBounds.AsDeferredJobArray(),
					m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies2),
					m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
					m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
					m_ResultQueue = updatedQueue.AsParallelWriter()
				}.Schedule(updatedLotBounds, 1, JobHandle.CombineDependencies(base.Dependency, dependencies, dependencies2));
				m_AreaUpdateCollectSystem.AddLotBoundsReader(jobHandle2);
				m_NetSearchSystem.AddNetSearchTreeReader(jobHandle2);
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
			}
			if (m_AreaUpdateCollectSystem.spacesUpdated)
			{
				JobHandle dependencies3;
				NativeList<Bounds2> updatedSpaceBounds = m_AreaUpdateCollectSystem.GetUpdatedSpaceBounds(out dependencies3);
				JobHandle dependencies4;
				JobHandle jobHandle3 = new FindUpdatedLanesJob
				{
					m_Bounds = updatedSpaceBounds.AsDeferredJobArray(),
					m_NetSearchTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies4),
					m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
					m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
					m_ResultQueue = updatedQueue2.AsParallelWriter()
				}.Schedule(updatedSpaceBounds, 1, JobHandle.CombineDependencies(base.Dependency, dependencies3, dependencies4));
				m_AreaUpdateCollectSystem.AddSpaceBoundsReader(jobHandle3);
				m_NetSearchSystem.AddNetSearchTreeReader(jobHandle3);
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle3);
			}
			if (flag)
			{
				JobHandle outJobHandle;
				CheckUpdatedLanesJob jobData = new CheckUpdatedLanesJob
				{
					m_Chunks = m_UpdatedQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle),
					m_OwnerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Owner_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_SubLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
					m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
					m_SpawnLocations = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_SpawnLocationElement_RO_BufferLookup, ref base.CheckedStateRef),
					m_ResultQueue = nativeQueue
				};
				JobHandle jobHandle4 = IJobExtensions.Schedule(jobData, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
				jobData.m_Chunks.Dispose(jobHandle4);
				jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle4);
			}
			ListUpdatedLanesJob jobData2 = new ListUpdatedLanesJob
			{
				m_UpdatedQueue1 = updatedQueue,
				m_UpdatedQueue2 = updatedQueue2,
				m_UpdatedQueue3 = nativeQueue,
				m_UpdatedList = nativeList
			};
			JobHandle dependencies5;
			FindLaneConnectionJob jobData3 = new FindLaneConnectionJob
			{
				m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Owner_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Lane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SlaveLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_SlaveLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ConnectionLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ConnectionLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNetLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NetLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabCarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CarLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ParkingLaneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabNavigationAreaData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_NavigationAreaData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LaneConnectionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LaneConnection_RW_ComponentLookup, ref base.CheckedStateRef),
				m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ParkingLane_RW_ComponentLookup, ref base.CheckedStateRef),
				m_Lanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
				m_AreaNodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
				m_AreaTriangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
				m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
				m_Entities = nativeList.AsDeferredJobArray(),
				m_AreaSearchTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies5),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			JobHandle jobHandle5 = IJobExtensions.Schedule(jobData2, jobHandle);
			JobHandle jobHandle6 = jobData3.Schedule(nativeList, 1, JobHandle.CombineDependencies(jobHandle5, dependencies5));
			updatedQueue.Dispose(jobHandle5);
			updatedQueue2.Dispose(jobHandle5);
			nativeQueue.Dispose(jobHandle5);
			nativeList.Dispose(jobHandle6);
			m_AreaSearchSystem.AddSearchTreeReader(jobHandle6);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle6);
			base.Dependency = jobHandle6;
		}
	}
```


## Nested types

- `Game.Net.LaneConnectionSystem+FindUpdatedLanesJob`  
- `Game.Net.LaneConnectionSystem+CheckUpdatedLanesJob`  
- `Game.Net.LaneConnectionSystem+ListUpdatedLanesJob`  
- `Game.Net.LaneConnectionSystem+FindLaneConnectionJob`  
- `Game.Net.LaneConnectionSystem+TypeHandle`  

