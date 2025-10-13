# Game.Triggers.LifePathEventSystem

**Assembly:** `Game`  
**Namespace:** `Game.Triggers`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class LifePathEventSystem : Game.GameSystemBase
{
    private System.Boolean <m_DebugLifePathChirps>k__BackingField;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Common.ModificationEndBarrier m_ModificationBarrier;
    private Game.Triggers.CreateChirpSystem m_CreateChirpSystem;
    private Unity.Entities.EntityQuery m_FollowedQuery;
    private Unity.Entities.EntityQuery m_DeletedFollowedQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Unity.Entities.EntityArchetype m_EventArchetype;
    private Unity.Collections.NativeQueue<Game.Triggers.LifePathEventCreationData> m_Queue;
    private Unity.Jobs.JobHandle m_WriteDependencies;
    private Game.Triggers.LifePathEventSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kMaxFollowed;

    public System.Boolean m_DebugLifePathChirps { get; set; }

    public LifePathEventSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddQueueWriter(Unity.Jobs.JobHandle handle);
    public System.Boolean FollowCitizen(Unity.Entities.Entity citizen);
    public Unity.Collections.NativeQueue<Game.Triggers.LifePathEventCreationData> GetQueue(Unity.Jobs.JobHandle& deps);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public System.Boolean UnfollowCitizen(Unity.Entities.Entity citizen);
}
```


## Fields

- `private System.Boolean <m_DebugLifePathChirps>k__BackingField`  

```csharp
private System.Boolean <m_DebugLifePathChirps>k__BackingField;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Common.ModificationEndBarrier m_ModificationBarrier`  

```csharp
private Game.Common.ModificationEndBarrier m_ModificationBarrier;
```

- `private Game.Triggers.CreateChirpSystem m_CreateChirpSystem`  

```csharp
private Game.Triggers.CreateChirpSystem m_CreateChirpSystem;
```

- `private Unity.Entities.EntityQuery m_FollowedQuery`  

```csharp
private Unity.Entities.EntityQuery m_FollowedQuery;
```

- `private Unity.Entities.EntityQuery m_DeletedFollowedQuery`  

```csharp
private Unity.Entities.EntityQuery m_DeletedFollowedQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Unity.Entities.EntityArchetype m_EventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_EventArchetype;
```

- `private Unity.Collections.NativeQueue<Game.Triggers.LifePathEventCreationData> m_Queue`  

```csharp
private Unity.Collections.NativeQueue<Game.Triggers.LifePathEventCreationData> m_Queue;
```

- `private Unity.Jobs.JobHandle m_WriteDependencies`  

```csharp
private Unity.Jobs.JobHandle m_WriteDependencies;
```

- `private Game.Triggers.LifePathEventSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Triggers.LifePathEventSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kMaxFollowed`  

```csharp
public static readonly System.Int32 kMaxFollowed;
```


## Properties

- `public System.Boolean m_DebugLifePathChirps { get; set }`  

```csharp
public System.Boolean m_DebugLifePathChirps { get; set; }
```


## Constructors

- `public LifePathEventSystem()`  

```csharp
[Preserve]
	public LifePathEventSystem()
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

- `public FollowCitizen(Unity.Entities.Entity citizen) : System.Boolean`  

```csharp
public bool FollowCitizen(Entity citizen)
	{
		if (m_FollowedQuery.CalculateEntityCount() < kMaxFollowed)
		{
			Citizen component;
			bool startedFollowingAsChild = base.EntityManager.TryGetComponent<Citizen>(citizen, out component) && component.GetAge() == CitizenAge.Child;
			base.EntityManager.AddComponentData(citizen, new Followed
			{
				m_Priority = m_SimulationSystem.frameIndex,
				m_StartedFollowingAsChild = startedFollowingAsChild
			});
			base.EntityManager.AddBuffer<LifePathEntry>(citizen);
			base.EntityManager.AddComponent<Updated>(citizen);
			return true;
		}
		return false;
	}
```

- `public GetQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Triggers.LifePathEventCreationData>`  

```csharp
public NativeQueue<LifePathEventCreationData> GetQueue(out JobHandle deps)
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
		m_ModificationBarrier = base.World.GetOrCreateSystemManaged<ModificationEndBarrier>();
		m_CreateChirpSystem = base.World.GetOrCreateSystemManaged<CreateChirpSystem>();
		m_FollowedQuery = GetEntityQuery(ComponentType.ReadOnly<Followed>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_DeletedFollowedQuery = GetEntityQuery(ComponentType.ReadOnly<Followed>(), ComponentType.ReadOnly<Deleted>(), ComponentType.Exclude<Temp>());
		m_TimeDataQuery = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		m_EventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadOnly<LifePathEvent>());
		m_Queue = new NativeQueue<LifePathEventCreationData>(Allocator.Persistent);
		RequireForUpdate(m_TimeDataQuery);
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
		CleanupLifePathEntriesJob jobData = new CleanupLifePathEntriesJob
		{
			m_EntryType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Triggers_LifePathEntry_RO_BufferTypeHandle, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_DeletedFollowedQuery, base.Dependency);
		m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
		JobHandle deps;
		CreateLifePathEventJob jobData2 = new CreateLifePathEventJob
		{
			m_LifePathEventDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_LifePathEventData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LifePathEntries = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Triggers_LifePathEntry_RO_BufferLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_ModificationBarrier.CreateCommandBuffer(),
			m_EventArchetype = m_EventArchetype,
			m_Queue = m_Queue,
			m_ChirpQueue = m_CreateChirpSystem.GetQueue(out deps),
			m_TimeData = m_TimeDataQuery.GetSingleton<TimeData>(),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_DebugLifePathChirps = m_DebugLifePathChirps
		};
		base.Dependency = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(base.Dependency, m_WriteDependencies, deps));
		m_CreateChirpSystem.AddQueueWriter(base.Dependency);
		m_ModificationBarrier.AddJobHandleForProducer(base.Dependency);
		m_WriteDependencies = base.Dependency;
	}
```

- `public UnfollowCitizen(Unity.Entities.Entity citizen) : System.Boolean`  

```csharp
public bool UnfollowCitizen(Entity citizen)
	{
		if (base.EntityManager.HasComponent<Followed>(citizen))
		{
			base.EntityManager.RemoveComponent<Followed>(citizen);
			if (base.EntityManager.TryGetBuffer(citizen, isReadOnly: true, out DynamicBuffer<LifePathEntry> buffer))
			{
				foreach (LifePathEntry item in buffer)
				{
					base.EntityManager.AddComponent<Deleted>(item.m_Entity);
				}
			}
			base.EntityManager.RemoveComponent<LifePathEntry>(citizen);
			base.EntityManager.AddComponent<Updated>(citizen);
			return true;
		}
		return false;
	}
```


## Nested types

- `Game.Triggers.LifePathEventSystem+CreateLifePathEventJob`  
- `Game.Triggers.LifePathEventSystem+CleanupLifePathEntriesJob`  
- `Game.Triggers.LifePathEventSystem+TypeHandle`  

