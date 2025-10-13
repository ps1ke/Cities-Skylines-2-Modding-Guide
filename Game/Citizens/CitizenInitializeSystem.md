# Game.Citizens.CitizenInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CitizenInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_NewCitizenQuery;
    private Unity.Entities.EntityQuery m_TimeSettingQuery;
    private Unity.Entities.EntityQuery m_CitizenPrefabQuery;
    private Unity.Entities.EntityQuery m_TimeDataQuery;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Common.ModificationBarrier5 m_EndFrameBarrier;
    private Game.Citizens.CitizenInitializeSystem+TypeHandle __TypeHandle;

    public CitizenInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_NewCitizenQuery`  

```csharp
private Unity.Entities.EntityQuery m_NewCitizenQuery;
```

- `private Unity.Entities.EntityQuery m_TimeSettingQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeSettingQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_TimeDataQuery`  

```csharp
private Unity.Entities.EntityQuery m_TimeDataQuery;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Common.ModificationBarrier5 m_EndFrameBarrier`  

```csharp
private Game.Common.ModificationBarrier5 m_EndFrameBarrier;
```

- `private Game.Citizens.CitizenInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Citizens.CitizenInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CitizenInitializeSystem()`  

```csharp
[Preserve]
	public CitizenInitializeSystem()
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
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier5>();
		m_NewCitizenQuery = GetEntityQuery(ComponentType.ReadWrite<Citizen>(), ComponentType.ReadWrite<HouseholdMember>(), ComponentType.ReadOnly<Created>(), ComponentType.Exclude<Temp>());
		m_CitizenPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<CitizenData>());
		m_TimeSettingQuery = GetEntityQuery(ComponentType.ReadOnly<TimeSettingsData>());
		m_TimeDataQuery = GetEntityQuery(ComponentType.ReadOnly<TimeData>());
		m_DemandParameterQuery = GetEntityQuery(ComponentType.ReadOnly<DemandParameterData>());
		RequireForUpdate(m_NewCitizenQuery);
		RequireForUpdate(m_TimeDataQuery);
		RequireForUpdate(m_TimeSettingQuery);
		RequireForUpdate(m_DemandParameterQuery);
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
		JobHandle outJobHandle;
		InitializeCitizenJob jobData = new InitializeCitizenJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_HouseholdMemberType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_HouseholdMember_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CitizenPrefabs = m_CitizenPrefabQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RW_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RW_BufferLookup, ref base.CheckedStateRef),
			m_CitizenDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_CitizenData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Arriveds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Arrived_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CarKeepers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CarKeeper_RW_ComponentLookup, ref base.CheckedStateRef),
			m_HasJobSeekers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Agents_HasJobSeeker_RW_ComponentLookup, ref base.CheckedStateRef),
			m_PropertySeekers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Agents_PropertySeeker_RW_ComponentLookup, ref base.CheckedStateRef),
			m_MailSenders = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_MailSender_RW_ComponentLookup, ref base.CheckedStateRef),
			m_CrimeVictims = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CrimeVictim_RW_ComponentLookup, ref base.CheckedStateRef),
			m_DemandParameters = m_DemandParameterQuery.GetSingleton<DemandParameterData>(),
			m_TimeSettings = m_TimeSettingQuery.GetSingleton<TimeSettingsData>(),
			m_TimeData = m_TimeDataQuery.GetSingleton<TimeData>(),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_RandomSeed = RandomSeed.Next(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_TriggerBuffer = m_TriggerSystem.CreateActionBuffer().AsParallelWriter()
		};
		base.Dependency = JobChunkExtensions.Schedule(jobData, m_NewCitizenQuery, JobHandle.CombineDependencies(base.Dependency, outJobHandle));
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Citizens.CitizenInitializeSystem+InitializeCitizenJob`  
- `Game.Citizens.CitizenInitializeSystem+TypeHandle`  

