# Game.Areas.CurrentDistrictSystem

**Assembly:** `Game`  
**Namespace:** `Game.Areas`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CurrentDistrictSystem : Game.GameSystemBase
{
    private Game.Areas.UpdateCollectSystem m_UpdateCollectSystem;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Objects.SearchSystem m_ObjectSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_CurrentDistrictQuery;
    private Game.Areas.CurrentDistrictSystem+TypeHandle __TypeHandle;

    public CurrentDistrictSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Areas.UpdateCollectSystem m_UpdateCollectSystem`  

```csharp
private Game.Areas.UpdateCollectSystem m_UpdateCollectSystem;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
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

- `private Unity.Entities.EntityQuery m_CurrentDistrictQuery`  

```csharp
private Unity.Entities.EntityQuery m_CurrentDistrictQuery;
```

- `private Game.Areas.CurrentDistrictSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Areas.CurrentDistrictSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CurrentDistrictSystem()`  

```csharp
[Preserve]
	public CurrentDistrictSystem()
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
		m_UpdateCollectSystem = base.World.GetOrCreateSystemManaged<UpdateCollectSystem>();
		m_AreaSearchSystem = base.World.GetOrCreateSystemManaged<SearchSystem>();
		m_ObjectSearchSystem = base.World.GetOrCreateSystemManaged<Game.Objects.SearchSystem>();
		m_NetSearchSystem = base.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_CurrentDistrictQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Updated>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<CurrentDistrict>(),
				ComponentType.ReadOnly<BorderDistrict>()
			}
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
		if (!m_CurrentDistrictQuery.IsEmptyIgnoreFilter || m_UpdateCollectSystem.districtsUpdated)
		{
			if (m_UpdateCollectSystem.districtsUpdated)
			{
				NativeQueue<Entity> updateBuffer = new NativeQueue<Entity>(Allocator.TempJob);
				NativeList<Entity> nativeList = new NativeList<Entity>(Allocator.TempJob);
				JobHandle dependencies;
				NativeList<Bounds2> updatedDistrictBounds = m_UpdateCollectSystem.GetUpdatedDistrictBounds(out dependencies);
				JobHandle dependencies2;
				JobHandle dependencies3;
				FindUpdatedDistrictItemsJob jobData = new FindUpdatedDistrictItemsJob
				{
					m_Bounds = updatedDistrictBounds.AsDeferredJobArray(),
					m_ObjectTree = m_ObjectSearchSystem.GetStaticSearchTree(readOnly: true, out dependencies2),
					m_NetTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies3),
					m_CurrentDistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_CurrentDistrict_RO_ComponentLookup, ref base.CheckedStateRef),
					m_BorderDistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_BorderDistrict_RO_ComponentLookup, ref base.CheckedStateRef),
					m_UpdateBuffer = updateBuffer.AsParallelWriter()
				};
				CollectUpdatedDistrictItemsJob jobData2 = new CollectUpdatedDistrictItemsJob
				{
					m_UpdateBuffer = updateBuffer,
					m_UpdateList = nativeList
				};
				JobHandle dependencies4;
				FindDistrictParallelJob jobData3 = new FindDistrictParallelJob
				{
					m_UpdateList = nativeList.AsDeferredJobArray(),
					m_AreaTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies4),
					m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter(),
					m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
					m_EdgeGeometryData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentLookup, ref base.CheckedStateRef),
					m_DistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_District_RO_ComponentLookup, ref base.CheckedStateRef),
					m_UpdatedData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Updated_RO_ComponentLookup, ref base.CheckedStateRef),
					m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
					m_PedestrianLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_PedestrianLane_RO_ComponentLookup, ref base.CheckedStateRef),
					m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentLookup, ref base.CheckedStateRef),
					m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
					m_Nodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
					m_Triangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef),
					m_CurrentDistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_CurrentDistrict_RW_ComponentLookup, ref base.CheckedStateRef),
					m_BorderDistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_BorderDistrict_RW_ComponentLookup, ref base.CheckedStateRef)
				};
				JobHandle job = JobHandle.CombineDependencies(dependencies, dependencies2, dependencies3);
				JobHandle jobHandle = jobData.Schedule(updatedDistrictBounds, 1, JobHandle.CombineDependencies(base.Dependency, job));
				JobHandle jobHandle2 = IJobExtensions.Schedule(jobData2, jobHandle);
				JobHandle jobHandle3 = jobData3.Schedule(nativeList, 1, JobHandle.CombineDependencies(jobHandle2, dependencies4));
				updateBuffer.Dispose(jobHandle2);
				nativeList.Dispose(jobHandle3);
				m_UpdateCollectSystem.AddDistrictBoundsReader(jobHandle);
				m_ObjectSearchSystem.AddStaticSearchTreeReader(jobHandle);
				m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
				m_AreaSearchSystem.AddSearchTreeReader(jobHandle3);
				m_ModificationBarrier.AddJobHandleForProducer(jobHandle3);
				base.Dependency = jobHandle3;
			}
			if (!m_CurrentDistrictQuery.IsEmptyIgnoreFilter)
			{
				JobHandle dependencies5;
				JobHandle jobHandle4 = JobChunkExtensions.ScheduleParallel(new FindDistrictChunkJob
				{
					m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_EdgeGeometryType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Net_EdgeGeometry_RO_ComponentTypeHandle, ref base.CheckedStateRef),
					m_CurrentDistrictType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_CurrentDistrict_RW_ComponentTypeHandle, ref base.CheckedStateRef),
					m_BorderDistrictType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_BorderDistrict_RW_ComponentTypeHandle, ref base.CheckedStateRef),
					m_AreaTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies5),
					m_DistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_District_RO_ComponentLookup, ref base.CheckedStateRef),
					m_Nodes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Node_RO_BufferLookup, ref base.CheckedStateRef),
					m_Triangles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_Triangle_RO_BufferLookup, ref base.CheckedStateRef)
				}, m_CurrentDistrictQuery, JobHandle.CombineDependencies(base.Dependency, dependencies5));
				m_AreaSearchSystem.AddSearchTreeReader(jobHandle4);
				base.Dependency = jobHandle4;
			}
		}
	}
```


## Nested types

- `Game.Areas.CurrentDistrictSystem+FindUpdatedDistrictItemsJob`  
- `Game.Areas.CurrentDistrictSystem+CollectUpdatedDistrictItemsJob`  
- `Game.Areas.CurrentDistrictSystem+FindDistrictParallelJob`  
- `Game.Areas.CurrentDistrictSystem+FindDistrictChunkJob`  
- `Game.Areas.CurrentDistrictSystem+DistrictIterator`  
- `Game.Areas.CurrentDistrictSystem+TypeHandle`  

