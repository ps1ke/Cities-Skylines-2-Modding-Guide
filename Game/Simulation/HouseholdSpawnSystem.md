# Game.Simulation.HouseholdSpawnSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdSpawnSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_HouseholdPrefabQuery;
    private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.CountStudyPositionsSystem m_CountStudyPositionsSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.HouseholdSpawnSystem+TypeHandle __TypeHandle;

    public HouseholdSpawnSystem();

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

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem`  

```csharp
private Game.Simulation.ResidentialDemandSystem m_ResidentialDemandSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.CountStudyPositionsSystem m_CountStudyPositionsSystem`  

```csharp
private Game.Simulation.CountStudyPositionsSystem m_CountStudyPositionsSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.HouseholdSpawnSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.HouseholdSpawnSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HouseholdSpawnSystem()`  

```csharp
[Preserve]
	public HouseholdSpawnSystem()
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
		m_ResidentialDemandSystem = base.World.GetOrCreateSystemManaged<ResidentialDemandSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_CountStudyPositionsSystem = base.World.GetOrCreateSystemManaged<CountStudyPositionsSystem>();
		m_HouseholdPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<ArchetypeData>(), ComponentType.ReadOnly<HouseholdData>(), ComponentType.Exclude<DynamicHousehold>());
		m_OutsideConnectionQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Objects.OutsideConnection>(), ComponentType.Exclude<Game.Objects.ElectricityOutsideConnection>(), ComponentType.Exclude<Game.Objects.WaterPipeOutsideConnection>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
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
		JobHandle jobHandle = base.Dependency;
		int householdDemand = m_ResidentialDemandSystem.householdDemand;
		if (householdDemand > 0)
		{
			JobHandle deps;
			NativeArray<int> lowDensityDemandFactors = m_ResidentialDemandSystem.GetLowDensityDemandFactors(out deps);
			JobHandle deps2;
			NativeArray<int> mediumDensityDemandFactors = m_ResidentialDemandSystem.GetMediumDensityDemandFactors(out deps2);
			JobHandle deps3;
			NativeArray<int> highDensityDemandFactors = m_ResidentialDemandSystem.GetHighDensityDemandFactors(out deps3);
			jobHandle = IJobExtensions.Schedule(new SpawnHouseholdJob
			{
				m_PrefabEntities = m_HouseholdPrefabQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out var outJobHandle),
				m_Archetypes = m_HouseholdPrefabQuery.ToComponentDataListAsync<ArchetypeData>(base.World.UpdateAllocator.ToAllocator, out var outJobHandle2),
				m_OutsideConnectionEntities = m_OutsideConnectionQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out var outJobHandle3),
				m_HouseholdDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_HouseholdData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Dynamics = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_DynamicHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Populations = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_City_Population_RO_ComponentLookup, ref base.CheckedStateRef),
				m_OutsideConnectionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_OutsideConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PrefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
				m_DemandParameterData = m_DemandParameterQuery.GetSingleton<DemandParameterData>(),
				m_LowFactors = lowDensityDemandFactors,
				m_MedFactors = mediumDensityDemandFactors,
				m_HiFactors = highDensityDemandFactors,
				m_StudyPositions = m_CountStudyPositionsSystem.GetStudyPositionsByEducation(out var deps4),
				m_City = m_CitySystem.City,
				m_Demand = householdDemand,
				m_Random = RandomSeed.Next().GetRandom((int)m_SimulationSystem.frameIndex),
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer()
			}, JobUtils.CombineDependencies(outJobHandle, outJobHandle2, jobHandle, outJobHandle3, deps, deps2, deps3, deps4));
			m_ResidentialDemandSystem.AddReader(jobHandle);
			m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		}
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.HouseholdSpawnSystem+SpawnHouseholdJob`  
- `Game.Simulation.HouseholdSpawnSystem+TypeHandle`  

