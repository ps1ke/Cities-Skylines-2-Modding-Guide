# Game.Triggers.CreateChirpSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CreateChirpSystem : Game.GameSystemBase
{
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Common.ModificationEndBarrier m_ModificationBarrier;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Unity.Entities.EntityQuery m_PrefabQuery;
    private Unity.Entities.EntityQuery m_ChirpQuery;
    private Unity.Entities.EntityQuery m_CitizenQuery;
    private Unity.Collections.NativeQueue<Game.Triggers.ChirpCreationData> m_Queue;
    private Game.Triggers.CreateChirpSystem+TypeHandle __TypeHandle;

    public CreateChirpSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddQueueWriter(Unity.Jobs.JobHandle handle);
    public Unity.Collections.NativeQueue<Game.Triggers.ChirpCreationData> GetQueue(Unity.Jobs.JobHandle& deps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationBarrier;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Unity.Entities.EntityQuery m_PrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrefabQuery;
```

- `private Unity.Entities.EntityQuery m_ChirpQuery`  

```csharp
private Unity.Entities.EntityQuery m_ChirpQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenQuery;
```

- `private Unity.Collections.NativeQueue<Game.Triggers.ChirpCreationData> m_Queue`  

```csharp
private Unity.Collections.NativeQueue<Game.Triggers.ChirpCreationData> m_Queue;
```

- `private Game.Triggers.CreateChirpSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Triggers.CreateChirpSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CreateChirpSystem()`  

```csharp
[Preserve]
	public CreateChirpSystem()
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

- `public AddQueueWriter(Unity.Jobs.JobHandle handle) : System.Void`  

```csharp
public void AddQueueWriter(JobHandle handle)
	{
		m_WriteDependencies = JobHandle.CombineDependencies(m_WriteDependencies, handle);
	}
```

- `public GetQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Triggers.ChirpCreationData>`  

```csharp
public NativeQueue<ChirpCreationData> GetQueue(out JobHandle deps)
	{
		Assert.IsTrue(base.Enabled, "Can not write to queue when system isn't running");
		deps = m_WriteDependencies;
		return m_Queue;
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationEndBarrier>();
		m_PrefabQuery = GetEntityQuery(ComponentType.ReadOnly<ChirpData>());
		m_ChirpQuery = GetEntityQuery(ComponentType.ReadOnly<Chirp>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_CitizenQuery = GetEntityQuery(ComponentType.ReadOnly<Citizen>(), ComponentType.ReadOnly<HouseholdMember>(), ComponentType.Exclude<Deleted>());
		m_Queue = new NativeQueue<ChirpCreationData>(Allocator.Persistent);
		base.Enabled = false;
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
		m_WriteDependencies.Complete();
		m_Queue.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, GameMode mode)
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
		int capacity = m_PrefabQuery.CalculateEntityCount();
		NativeParallelHashMap<Entity, Entity> recentChirps = new NativeParallelHashMap<Entity, Entity>(capacity, Allocator.TempJob);
		JobHandle job = default(JobHandle);
		if (!m_ChirpQuery.IsEmptyIgnoreFilter)
		{
			job = JobChunkExtensions.ScheduleParallel(new CollectRecentChirpsJob
			{
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ChirpType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Triggers_Chirp_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_ChirpDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ChirpData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_RecentChirps = recentChirps.AsParallelWriter(),
				m_SimulationFrame = m_SimulationSystem.frameIndex
			}, m_ChirpQuery, base.Dependency);
		}
		JobHandle outJobHandle;
		NativeList<ArchetypeChunk> randomCitizenChunks = m_CitizenQuery.ToArchetypeChunkListAsync(Allocator.TempJob, out outJobHandle);
		CreateChirpJob jobData = new CreateChirpJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_TriggerChirpData = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_TriggerChirpData_RO_BufferLookup, ref base.CheckedStateRef),
			m_ChirpData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ChirpData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LifepathEventData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LifePathEventData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BrandChirpData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BrandChirpData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_RandomLikeCountData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_RandomLikeCountData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceChirpDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ServiceChirpData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HealthProblems = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdMembers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Households = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HomelessHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HomelessHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_Employees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RO_BufferLookup, ref base.CheckedStateRef),
			m_LifepathEntries = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Triggers_LifePathEntry_RO_BufferLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer(),
			m_Queue = m_Queue,
			m_RecentChirps = recentChirps,
			m_RandomCitizenChunks = randomCitizenChunks,
			m_RandomSeed = RandomSeed.Next(),
			m_UneducatedPopulation = m_CityStatisticsSystem.GetStatisticValue(StatisticType.EducationCount) + m_CityStatisticsSystem.GetStatisticValue(StatisticType.EducationCount, 1),
			m_EducatedPopulation = m_CityStatisticsSystem.GetStatisticValue(StatisticType.EducationCount, 2) + m_CityStatisticsSystem.GetStatisticValue(StatisticType.EducationCount, 3) + m_CityStatisticsSystem.GetStatisticValue(StatisticType.EducationCount, 4),
			m_SimulationFrame = m_SimulationSystem.frameIndex
		};
		base.Dependency = IJobExtensions.Schedule(jobData, JobUtils.CombineDependencies(base.Dependency, m_WriteDependencies, outJobHandle, job));
		recentChirps.Dispose(base.Dependency);
		randomCitizenChunks.Dispose(base.Dependency);
		m_WriteDependencies = base.Dependency;
		m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Triggers.CreateChirpSystem+CollectRecentChirpsJob`  
- `Game.Triggers.CreateChirpSystem+CreateChirpJob`  
- `Game.Triggers.CreateChirpSystem+TypeHandle`  

