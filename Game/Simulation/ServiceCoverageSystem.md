# Game.Simulation.ServiceCoverageSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ServiceCoverageSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Game.Net.AirwaySystem m_AirwaySystem;
    private Unity.Entities.EntityQuery m_EdgeQuery;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
    private Unity.Collections.NativeQueue<Game.Simulation.ServiceCoverageSystem+QueueItem> m_PendingCoverages;
    private Game.Net.CoverageService m_LastCoverageService;
    private Game.Simulation.ServiceCoverageSystem+TypeHandle __TypeHandle;
    public static const System.UInt32 COVERAGE_UPDATE_INTERVAL;

    public ServiceCoverageSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    private System.Boolean EnqueuePendingCoverages(Unity.Jobs.JobHandle& outputDeps);
    private static Game.Net.CoverageService GetFrameService(System.UInt32 frame);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public static System.Void SetupPathfindMethods(Game.Net.CoverageService service, Game.Pathfind.PathfindParameters& pathfindParameters, Game.Pathfind.SetupQueueTarget& setupQueueTarget);
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

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

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData`  

```csharp
private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
```

- `private Unity.Collections.NativeQueue<Game.Simulation.ServiceCoverageSystem+QueueItem> m_PendingCoverages`  

```csharp
private Unity.Collections.NativeQueue<Game.Simulation.ServiceCoverageSystem+QueueItem> m_PendingCoverages;
```

- `private Game.Net.CoverageService m_LastCoverageService`  

```csharp
private Game.Net.CoverageService m_LastCoverageService;
```

- `private Game.Simulation.ServiceCoverageSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.ServiceCoverageSystem+TypeHandle __TypeHandle;
```

- `public static const System.UInt32 COVERAGE_UPDATE_INTERVAL`  

```csharp
public static const System.UInt32 COVERAGE_UPDATE_INTERVAL;
```


## Constructors

- `public ServiceCoverageSystem()`  

```csharp
[Preserve]
	public ServiceCoverageSystem()
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

- `private EnqueuePendingCoverages(Unity.Jobs.JobHandle& outputDeps) : System.Boolean`  

```csharp
private bool EnqueuePendingCoverages(out JobHandle outputDeps)
	{
		outputDeps = default(JobHandle);
		if (m_PendingCoverages.IsEmpty())
		{
			return false;
		}
		int count = m_PendingCoverages.Count;
		int num = 192;
		int num2 = (count + num - 1) / num;
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
		SetupCoverageSearchJob jobData = new SetupCoverageSearchJob
		{
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCoverageData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CoverageData_RO_ComponentLookup, ref base.CheckedStateRef)
		};
		for (int i = 0; i < count; i++)
		{
			QueueItem queueItem = m_PendingCoverages.Peek();
			if (--num2 < 0 && queueItem.m_QueueFrame > m_SimulationSystem.frameIndex)
			{
				break;
			}
			m_PendingCoverages.Dequeue();
			if (base.EntityManager.TryGetSharedComponent<CoverageServiceType>(queueItem.m_Entity, out var component))
			{
				SetupPathfindMethods(component.m_Service, ref pathfindParameters, ref setupQueueTarget);
				CoverageAction action = new CoverageAction(Allocator.Persistent);
				jobData.m_Entity = queueItem.m_Entity;
				jobData.m_TargetSeeker = new PathfindTargetSeeker<PathfindTargetBuffer>(m_TargetSeekerData, pathfindParameters, setupQueueTarget, action.data.m_Sources.AsParallelWriter(), RandomSeed.Next(), isStartTarget: true);
				jobData.m_Action = action;
				JobHandle jobHandle = IJobExtensions.Schedule(jobData, base.Dependency);
				outputDeps = JobHandle.CombineDependencies(outputDeps, jobHandle);
				m_PathfindQueueSystem.Enqueue(action, queueItem.m_Entity, jobHandle, queueItem.m_ResultFrame, this);
			}
		}
		return true;
	}
```

- `private static GetFrameService(System.UInt32 frame) : Game.Net.CoverageService`  

