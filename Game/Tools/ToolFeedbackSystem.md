# Game.Tools.ToolFeedbackSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.Serialization.IPostDeserialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ToolFeedbackSystem : Game.GameSystemBase, Game.Serialization.IPostDeserialize
{
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
    private Game.Net.AirwaySystem m_AirwaySystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
    private System.Collections.Generic.List<Unity.Entities.Entity> m_FeedbackContainers;
    private System.Collections.Generic.List<Unity.Entities.Entity> m_PendingContainers;
    private Unity.Collections.NativeParallelHashMap<Game.Tools.ToolFeedbackSystem+RecentKey, Game.Tools.ToolFeedbackSystem+RecentValue> m_RecentMap;
    private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
    private Unity.Entities.EntityQuery m_ConfigurationQuery;
    private Unity.Entities.EntityQuery m_AppliedQuery;
    private Unity.Entities.EntityQuery m_TargetQuery;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Jobs.JobHandle m_RecentDeps;
    private Game.Tools.ToolFeedbackSystem+TypeHandle __TypeHandle;
    private static const System.Single INFINITE_RANGE;

    public ToolFeedbackSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public System.Void PostDeserialize(Colossal.Serialization.Entities.Context context);
    private System.Void ProcessModifications();
    private System.Void UpdatePending();
}
```


## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  

```csharp
private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem;
```

- `private Game.Net.AirwaySystem m_AirwaySystem`  

```csharp
private Game.Net.AirwaySystem m_AirwaySystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  

```csharp
private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
```

- `private System.Collections.Generic.List<Unity.Entities.Entity> m_FeedbackContainers`  

```csharp
private System.Collections.Generic.List<Unity.Entities.Entity> m_FeedbackContainers;
```

- `private System.Collections.Generic.List<Unity.Entities.Entity> m_PendingContainers`  

```csharp
private System.Collections.Generic.List<Unity.Entities.Entity> m_PendingContainers;
```

- `private Unity.Collections.NativeParallelHashMap<Game.Tools.ToolFeedbackSystem+RecentKey, Game.Tools.ToolFeedbackSystem+RecentValue> m_RecentMap`  

```csharp
private Unity.Collections.NativeParallelHashMap<Game.Tools.ToolFeedbackSystem+RecentKey, Game.Tools.ToolFeedbackSystem+RecentValue> m_RecentMap;
```

- `private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData`  

```csharp
private Game.Pathfind.PathfindTargetSeekerData m_TargetSeekerData;
```

- `private Unity.Entities.EntityQuery m_ConfigurationQuery`  

```csharp
private Unity.Entities.EntityQuery m_ConfigurationQuery;
```

- `private Unity.Entities.EntityQuery m_AppliedQuery`  

```csharp
private Unity.Entities.EntityQuery m_AppliedQuery;
```

- `private Unity.Entities.EntityQuery m_TargetQuery`  

```csharp
private Unity.Entities.EntityQuery m_TargetQuery;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Jobs.JobHandle m_RecentDeps`  

```csharp
private Unity.Jobs.JobHandle m_RecentDeps;
```

- `private Game.Tools.ToolFeedbackSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Tools.ToolFeedbackSystem+TypeHandle __TypeHandle;
```

- `private static const System.Single INFINITE_RANGE`  

```csharp
private static const System.Single INFINITE_RANGE;
```


## Constructors

- `public ToolFeedbackSystem()`  

```csharp
[Preserve]
	public ToolFeedbackSystem()
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
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_PathfindQueueSystem = base.World.GetOrCreateSystemManaged<PathfindQueueSystem>();
		m_AirwaySystem = base.World.GetOrCreateSystemManaged<AirwaySystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TelecomCoverageSystem = base.World.GetOrCreateSystemManaged<TelecomCoverageSystem>();
		m_FeedbackContainers = new List<Entity>();
		m_PendingContainers = new List<Entity>();
		m_RecentMap = new NativeParallelHashMap<RecentKey, RecentValue>(1000, Allocator.Persistent);
		m_TargetSeekerData = new PathfindTargetSeekerData(this);
		m_ConfigurationQuery = GetEntityQuery(ComponentType.ReadOnly<FeedbackConfigurationData>());
		m_AppliedQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Applied>(),
				ComponentType.ReadOnly<Created>(),
				ComponentType.ReadOnly<Game.Objects.Object>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Game.Buildings.ServiceUpgrade>(),
				ComponentType.ReadOnly<Game.Routes.TransportStop>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Game.Objects.Object>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<Game.Buildings.ServiceUpgrade>(),
				ComponentType.ReadOnly<Game.Routes.TransportStop>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Abandoned>(),
				ComponentType.ReadOnly<Condemned>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_TargetQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.Exclude<Game.Buildings.ServiceUpgrade>(), ComponentType.Exclude<Abandoned>(), ComponentType.Exclude<Condemned>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Updated>(), ComponentType.Exclude<Temp>());
		m_EventQuery = GetEntityQuery(ComponentType.ReadOnly<Event>(), ComponentType.ReadOnly<CoverageUpdated>());
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
		m_RecentDeps.Complete();
		m_RecentMap.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		base.Enabled = mode.IsGame();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_AppliedQuery.IsEmptyIgnoreFilter && !m_ConfigurationQuery.IsEmptyIgnoreFilter)
		{
			ProcessModifications();
		}
		if (m_PendingContainers.Count != 0 && !m_EventQuery.IsEmptyIgnoreFilter)
		{
			UpdatePending();
		}
	}
```

