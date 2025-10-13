# Game.Simulation.DivorceSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class DivorceSystem : Game.GameSystemBase
{
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Colossal.Collections.NativeValue<System.Int32> m_DebugDivorce;
    private Colossal.NativeCounter m_DebugDivorceCount;
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Entities.EntityQuery m_HouseholdPrefabQuery;
    private Unity.Entities.EntityQuery m_CitizenParametersQuery;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.DivorceSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public DivorceSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Colossal.Collections.NativeValue<System.Int32> m_DebugDivorce`  

```csharp
private Colossal.Collections.NativeValue<System.Int32> m_DebugDivorce;
```

- `private Colossal.NativeCounter m_DebugDivorceCount`  

```csharp
private Colossal.NativeCounter m_DebugDivorceCount;
```

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Entities.EntityQuery m_HouseholdPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenParametersQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenParametersQuery;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.DivorceSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.DivorceSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public DivorceSystem()`  

```csharp
[Preserve]
	public DivorceSystem()
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

- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  

```csharp
public override int GetUpdateInterval(SystemUpdatePhase phase)
	{
		return 262144 / (kUpdatesPerDay * 16);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_DebugDivorce = new NativeValue<int>(Allocator.Persistent);
		m_DebugDivorceCount = new NativeCounter(Allocator.Persistent);
		m_HouseholdQuery = GetEntityQuery(ComponentType.ReadOnly<Household>(), ComponentType.ReadOnly<HouseholdCitizen>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.Exclude<TouristHousehold>(), ComponentType.Exclude<CommuterHousehold>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_HouseholdPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<ArchetypeData>(), ComponentType.ReadOnly<HouseholdData>(), ComponentType.ReadOnly<DynamicHousehold>());
		m_CitizenParametersQuery = GetEntityQuery(ComponentType.ReadOnly<CitizenParametersData>());
		RequireForUpdate(m_HouseholdPrefabQuery);
		RequireForUpdate(m_CitizenParametersQuery);
		RequireForUpdate(m_HouseholdQuery);
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
		m_DebugDivorce.Dispose();
		m_DebugDivorceCount.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16);
		JobHandle outJobHandle;
		CheckDivorceJob jobData = new CheckDivorceJob
		{
			m_DebugDivorceCount = m_DebugDivorceCount.ToConcurrent(),
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_HouseholdCitizenType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = InternalCompilerInterface.GetSharedComponentTypeHandle(ref __TypeHandle.__Game_Simulation_UpdateFrame_SharedComponentTypeHandle, ref base.CheckedStateRef),
			m_HouseholdType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Household_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResourceType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_HouseholdMembers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HouseholdMember_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ArchetypeDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ArchetypeData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdPrefabs = m_HouseholdPrefabQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_RandomSeed = RandomSeed.Next(),
			m_UpdateFrameIndex = updateFrame,
			m_CitizenParametersData = m_CitizenParametersQuery.GetSingleton<CitizenParametersData>(),
			m_TriggerBuffer = m_TriggerSystem.CreateActionBuffer().AsParallelWriter(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_HouseholdQuery, JobHandle.CombineDependencies(outJobHandle, base.Dependency));
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		m_TriggerSystem.AddActionBufferWriter(base.Dependency);
		SumDivorceJob jobData2 = new SumDivorceJob
		{
			m_DebugDivorce = m_DebugDivorce,
			m_DebugDivorceCount = m_DebugDivorceCount
		};
		base.Dependency = IJobExtensions.Schedule(jobData2, base.Dependency);
	}
```


## Nested types

- `Game.Simulation.DivorceSystem+CheckDivorceJob`  
- `Game.Simulation.DivorceSystem+SumDivorceJob`  
- `Game.Simulation.DivorceSystem+TypeHandle`  

