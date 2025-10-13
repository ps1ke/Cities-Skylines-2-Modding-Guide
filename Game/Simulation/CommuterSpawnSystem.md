# Game.Simulation.CommuterSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class CommuterSpawnSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_HouseholdPrefabQuery;
    private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
    private Unity.Entities.EntityQuery m_CommuterQuery;
    private Unity.Entities.EntityQuery m_WorkerQuery;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
    private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
    private Game.Simulation.CommuterSpawnSystem+TypeHandle __TypeHandle;

    public CommuterSpawnSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_HouseholdPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
```

- `private Unity.Entities.EntityQuery m_CommuterQuery`  

```csharp
private Unity.Entities.EntityQuery m_CommuterQuery;
```

- `private Unity.Entities.EntityQuery m_WorkerQuery`  

```csharp
private Unity.Entities.EntityQuery m_WorkerQuery;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem`  

```csharp
private Game.Simulation.CountWorkplacesSystem m_CountWorkplacesSystem;
```

- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  

```csharp
private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem;
```

- `private Game.Simulation.CommuterSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.CommuterSpawnSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public CommuterSpawnSystem()`  

```csharp
[Preserve]
	public CommuterSpawnSystem()
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
		return 16;
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
		m_CountWorkplacesSystem = base.World.GetOrCreateSystemManaged<CountWorkplacesSystem>();
		m_CountHouseholdDataSystem = base.World.GetOrCreateSystemManaged<CountHouseholdDataSystem>();
		m_HouseholdPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<ArchetypeData>(), ComponentType.ReadOnly<HouseholdData>());
		m_OutsideConnectionQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Game.Objects.ElectricityOutsideConnection>(), ComponentType.Exclude<Game.Objects.WaterPipeOutsideConnection>(), ComponentType.Exclude<Building>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_CommuterQuery = GetEntityQuery(ComponentType.ReadOnly<CommuterHousehold>(), ComponentType.Exclude<Deleted>());
		m_WorkerQuery = GetEntityQuery(ComponentType.ReadOnly<Worker>(), ComponentType.Exclude<Deleted>());
		m_DemandParameterQuery = GetEntityQuery(ComponentType.ReadOnly<DemandParameterData>());
		RequireForUpdate(m_HouseholdPrefabQuery);
		RequireForUpdate(m_OutsideConnectionQuery);
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
		DemandParameterData singleton = m_DemandParameterQuery.GetSingleton<DemandParameterData>();
		int num = m_CommuterQuery.CalculateEntityCount();
		int num2 = m_WorkerQuery.CalculateEntityCount();
		if (num * singleton.m_CommuterWorkerRatioLimit < num2)
		{
			JobHandle outJobHandle;
			JobHandle outJobHandle2;
			JobHandle outJobHandle3;
			JobHandle outJobHandle4;
			SpawnCommuterHouseholdJob jobData = new SpawnCommuterHouseholdJob
			{
				m_PrefabEntities = m_HouseholdPrefabQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
				m_Archetypes = m_HouseholdPrefabQuery.ToComponentDataListAsync<ArchetypeData>(base.World.UpdateAllocator.ToAllocator, out outJobHandle2),
				m_HouseholdPrefabs = m_HouseholdPrefabQuery.ToComponentDataListAsync<HouseholdData>(base.World.UpdateAllocator.ToAllocator, out outJobHandle3),
				m_OutsideConnectionEntities = m_OutsideConnectionQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle4),
				m_Employables = m_CountHouseholdDataSystem.GetEmployables(),
				m_FreeWorkplaces = m_CountWorkplacesSystem.GetFreeWorkplaces(),
				m_DemandParameterData = singleton,
				m_OutsideConnectionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_OutsideConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Frame = m_SimulationSystem.frameIndex,
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer(),
				m_RandomSeed = RandomSeed.Next()
			};
			base.Dependency = IJobExtensions.Schedule(jobData, JobUtils.CombineDependencies(outJobHandle, outJobHandle2, outJobHandle3, base.Dependency, outJobHandle4));
			m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		}
	}
```


## Nested types

- `Game.Simulation.CommuterSpawnSystem+SpawnCommuterHouseholdJob`  
- `Game.Simulation.CommuterSpawnSystem+TypeHandle`  