```csharp
private static CoverageService GetFrameService(uint frame)
	{
		return (CoverageService)(frame % 256 * 8 / 256);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_PathfindQueueSystem = base.World.GetOrCreateSystemManaged<PathfindQueueSystem>();
		m_AirwaySystem = base.World.GetOrCreateSystemManaged<AirwaySystem>();
		m_EdgeQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Net.Edge>(), ComponentType.ReadWrite<Game.Net.ServiceCoverage>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_BuildingQuery = GetEntityQuery(ComponentType.ReadOnly<CoverageServiceType>(), ComponentType.ReadOnly<Game.Pathfind.CoverageElement>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_TargetSeekerData = new PathfindTargetSeekerData(this);
		m_PendingCoverages = new NativeQueue<QueueItem>(Allocator.Persistent);
		m_LastCoverageService = CoverageService.Count;
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
		m_PendingCoverages.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		m_PendingCoverages.Clear();
		m_LastCoverageService = CoverageService.Count;
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		CoverageService frameService = GetFrameService(m_SimulationSystem.frameIndex);
		CoverageService frameService2 = GetFrameService(m_SimulationSystem.frameIndex + 1);
		if (frameService == frameService2)
		{
			if (EnqueuePendingCoverages(out var outputDeps))
			{
				base.Dependency = outputDeps;
			}
			return;
		}
		NativeArray<ArchetypeChunk> buildingChunks = m_BuildingQuery.ToArchetypeChunkArray(Allocator.TempJob);
		EntityTypeHandle entityTypeHandle = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef);
		BufferTypeHandle<Game.Net.ServiceCoverage> bufferTypeHandle = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Net_ServiceCoverage_RW_BufferTypeHandle, ref base.CheckedStateRef);
		SharedComponentTypeHandle<CoverageServiceType> sharedComponentTypeHandle = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Net_CoverageServiceType_SharedComponentTypeHandle, ref base.CheckedStateRef);
		uint queueFrame = m_SimulationSystem.frameIndex + 192;
		uint resultFrame = m_SimulationSystem.frameIndex + 256;
		for (int i = 0; i < buildingChunks.Length; i++)
		{
			ArchetypeChunk archetypeChunk = buildingChunks[i];
			if (archetypeChunk.GetSharedComponent(sharedComponentTypeHandle).m_Service == frameService2)
			{
				NativeArray<Entity> nativeArray = archetypeChunk.GetNativeArray(entityTypeHandle);
				for (int j = 0; j < nativeArray.Length; j++)
				{
					m_PendingCoverages.Enqueue(new QueueItem
					{
						m_Entity = nativeArray[j],
						m_QueueFrame = queueFrame,
						m_ResultFrame = resultFrame
					});
				}
			}
		}
		EnqueuePendingCoverages(out var outputDeps2);
		if (m_LastCoverageService != CoverageService.Count)
		{
			NativeList<BuildingData> nativeList = new NativeList<BuildingData>(Allocator.TempJob);
			NativeList<CoverageElement> elements = new NativeList<CoverageElement>(Allocator.TempJob);
			PrepareCoverageJob jobData = new PrepareCoverageJob
			{
				m_Service = frameService,
				m_BuildingChunks = buildingChunks,
				m_CoverageServiceType = sharedComponentTypeHandle,
				m_EntityType = entityTypeHandle,
				m_CoverageElementType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Pathfind_CoverageElement_RO_BufferTypeHandle, ref base.CheckedStateRef),
				m_BuildingData = nativeList,
				m_Elements = elements
			};
			ClearCoverageJob jobData2 = new ClearCoverageJob
			{
				m_CoverageIndex = (int)frameService,
				m_ServiceCoverageType = bufferTypeHandle
			};
			ProcessCoverageJob jobData3 = new ProcessCoverageJob
			{
				m_CoverageIndex = (int)frameService,
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
			ApplyCoverageJob jobData4 = new ApplyCoverageJob
			{
				m_BuildingData = nativeList,
				m_Elements = elements
			};
			JobHandle jobHandle = IJobExtensions.Schedule(jobData, base.Dependency);
			JobHandle dependsOn = IJobParallelForDeferExtensions.Schedule(dependsOn: JobHandle.CombineDependencies(jobHandle, JobChunkExtensions.ScheduleParallel(jobData2, m_EdgeQuery, base.Dependency)), jobData: jobData3, list: nativeList, innerloopBatchCount: 1);
			JobHandle jobHandle2 = IJobExtensions.Schedule(jobData4, dependsOn);
			buildingChunks.Dispose(jobHandle);
			nativeList.Dispose(jobHandle2);
			elements.Dispose(jobHandle2);
			outputDeps2 = JobHandle.CombineDependencies(outputDeps2, jobHandle2);
		}
		else
		{
			buildingChunks.Dispose();
		}
		m_LastCoverageService = frameService2;
		base.Dependency = outputDeps2;
	}
```

