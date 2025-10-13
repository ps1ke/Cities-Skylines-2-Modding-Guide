# Game.Tools.CoveragePreviewSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CoveragePreviewSystem : Game.GameSystemBase
{
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Game.Net.AirwaySystem m_AirwaySystem;
    private Unity.Entities.EntityQuery m_EdgeQuery;
    private Unity.Entities.EntityQuery m_ModifiedQuery;
    private Unity.Entities.EntityQuery m_UpdatedBuildingQuery;
    private Unity.Entities.EntityQuery m_ServiceBuildingQuery;
    private Unity.Entities.EntityQuery m_InfomodeQuery;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Game.Net.CoverageService m_LastService;
    private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
    private System.Collections.Generic.HashSet<Unity.Entities.Entity> m_PendingCoverages;
    private Game.Tools.CoveragePreviewSystem+TypeHandle __TypeHandle;

    public CoveragePreviewSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean GetInfoviewCoverageData(Game.Prefabs.InfoviewCoverageData& coverageData);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnStopRunning();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Game.Net.AirwaySystem m_AirwaySystem`  

```csharp
private Game.Net.AirwaySystem m_AirwaySystem;
```

- `private Unity.Entities.EntityQuery m_EdgeQuery`  

```csharp
private Unity.Entities.EntityQuery m_EdgeQuery;
```

- `private Unity.Entities.EntityQuery m_ModifiedQuery`  

```csharp
private Unity.Entities.EntityQuery m_ModifiedQuery;
```

- `private Unity.Entities.EntityQuery m_UpdatedBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_UpdatedBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_ServiceBuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceBuildingQuery;
```

- `private Unity.Entities.EntityQuery m_InfomodeQuery`  

```csharp
private Unity.Entities.EntityQuery m_InfomodeQuery;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Game.Net.CoverageService m_LastService`  

```csharp
private Game.Net.CoverageService m_LastService;
```

- `private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData`  

```csharp
private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
```

- `private System.Collections.Generic.HashSet<Unity.Entities.Entity> m_PendingCoverages`  

```csharp
private System.Collections.Generic.HashSet<Unity.Entities.Entity> m_PendingCoverages;
```

- `private Game.Tools.CoveragePreviewSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.CoveragePreviewSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CoveragePreviewSystem()`  

```csharp
[Preserve]
	public CoveragePreviewSystem()
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

- `private GetInfoviewCoverageData(Game.Prefabs.InfoviewCoverageData& coverageData) : System.Boolean`  

```csharp
private bool GetInfoviewCoverageData(out InfoviewCoverageData coverageData)
	{
		if (m_InfomodeQuery.IsEmptyIgnoreFilter)
		{
			coverageData = default(InfoviewCoverageData);
			return false;
		}
		NativeArray<ArchetypeChunk> nativeArray = m_InfomodeQuery.ToArchetypeChunkArray(Allocator.TempJob);
		ComponentTypeHandle<InfoviewCoverageData> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_InfoviewCoverageData_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		coverageData = nativeArray[0].GetNativeArray(ref typeHandle)[0];
		nativeArray.Dispose();
		return true;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PathfindQueueSystem = base.World.GetOrCreateSystemManaged<PathfindQueueSystem>();
		m_AirwaySystem = base.World.GetOrCreateSystemManaged<AirwaySystem>();
		m_EdgeQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.Edge>(), ComponentType.ReadWrite<Game.Net.ServiceCoverage>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_ModifiedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Updated>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadWrite<Game.Net.Edge>(),
				ComponentType.ReadWrite<District>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		}, new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Deleted>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadWrite<Game.Net.Edge>(),
				ComponentType.ReadWrite<District>()
			},
			None = new ComponentType[1] { ComponentType.ReadOnly<Temp>() }
		});
		m_UpdatedBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<CoverageServiceType>(), ComponentType.ReadOnly<CoverageElement>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Updated>(), ComponentType.Exclude<Deleted>());
		m_ServiceBuildingQuery = GetEntityQuery(ComponentType.ReadOnly<CoverageServiceType>(), ComponentType.ReadOnly<CoverageElement>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Hidden>(), ComponentType.Exclude<Deleted>());
		m_InfomodeQuery = GetEntityQuery(ComponentType.ReadOnly<InfomodeActive>(), ComponentType.ReadOnly<InfoviewCoverageData>());
		m_EventQuery = GetEntityQuery(ComponentType.ReadOnly<Event>(), ComponentType.ReadOnly<CoverageUpdated>());
		m_LastService = CoverageService.Count;
		m_TargetSeekerData = new PathfindTargetSeekerData(this);
		m_PendingCoverages = new HashSet<Entity>();
		RequireForUpdate(m_InfomodeQuery);
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

- `protected virtual OnStopRunning() : System.Void`  

```csharp
[Preserve]
	protected override void OnStopRunning()
	{
		m_LastService = CoverageService.Count;
		base.OnStopRunning();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!GetInfoviewCoverageData(out var coverageData))
		{
			m_LastService = CoverageService.Count;
		}
		bool flag = m_LastService != coverageData.m_Service;
		bool flag2 = flag || !m_ModifiedQuery.IsEmptyIgnoreFilter;
		m_LastService = coverageData.m_Service;
		bool flag3 = (flag2 ? (!m_ServiceBuildingQuery.IsEmptyIgnoreFilter) : (!m_UpdatedBuildingQuery.IsEmptyIgnoreFilter));
		bool flag4 = !m_EventQuery.IsEmptyIgnoreFilter;
		if (!flag3 && !flag2 && !flag4)
		{
			return;
		}
		NativeArray<ArchetypeChunk> nativeArray = m_ServiceBuildingQuery.ToArchetypeChunkArray(Allocator.TempJob);
		EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
		SharedComponentTypeHandle<CoverageServiceType> sharedComponentTypeHandle = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Net_CoverageServiceType_SharedComponentTypeHandle, ref base.CheckedStateRef);
		BufferTypeHandle<Game.Net.ServiceCoverage> bufferTypeHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ServiceCoverage_RW_BufferTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<Created> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Common_Created_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<Temp> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		JobHandle job = default(JobHandle);
		JobHandle jobHandle = default(JobHandle);
		if (flag2)
		{
			m_PendingCoverages.Clear();
		}
		if (flag3)
		{
			m_TargetSeekerData.Update(this, m_AirwaySystem.GetAirwayData());
			PathfindParameters pathfindParameters = new PathfindParameters
			{
				m_MaxSpeed = 111.111115f,
				m_WalkSpeed = 5.555556f,
				m_Weights = new PathfindWeights(1f, 1f, 1f, 1f),
				m_PathfindFlags = (PathfindFlags.Stable | PathfindFlags.IgnoreFlow),
				m_IgnoredRules = (RuleFlags.HasBlockage | RuleFlags.ForbidCombustionEngines | RuleFlags.ForbidTransitTraffic | RuleFlags.ForbidHeavyTraffic | RuleFlags.ForbidPrivateTraffic | RuleFlags.ForbidSlowTraffic)
			};
			SetupQueueTarget setupQueueTarget = default(SetupQueueTarget);
			ServiceCoverageSystem.SetupPathfindMethods(coverageData.m_Service, ref pathfindParameters, ref setupQueueTarget);
			NativeArray<ArchetypeChunk> nativeArray2 = ((!flag2) ? m_UpdatedBuildingQuery.ToArchetypeChunkArray(Allocator.TempJob) : nativeArray);
			SetupCoverageSearchJob jobData = new SetupCoverageSearchJob
			{
				m_BackSideData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_BackSide_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabCoverageData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CoverageData_RO_ComponentLookup, ref base.CheckedStateRef)
			};
			base.EntityManager.CompleteDependencyBeforeRO<Temp>();
			for (int i = 0; i < nativeArray2.Length; i++)
			{
				ArchetypeChunk archetypeChunk = nativeArray2[i];
				if (archetypeChunk.GetSharedComponent(sharedComponentTypeHandle).m_Service != coverageData.m_Service)
				{
					continue;
				}
				NativeArray<Entity> nativeArray3 = archetypeChunk.GetNativeArray(entityTypeHandle);
				NativeArray<Temp> nativeArray4 = archetypeChunk.GetNativeArray(ref typeHandle2);
				for (int j = 0; j < archetypeChunk.Count; j++)
				{
					Entity entity = nativeArray3[j];
					Temp value;
					Entity entity2 = ((CollectionUtils.TryGet(nativeArray4, j, out value) && value.m_Original != Entity.Null) ? value.m_Original : entity);
					if (base.EntityManager.TryGetBuffer(entity2, isReadOnly: true, out DynamicBuffer<CoverageElement> buffer) && buffer.Length == 0)
					{
						m_PendingCoverages.Add(entity);
					}
				}
			}
			for (int k = 0; k < nativeArray2.Length; k++)
			{
				ArchetypeChunk archetypeChunk2 = nativeArray2[k];
				if (archetypeChunk2.GetSharedComponent(sharedComponentTypeHandle).m_Service != coverageData.m_Service)
				{
					continue;
				}
				NativeArray<Entity> nativeArray5 = archetypeChunk2.GetNativeArray(entityTypeHandle);
				NativeArray<Temp> nativeArray6 = archetypeChunk2.GetNativeArray(ref typeHandle2);
				bool flag5 = archetypeChunk2.Has(ref typeHandle);
				for (int l = 0; l < archetypeChunk2.Count; l++)
				{
					Entity entity3 = nativeArray5[l];
					CollectionUtils.TryGet(nativeArray6, l, out var value2);
					CoverageAction action = new CoverageAction(Allocator.Persistent);
					if (value2.m_Original != Entity.Null && (value2.m_Flags & TempFlags.Modify) == 0)
					{
						jobData.m_Entity = value2.m_Original;
					}
					else
					{
						jobData.m_Entity = entity3;
					}
					jobData.m_TargetSeeker = new PathfindTargetSeeker<PathfindTargetBuffer>(m_TargetSeekerData, pathfindParameters, setupQueueTarget, action.data.m_Sources.AsParallelWriter(), RandomSeed.Next(), isStartTarget: true);
					jobData.m_Action = action;
					JobHandle jobHandle2 = IJobExtensions.Schedule(jobData, base.Dependency);
					job = JobHandle.CombineDependencies(job, jobHandle2);
					m_PathfindQueueSystem.Enqueue(action, entity3, jobHandle2, uint.MaxValue, this, default(PathEventData), nativeArray6.Length != 0);
					if (flag5 && value2.m_Original != Entity.Null)
					{
						jobHandle = IJobExtensions.Schedule(new CopyServiceCoverageJob
						{
							m_Source = value2.m_Original,
							m_Target = entity3,
							m_CoverageElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_CoverageElement_RW_BufferLookup, ref base.CheckedStateRef)
						}, jobHandle);
					}
				}
			}
			if (!flag2)
			{
				nativeArray2.Dispose();
			}
		}
		if (flag4)
		{
			NativeArray<CoverageUpdated> nativeArray7 = m_EventQuery.ToComponentDataArray<CoverageUpdated>(Allocator.Temp);
			for (int m = 0; m < nativeArray7.Length; m++)
			{
				m_PendingCoverages.Remove(nativeArray7[m].m_Owner);
			}
			nativeArray7.Dispose();
		}
		if (m_PendingCoverages.Count != 0)
		{
			if (flag)
			{
				JobHandle job2 = JobChunkExtensions.ScheduleParallel(new InitializeCoverageJob
				{
					m_SourceCoverageIndex = (int)coverageData.m_Service,
					m_TargetCoverageIndex = 8,
					m_ServiceCoverageType = bufferTypeHandle
				}, m_EdgeQuery, base.Dependency);
				job = JobHandle.CombineDependencies(job, jobHandle, job2);
			}
			else
			{
				job = JobHandle.CombineDependencies(job, jobHandle);
			}
			nativeArray.Dispose();
			base.Dependency = job;
			return;
		}
		NativeList<ServiceCoverageSystem.BuildingData> nativeList = new NativeList<ServiceCoverageSystem.BuildingData>(Allocator.TempJob);
		NativeList<ServiceCoverageSystem.CoverageElement> elements = new NativeList<ServiceCoverageSystem.CoverageElement>(Allocator.TempJob);
		ServiceCoverageSystem.PrepareCoverageJob jobData2 = new ServiceCoverageSystem.PrepareCoverageJob
		{
			m_Service = coverageData.m_Service,
			m_BuildingChunks = nativeArray,
			m_CoverageServiceType = sharedComponentTypeHandle,
			m_EntityType = entityTypeHandle,
			m_CoverageElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Pathfind_CoverageElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_BuildingData = nativeList,
			m_Elements = elements
		};
		ServiceCoverageSystem.ClearCoverageJob jobData3 = new ServiceCoverageSystem.ClearCoverageJob
		{
			m_CoverageIndex = 8,
			m_ServiceCoverageType = bufferTypeHandle
		};
		ServiceCoverageSystem.ProcessCoverageJob jobData4 = new ServiceCoverageSystem.ProcessCoverageJob
		{
			m_CoverageIndex = 8,
			m_BuildingData = nativeList,
			m_Elements = elements,
			m_CurveData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Curve_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DensityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_Density_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TempData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ModifiedServiceCoverageData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ModifiedServiceCoverage_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BorderDistrictData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_BorderDistrict_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCoverageData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CoverageData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CoverageElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_CoverageElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_ServiceDistricts = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_ServiceDistrict_RO_BufferLookup, ref base.CheckedStateRef),
			m_Efficiencies = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Efficiency_RO_BufferLookup, ref base.CheckedStateRef),
			m_CoverageData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ServiceCoverage_RW_BufferLookup, ref base.CheckedStateRef)
		};
		ServiceCoverageSystem.ApplyCoverageJob jobData5 = new ServiceCoverageSystem.ApplyCoverageJob
		{
			m_BuildingData = nativeList,
			m_Elements = elements
		};
		JobHandle jobHandle3 = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(base.Dependency, jobHandle));
		JobHandle dependsOn = IJobParallelForDeferExtensions.Schedule(dependsOn: JobHandle.CombineDependencies(jobHandle3, JobChunkExtensions.ScheduleParallel(jobData3, m_EdgeQuery, base.Dependency)), jobData: jobData4, list: nativeList, innerloopBatchCount: 1);
		JobHandle jobHandle4 = IJobExtensions.Schedule(jobData5, dependsOn);
		nativeArray.Dispose(jobHandle3);
		nativeList.Dispose(jobHandle4);
		elements.Dispose(jobHandle4);
		job = JobHandle.CombineDependencies(job, jobHandle4);
		base.Dependency = job;
	}
```


## Nested types

- `Game.Tools.CoveragePreviewSystem+InitializeCoverageJob`  
- `Game.Tools.CoveragePreviewSystem+CopyServiceCoverageJob`  
- `Game.Tools.CoveragePreviewSystem+SetupCoverageSearchJob`  
- `Game.Tools.CoveragePreviewSystem+TypeHandle`  