- `public PostDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PostDeserialize(Context context)
	{
		m_RecentDeps.Complete();
		m_RecentMap.Clear();
		for (int i = 0; i < m_PendingContainers.Count; i++)
		{
			Entity item = m_PendingContainers[i];
			m_PendingContainers.RemoveAtSwapBack(i--);
			m_FeedbackContainers.Add(item);
		}
	}
```

- `private ProcessModifications() : System.Void`  

```csharp
private void ProcessModifications()
	{
		NativeArray<Entity> nativeArray = m_AppliedQuery.ToEntityArray(Allocator.TempJob);
		PathfindParameters pathfindParameters = new PathfindParameters
		{
			m_MaxSpeed = 111.111115f,
			m_WalkSpeed = 5.555556f,
			m_Weights = new PathfindWeights(1f, 1f, 1f, 1f),
			m_PathfindFlags = (PathfindFlags.Stable | PathfindFlags.IgnoreFlow),
			m_IgnoredRules = (RuleFlags.HasBlockage | RuleFlags.ForbidCombustionEngines | RuleFlags.ForbidTransitTraffic | RuleFlags.ForbidHeavyTraffic | RuleFlags.ForbidPrivateTraffic | RuleFlags.ForbidSlowTraffic)
		};
		SetupQueueTarget setupQueueTarget = default(SetupQueueTarget);
		while (m_FeedbackContainers.Count < nativeArray.Length)
		{
			m_FeedbackContainers.Add(base.EntityManager.CreateEntity(ComponentType.ReadWrite<Feedback>(), ComponentType.ReadWrite<ExtraFeedback>(), ComponentType.ReadWrite<CoverageElement>()));
		}
		m_TargetSeekerData.Update(this, m_AirwaySystem.GetAirwayData());
		SetupCoverageSearchJob jobData = new SetupCoverageSearchJob
		{
			m_BackSideData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_BackSide_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCoverageData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CoverageData_RO_ComponentLookup, ref base.CheckedStateRef)
		};
		FeedbackConfigurationData feedbackConfigurationData = default(FeedbackConfigurationData);
		IconCommandBuffer iconCommandBuffer = default(IconCommandBuffer);
		JobHandle jobHandle = default(JobHandle);
		bool flag = false;
		for (int i = 0; i < nativeArray.Length; i++)
		{
			Entity entity = nativeArray[i];
			Entity entity2 = entity;
			Owner component;
			while (base.EntityManager.TryGetComponent<Owner>(entity2, out component))
			{
				entity2 = component.m_Owner;
			}
			bool flag2 = base.EntityManager.HasComponent<Deleted>(entity);
			if (entity2 != entity)
			{
				if (flag2)
				{
					if (base.EntityManager.HasComponent<Deleted>(entity2))
					{
						continue;
					}
				}
				else if (base.EntityManager.HasComponent<Applied>(entity2))
				{
					continue;
				}
			}
			Transform componentData = base.EntityManager.GetComponentData<Transform>(entity2);
			PrefabRef componentData2 = base.EntityManager.GetComponentData<PrefabRef>(entity);
			PrefabRef componentData3 = base.EntityManager.GetComponentData<PrefabRef>(entity2);
			if (base.EntityManager.HasComponent<SpawnableBuildingData>(componentData2.m_Prefab))
			{
				if (flag2)
				{
					if (feedbackConfigurationData.m_HappyFaceNotification == Entity.Null)
					{
						feedbackConfigurationData = m_ConfigurationQuery.GetSingleton<FeedbackConfigurationData>();
						iconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer();
					}
					iconCommandBuffer.Add(entity, feedbackConfigurationData.m_SadFaceNotification, IconPriority.Info, IconClusterLayer.Transaction);
				}
				continue;
			}
			Entity entity3 = m_FeedbackContainers[m_FeedbackContainers.Count - 1];
			m_FeedbackContainers.RemoveAt(m_FeedbackContainers.Count - 1);
			m_PendingContainers.Add(entity3);
			base.EntityManager.SetComponentData(entity3, new Feedback
			{
				m_Position = componentData.m_Position,
				m_MainEntity = entity2,
				m_Prefab = componentData2.m_Prefab,
				m_MainPrefab = componentData3.m_Prefab,
				m_IsDeleted = flag2
			});
			DynamicBuffer<ExtraFeedback> buffer = base.EntityManager.GetBuffer<ExtraFeedback>(entity3);
			buffer.Clear();
			if (base.EntityManager.TryGetBuffer(entity2, isReadOnly: true, out DynamicBuffer<InstalledUpgrade> buffer2))
			{
				for (int j = 0; j < buffer2.Length; j++)
				{
					InstalledUpgrade installedUpgrade = buffer2[j];
					if (!BuildingUtils.CheckOption(installedUpgrade, BuildingOption.Inactive))
					{
						buffer.Add(new ExtraFeedback
						{
							m_Prefab = base.EntityManager.GetComponentData<PrefabRef>(installedUpgrade.m_Upgrade).m_Prefab
						});
					}
				}
			}
			base.EntityManager.GetBuffer<CoverageElement>(entity3).Clear();
			if (!base.EntityManager.TryGetSharedComponent<CoverageServiceType>(entity2, out var component2))
			{
				component2.m_Service = CoverageService.Count;
			}
			Game.Simulation.ServiceCoverageSystem.SetupPathfindMethods(component2.m_Service, ref pathfindParameters, ref setupQueueTarget);
			CoverageAction action = new CoverageAction(Allocator.Persistent);
			jobData.m_Entity = entity2;
			jobData.m_TargetSeeker = new PathfindTargetSeeker<PathfindTargetBuffer>(m_TargetSeekerData, pathfindParameters, setupQueueTarget, action.data.m_Sources.AsParallelWriter(), RandomSeed.Next(), isStartTarget: true);
			jobData.m_Action = action;
			JobHandle jobHandle2 = IJobExtensions.Schedule(jobData, base.Dependency);
			jobHandle = JobHandle.CombineDependencies(jobHandle, jobHandle2);
			m_PathfindQueueSystem.Enqueue(action, entity3, jobHandle2, uint.MaxValue, this, default(PathEventData), highPriority: true);
			flag = true;
		}
		nativeArray.Dispose();
		if (flag)
		{
			base.Dependency = jobHandle;
		}
	}
```

