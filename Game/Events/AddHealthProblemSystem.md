# Game.Events.AddHealthProblemSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AddHealthProblemSystem : Game.GameSystemBase
{
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Game.Common.ModificationBarrier4 m_ModificationBarrier;
    private Unity.Entities.EntityQuery m_AddHealthProblemQuery;
    private Unity.Entities.EntityQuery m_HealthcareSettingsQuery;
    private Unity.Entities.EntityQuery m_CitizenQuery;
    private Unity.Entities.EntityArchetype m_JournalDataArchetype;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Events.AddHealthProblemSystem+TypeHandle __TypeHandle;

    public AddHealthProblemSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_ModificationBarrier;
```

- `private Unity.Entities.EntityQuery m_AddHealthProblemQuery`  

```csharp
private Unity.Entities.EntityQuery m_AddHealthProblemQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareSettingsQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenQuery;
```

- `private Unity.Entities.EntityArchetype m_JournalDataArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_JournalDataArchetype;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Events.AddHealthProblemSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Events.AddHealthProblemSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public AddHealthProblemSystem()`  

```csharp
[Preserve]
	public AddHealthProblemSystem()
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier4>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_AddHealthProblemQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Game.Common.Event>() },
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<AddHealthProblem>(),
				ComponentType.ReadOnly<Ignite>(),
				ComponentType.ReadOnly<Destroy>()
			}
		});
		m_HealthcareSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<HealthcareParameterData>());
		m_CitizenQuery = GetEntityQuery(ComponentType.ReadOnly<Citizen>(), ComponentType.ReadOnly<CurrentBuilding>(), ComponentType.Exclude<Deleted>());
		m_JournalDataArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<AddEventJournalData>(), ComponentType.ReadWrite<Game.Common.Event>());
		RequireForUpdate(m_AddHealthProblemQuery);
		RequireForUpdate(m_HealthcareSettingsQuery);
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
		NativeArray<ArchetypeChunk> chunks = m_AddHealthProblemQuery.ToArchetypeChunkArray(Allocator.TempJob);
		NativeQueue<AddHealthProblem> addQueue = new NativeQueue<AddHealthProblem>(Allocator.TempJob);
		NativeQueue<AddHealthProblem>.ParallelWriter addQueue2 = addQueue.AsParallelWriter();
		ComponentTypeHandle<Ignite> typeHandle = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_Ignite_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		ComponentTypeHandle<Destroy> typeHandle2 = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Objects_Destroy_RO_ComponentTypeHandle, ref base.CheckedStateRef);
		for (int i = 0; i < chunks.Length; i++)
		{
			ArchetypeChunk archetypeChunk = chunks[i];
			NativeArray<Ignite> nativeArray = archetypeChunk.GetNativeArray(ref typeHandle);
			NativeArray<Destroy> nativeArray2 = archetypeChunk.GetNativeArray(ref typeHandle2);
			for (int j = 0; j < nativeArray.Length; j++)
			{
				Ignite ignite = nativeArray[j];
				if (base.EntityManager.HasComponent<Building>(ignite.m_Target))
				{
					JobHandle deps;
					FindCitizensInBuildingJob jobData = new FindCitizensInBuildingJob
					{
						m_Event = ignite.m_Event,
						m_Building = ignite.m_Target,
						m_Flags = HealthProblemFlags.InDanger,
						m_DeathProbability = 0f,
						m_RandomSeed = RandomSeed.Next(),
						m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
						m_CurrentBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentTypeHandle, ref base.CheckedStateRef),
						m_HouseholdMemberType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentTypeHandle, ref base.CheckedStateRef),
						m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
						m_TriggerBuffer = m_TriggerSystem.CreateActionBuffer().AsParallelWriter(),
						m_StatisticsEventQueue = m_CityStatisticsSystem.GetStatisticsEventQueue(out deps).AsParallelWriter(),
						m_AddQueue = addQueue2
					};
					base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_CitizenQuery, JobHandle.CombineDependencies(base.Dependency, deps));
					m_CityStatisticsSystem.AddWriter(base.Dependency);
					m_TriggerSystem.AddActionBufferWriter(base.Dependency);
				}
			}
			for (int k = 0; k < nativeArray2.Length; k++)
			{
				Destroy destroy = nativeArray2[k];
				if (base.EntityManager.HasComponent<Building>(destroy.m_Object))
				{
					JobHandle deps2;
					FindCitizensInBuildingJob jobData2 = new FindCitizensInBuildingJob
					{
						m_Event = destroy.m_Event,
						m_Building = destroy.m_Object,
						m_Flags = HealthProblemFlags.Trapped,
						m_DeathProbability = m_HealthcareSettingsQuery.GetSingleton<HealthcareParameterData>().m_BuildingDestoryDeathRate,
						m_RandomSeed = RandomSeed.Next(),
						m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
						m_CurrentBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentTypeHandle, ref base.CheckedStateRef),
						m_HouseholdMemberType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentTypeHandle, ref base.CheckedStateRef),
						m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
						m_TriggerBuffer = m_TriggerSystem.CreateActionBuffer().AsParallelWriter(),
						m_StatisticsEventQueue = m_CityStatisticsSystem.GetStatisticsEventQueue(out deps2).AsParallelWriter(),
						m_AddQueue = addQueue2
					};
					base.Dependency = JobChunkExtensions.ScheduleParallel(jobData2, m_CitizenQuery, JobHandle.CombineDependencies(base.Dependency, deps2));
					m_CityStatisticsSystem.AddWriter(base.Dependency);
					m_TriggerSystem.AddActionBufferWriter(base.Dependency);
				}
			}
		}
		AddHealthProblemJob jobData3 = new AddHealthProblemJob
		{
			m_Chunks = chunks,
			m_AddHealthProblemType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Events_AddHealthProblem_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CurrentTransportData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentTransport_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HealthcareParameterData = m_HealthcareSettingsQuery.GetSingleton<HealthcareParameterData>(),
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer(),
			m_HealthProblemData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RW_ComponentLookup, ref base.CheckedStateRef),
			m_PathOwnerData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathOwner_RW_ComponentLookup, ref base.CheckedStateRef),
			m_TargetData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Target_RW_ComponentLookup, ref base.CheckedStateRef),
			m_TargetElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Events_TargetElement_RW_BufferLookup, ref base.CheckedStateRef),
			m_JournalDataArchetype = m_JournalDataArchetype,
			m_AddQueue = addQueue,
			m_TriggerBuffer = m_TriggerSystem.CreateActionBuffer(),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer()
		};
		base.Dependency = IJobExtensions.Schedule(jobData3, base.Dependency);
		addQueue.Dispose(base.Dependency);
		m_TriggerSystem.AddActionBufferWriter(base.Dependency);
		m_IconCommandSystem.AddCommandBufferWriter(base.Dependency);
		m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Events.AddHealthProblemSystem+FindCitizensInBuildingJob`  
- `Game.Events.AddHealthProblemSystem+AddHealthProblemJob`  
- `Game.Events.AddHealthProblemSystem+TypeHandle`  

