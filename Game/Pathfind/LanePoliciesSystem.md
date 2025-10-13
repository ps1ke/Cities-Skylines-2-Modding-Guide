# Game.Pathfind.LanePoliciesSystem

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LanePoliciesSystem : Game.GameSystemBase
{
    private Game.Common.ModificationBarrier5 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_PolicyModifyQuery;
    private Unity.Entities.EntityQuery m_LaneOwnerQuery;
    private Unity.Entities.EntityQuery m_CarLaneQuery;
    private Unity.Entities.EntityQuery m_ParkingLaneQuery;
    private Game.Pathfind.LanePoliciesSystem+TypeHandle __TypeHandle;

    public LanePoliciesSystem();

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

- `private Unity.Entities.EntityQuery m_PolicyModifyQuery`  

```csharp
private Unity.Entities.EntityQuery m_PolicyModifyQuery;
```

- `private Unity.Entities.EntityQuery m_LaneOwnerQuery`  

```csharp
private Unity.Entities.EntityQuery m_LaneOwnerQuery;
```

- `private Unity.Entities.EntityQuery m_CarLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_CarLaneQuery;
```

- `private Unity.Entities.EntityQuery m_ParkingLaneQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParkingLaneQuery;
```

- `private Game.Pathfind.LanePoliciesSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Pathfind.LanePoliciesSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public LanePoliciesSystem()`  

```csharp
[Preserve]
	public LanePoliciesSystem()
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
		m_PolicyModifyQuery = GetEntityQuery(ComponentType.ReadOnly<Modify>());
		m_LaneOwnerQuery = GetEntityQuery(ComponentType.ReadOnly<BorderDistrict>(), ComponentType.ReadOnly<Game.Net.SubLane>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Updated>(), ComponentType.Exclude<Deleted>());
		m_CarLaneQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.CarLane>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Updated>(), ComponentType.Exclude<Deleted>());
		m_ParkingLaneQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.ParkingLane>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Updated>(), ComponentType.Exclude<Deleted>());
		RequireForUpdate(m_PolicyModifyQuery);
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
		NativeArray<Modify> nativeArray = m_PolicyModifyQuery.ToComponentDataArray<Modify>(Allocator.TempJob);
		NativeParallelHashMap<Entity, LaneCheckMask> checkDistricts = default(NativeParallelHashMap<Entity, LaneCheckMask>);
		NativeList<Entity> nativeList = default(NativeList<Entity>);
		LaneCheckMask laneCheckMask = (LaneCheckMask)0;
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Modify modify = nativeArray[i];
			LaneCheckMask laneCheckMask2 = (LaneCheckMask)0;
			bool flag = false;
			if (base.EntityManager.HasComponent<Game.City.City>(modify.m_Entity))
			{
				if (base.EntityManager.TryGetComponent<CityOptionData>(modify.m_Policy, out var component))
				{
					if (CityUtils.HasOption(component, CityOption.UnlimitedHighwaySpeed))
					{
						laneCheckMask |= LaneCheckMask.CarUnknown;
					}
					if (CityUtils.HasOption(component, CityOption.PaidTaxiStart))
					{
						laneCheckMask |= LaneCheckMask.ParkingUnknown;
					}
				}
				if (base.EntityManager.TryGetBuffer(modify.m_Policy, isReadOnly: true, out DynamicBuffer<CityModifierData> buffer))
				{
					for (int j = 0; j < buffer.Length; j++)
					{
						if (buffer[j].m_Type == CityModifierType.TaxiStartingFee)
						{
							laneCheckMask |= LaneCheckMask.ParkingUnknown;
						}
					}
				}
			}
			if (base.EntityManager.HasComponent<District>(modify.m_Entity))
			{
				if (base.EntityManager.TryGetComponent<DistrictOptionData>(modify.m_Policy, out var component2))
				{
					if (AreaUtils.HasOption(component2, DistrictOption.PaidParking))
					{
						laneCheckMask2 |= LaneCheckMask.ParkingUnknown;
					}
					if (AreaUtils.HasOption(component2, DistrictOption.ForbidCombustionEngines))
					{
						laneCheckMask2 |= LaneCheckMask.CarUnknown;
					}
					if (AreaUtils.HasOption(component2, DistrictOption.ForbidTransitTraffic))
					{
						laneCheckMask2 |= (LaneCheckMask)6;
					}
					if (AreaUtils.HasOption(component2, DistrictOption.ForbidHeavyTraffic))
					{
						laneCheckMask2 |= LaneCheckMask.CarUnknown;
					}
				}
				if (base.EntityManager.TryGetBuffer(modify.m_Policy, isReadOnly: true, out DynamicBuffer<DistrictModifierData> buffer2))
				{
					for (int k = 0; k < buffer2.Length; k++)
					{
						switch (buffer2[k].m_Type)
						{
						case DistrictModifierType.ParkingFee:
							laneCheckMask2 |= LaneCheckMask.ParkingUnknown;
							break;
						case DistrictModifierType.StreetSpeedLimit:
							laneCheckMask2 |= LaneCheckMask.CarUnknown;
							break;
						}
					}
				}
			}
			if (base.EntityManager.HasComponent<Building>(modify.m_Entity))
			{
				if (base.EntityManager.TryGetComponent<BuildingOptionData>(modify.m_Policy, out var component3) && BuildingUtils.HasOption(component3, BuildingOption.PaidParking))
				{
					flag = true;
				}
				if (base.EntityManager.TryGetBuffer(modify.m_Policy, isReadOnly: true, out DynamicBuffer<BuildingModifierData> buffer3))
				{
					for (int l = 0; l < buffer3.Length; l++)
					{
						if (buffer3[l].m_Type == BuildingModifierType.ParkingFee)
						{
							flag = true;
							break;
						}
					}
				}
			}
			if (laneCheckMask2 != 0)
			{
				if (!checkDistricts.IsCreated)
				{
					checkDistricts = new NativeParallelHashMap<Entity, LaneCheckMask>(nativeArray.Length, Allocator.TempJob);
				}
				if (!checkDistricts.TryAdd(modify.m_Entity, laneCheckMask2))
				{
					checkDistricts[modify.m_Entity] = checkDistricts[modify.m_Entity] | laneCheckMask2;
				}
			}
			if (flag)
			{
				if (!nativeList.IsCreated)
				{
					nativeList = new NativeList<Entity>(nativeArray.Length, Allocator.TempJob);
				}
				nativeList.Add(in modify.m_Entity);
			}
		}
		nativeArray.Dispose();
		JobHandle jobHandle = base.Dependency;
		if (laneCheckMask != 0)
		{
			EntityCommandBuffer entityCommandBuffer = m_ModificationBarrier.CreateCommandBuffer();
			if ((laneCheckMask & LaneCheckMask.CarUnknown) != 0)
			{
				entityCommandBuffer.AddComponent<PathfindUpdated>(m_CarLaneQuery, EntityQueryCaptureMode.AtPlayback);
			}
			if ((laneCheckMask & LaneCheckMask.ParkingUnknown) != 0)
			{
				entityCommandBuffer.AddComponent<PathfindUpdated>(m_ParkingLaneQuery, EntityQueryCaptureMode.AtPlayback);
			}
		}
		if (checkDistricts.IsCreated)
		{
			JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(new CheckDistrictLanesJob
			{
				m_BorderDistrictType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Areas_BorderDistrict_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_SubLaneType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_SubLane_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_CarLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_CarLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PedestrianLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_PedestrianLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CheckDistricts = checkDistricts,
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			}, m_LaneOwnerQuery, base.Dependency);
			checkDistricts.Dispose(jobHandle2);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle2);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
		}
		if (nativeList.IsCreated)
		{
			JobHandle jobHandle3 = IJobParallelForExtensions.Schedule(new CheckBuildingLanesJob
			{
				m_SubNets = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubNet_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubLanes = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_SubLane_RO_BufferLookup, ref base.CheckedStateRef),
				m_SubObjects = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Objects_SubObject_RO_BufferLookup, ref base.CheckedStateRef),
				m_ParkingLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_ParkingLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_GarageLaneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_GarageLane_RO_ComponentLookup, ref base.CheckedStateRef),
				m_CheckBuildings = nativeList.AsArray(),
				m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
			}, nativeList.Length, 1, base.Dependency);
			nativeList.Dispose(jobHandle3);
			m_ModificationBarrier.AddJobHandleForProducer(jobHandle3);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle3);
		}
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Pathfind.LanePoliciesSystem+LaneCheckMask`  
- `Game.Pathfind.LanePoliciesSystem+CheckDistrictLanesJob`  
- `Game.Pathfind.LanePoliciesSystem+CheckBuildingLanesJob`  
- `Game.Pathfind.LanePoliciesSystem+TypeHandle`  