- `private UpdatePending() : System.Void`  

```csharp
private void UpdatePending()
	{
		NativeArray<CoverageUpdated> nativeArray = m_EventQuery.ToComponentDataArray<CoverageUpdated>(Allocator.TempJob);
		Entity singletonEntity = m_ConfigurationQuery.GetSingletonEntity();
		TargetCheckJob jobData = new TargetCheckJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TransformType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_GarbageProducerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_GarbageProducer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ElectricityConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_WaterConsumerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_MailProducerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_MailProducer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CrimeProducerType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_CrimeProducer_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabCoverageData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CoverageData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabGarbageFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_GarbageFacilityData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabHospitalData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_HospitalData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabDeathcareFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_DeathcareFacilityData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPowerPlantData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PowerPlantData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabWindPoweredData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WindPoweredData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSolarPoweredData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SolarPoweredData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTransformerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransformerData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabWaterPumpingStationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WaterPumpingStationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSewageOutletData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SewageOutletData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabWastewaterTreatmentPlantData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WastewaterTreatmentPlantData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTransportDepotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportDepotData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTransportStationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportStationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPublicTransportStationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PublicTransportStationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabCargoTransportStationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CargoTransportStationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTransportStopData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TransportStopData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPostFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PostFacilityData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabTelecomFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_TelecomFacilityData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabSchoolData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SchoolData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabParkingFacilityData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ParkingFacilityData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabMaintenanceDepotData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_MaintenanceDepotData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabFireStationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_FireStationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPoliceStationData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PoliceStationData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPrisonData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrisonData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabPollutionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PollutionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabAttractionData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AttractionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceCoverages = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ServiceCoverage_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabLocalModifierDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_LocalModifierData_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabCityModifierDatas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_CityModifierData_RO_BufferLookup, ref base.CheckedStateRef),
			m_FeedbackConfigurationData = base.EntityManager.GetComponentData<FeedbackConfigurationData>(singletonEntity),
			m_FeedbackLocalEffectFactors = base.EntityManager.GetBuffer<FeedbackLocalEffectFactor>(singletonEntity, isReadOnly: true),
			m_FeedbackCityEffectFactors = base.EntityManager.GetBuffer<FeedbackCityEffectFactor>(singletonEntity, isReadOnly: true),
			m_RecentMap = m_RecentMap
		};
		NativeQueue<RecentUpdate> recentUpdates = default(NativeQueue<RecentUpdate>);
		JobHandle jobHandle = default(JobHandle);
		bool flag = false;
		for (int i = 0; i < m_PendingContainers.Count; i++)
		{
			Entity entity = m_PendingContainers[i];
			DynamicBuffer<CoverageElement> buffer = base.EntityManager.GetBuffer<CoverageElement>(entity, isReadOnly: true);
			if (buffer.Length != 0)
			{
				m_PendingContainers.RemoveAtSwapBack(i--);
				m_FeedbackContainers.Add(entity);
				NativeParallelHashMap<Entity, float2> coverageMap = new NativeParallelHashMap<Entity, float2>(buffer.Length, Allocator.TempJob);
				FillCoverageMapJob jobData2 = new FillCoverageMapJob
				{
					m_CoverageElements = buffer.AsNativeArray(),
					m_CoverageMap = coverageMap.AsParallelWriter()
				};
				jobData.m_FeedbackData = base.EntityManager.GetComponentData<Feedback>(entity);
				jobData.m_ExtraFeedbacks = base.EntityManager.GetBuffer<ExtraFeedback>(entity, isReadOnly: true);
				jobData.m_RandomSeed = RandomSeed.Next();
				jobData.m_CoverageMap = coverageMap;
				if (!flag)
				{
					recentUpdates = new NativeQueue<RecentUpdate>(Allocator.TempJob);
					jobData.m_TelecomCoverageData = m_TelecomCoverageSystem.GetData(readOnly: true, out var dependencies);
					jobData.m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer();
					jobData.m_RecentUpdates = recentUpdates.AsParallelWriter();
					jobHandle = JobHandle.CombineDependencies(base.Dependency, m_RecentDeps, dependencies);
				}
				JobHandle job = IJobParallelForExtensions.Schedule(jobData2, buffer.Length, 4);
				JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(jobData, m_TargetQuery, JobHandle.CombineDependencies(jobHandle, job));
				coverageMap.Dispose(jobHandle2);
				jobHandle = jobHandle2;
				flag = true;
			}
		}
		for (int j = 0; j < nativeArray.Length; j++)
		{
			CoverageUpdated coverageUpdated = nativeArray[j];
			for (int k = 0; k < m_PendingContainers.Count; k++)
			{
				Entity entity2 = m_PendingContainers[k];
				if (entity2 == coverageUpdated.m_Owner)
				{
					m_PendingContainers.RemoveAtSwapBack(k--);
					m_FeedbackContainers.Add(entity2);
					jobData.m_FeedbackData = base.EntityManager.GetComponentData<Feedback>(entity2);
					jobData.m_ExtraFeedbacks = base.EntityManager.GetBuffer<ExtraFeedback>(entity2, isReadOnly: true);
					jobData.m_RandomSeed = RandomSeed.Next();
					jobData.m_CoverageMap = default(NativeParallelHashMap<Entity, float2>);
					if (!flag)
					{
						recentUpdates = new NativeQueue<RecentUpdate>(Allocator.TempJob);
						jobData.m_TelecomCoverageData = m_TelecomCoverageSystem.GetData(readOnly: true, out var dependencies2);
						jobData.m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer();
						jobData.m_RecentUpdates = recentUpdates.AsParallelWriter();
						jobHandle = JobHandle.CombineDependencies(base.Dependency, m_RecentDeps, dependencies2);
					}
					jobHandle = JobChunkExtensions.ScheduleParallel(jobData, m_TargetQuery, jobHandle);
					flag = true;
					break;
				}
			}
		}
		nativeArray.Dispose();
		if (flag)
		{
			m_IconCommandSystem.AddCommandBufferWriter(jobHandle);
			m_TelecomCoverageSystem.AddReader(jobHandle);
			base.Dependency = jobHandle;
			UpdateRecentMapJob jobData3 = new UpdateRecentMapJob
			{
				m_RecentMap = m_RecentMap,
				m_RecentUpdates = recentUpdates,
				m_SimulationFrame = m_SimulationSystem.frameIndex
			};
			m_RecentDeps = IJobExtensions.Schedule(jobData3, jobHandle);
			recentUpdates.Dispose(m_RecentDeps);
		}
	}
```


## Nested types

- `Game.Tools.ToolFeedbackSystem+RecentKey`  
- `Game.Tools.ToolFeedbackSystem+RecentValue`  
- `Game.Tools.ToolFeedbackSystem+RecentUpdate`  
- `Game.Tools.ToolFeedbackSystem+FeedbackType`  
- `Game.Tools.ToolFeedbackSystem+SetupCoverageSearchJob`  
- `Game.Tools.ToolFeedbackSystem+FillCoverageMapJob`  
- `Game.Tools.ToolFeedbackSystem+TargetCheckJob`  
- `Game.Tools.ToolFeedbackSystem+UpdateRecentMapJob`  
- `Game.Tools.ToolFeedbackSystem+TypeHandle`  