- `public static SetupPathfindMethods(Game.Net.CoverageService service, Game.Pathfind.PathfindParameters& pathfindParameters, Game.Pathfind.SetupQueueTarget& setupQueueTarget) : System.Void`  

```csharp
public static void SetupPathfindMethods(CoverageService service, ref PathfindParameters pathfindParameters, ref SetupQueueTarget setupQueueTarget)
	{
		switch (service)
		{
		case CoverageService.PostService:
		case CoverageService.Education:
		case CoverageService.EmergencyShelter:
		case CoverageService.Welfare:
			pathfindParameters.m_Methods = PathMethod.Pedestrian;
			setupQueueTarget.m_Methods = PathMethod.Pedestrian;
			setupQueueTarget.m_RoadTypes = RoadTypes.None;
			break;
		case CoverageService.Park:
			pathfindParameters.m_Methods = PathMethod.Pedestrian;
			setupQueueTarget.m_Methods = PathMethod.Pedestrian;
			setupQueueTarget.m_RoadTypes = RoadTypes.None;
			setupQueueTarget.m_ActivityMask.m_Mask |= new ActivityMask(ActivityType.BenchSitting).m_Mask;
			setupQueueTarget.m_ActivityMask.m_Mask |= new ActivityMask(ActivityType.PullUps).m_Mask;
			setupQueueTarget.m_ActivityMask.m_Mask |= new ActivityMask(ActivityType.Standing).m_Mask;
			setupQueueTarget.m_ActivityMask.m_Mask |= new ActivityMask(ActivityType.GroundLaying).m_Mask;
			setupQueueTarget.m_ActivityMask.m_Mask |= new ActivityMask(ActivityType.GroundSitting).m_Mask;
			setupQueueTarget.m_ActivityMask.m_Mask |= new ActivityMask(ActivityType.PushUps).m_Mask;
			setupQueueTarget.m_ActivityMask.m_Mask |= new ActivityMask(ActivityType.SitUps).m_Mask;
			setupQueueTarget.m_ActivityMask.m_Mask |= new ActivityMask(ActivityType.JumpingJacks).m_Mask;
			setupQueueTarget.m_ActivityMask.m_Mask |= new ActivityMask(ActivityType.JumpingLunges).m_Mask;
			setupQueueTarget.m_ActivityMask.m_Mask |= new ActivityMask(ActivityType.Squats).m_Mask;
			setupQueueTarget.m_ActivityMask.m_Mask |= new ActivityMask(ActivityType.Yoga).m_Mask;
			break;
		default:
			pathfindParameters.m_Methods = PathMethod.Road;
			setupQueueTarget.m_Methods = PathMethod.Road;
			setupQueueTarget.m_RoadTypes = RoadTypes.Car;
			break;
		}
	}
```


## Nested types

- `Game.Simulation.ServiceCoverageSystem+ClearCoverageJob`  
- `Game.Simulation.ServiceCoverageSystem+CoverageElement`  
- `Game.Simulation.ServiceCoverageSystem+QueueItem`  
- `Game.Simulation.ServiceCoverageSystem+BuildingData`  
- `Game.Simulation.ServiceCoverageSystem+PrepareCoverageJob`  
- `Game.Simulation.ServiceCoverageSystem+ProcessCoverageJob`  
- `Game.Simulation.ServiceCoverageSystem+BuildingDataComparer`  
- `Game.Simulation.ServiceCoverageSystem+ApplyCoverageJob`  
- `Game.Simulation.ServiceCoverageSystem+SetupCoverageSearchJob`  
- `Game.Simulation.ServiceCoverageSystem+TypeHandle`  

