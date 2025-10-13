# Game.Citizens.HouseholdInitializeSystem

**Assembly:** `Game`  
**Namespace:** `Game.Citizens`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdInitializeSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CarPrefabGroup;
    private Unity.Entities.EntityQuery m_CitizenPrefabGroup;
    private Unity.Entities.EntityQuery m_HouseholdPetPrefabGroup;
    private Unity.Entities.EntityQuery m_Additions;
    private Game.Common.ModificationBarrier4 m_EndFrameBarrier;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
    private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData;
    private Game.Citizens.HouseholdInitializeSystem+TypeHandle __TypeHandle;

    public HouseholdInitializeSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CarPrefabGroup`  

```csharp
private Unity.Entities.EntityQuery m_CarPrefabGroup;
```

- `private Unity.Entities.EntityQuery m_CitizenPrefabGroup`  

```csharp
private Unity.Entities.EntityQuery m_CitizenPrefabGroup;
```

- `private Unity.Entities.EntityQuery m_HouseholdPetPrefabGroup`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdPetPrefabGroup;
```

- `private Unity.Entities.EntityQuery m_Additions`  

```csharp
private Unity.Entities.EntityQuery m_Additions;
```

- `private Game.Common.ModificationBarrier4 m_EndFrameBarrier`  

```csharp
private Game.Common.ModificationBarrier4 m_EndFrameBarrier;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  

```csharp
private Game.City.CityConfigurationSystem m_CityConfigurationSystem;
```

- `private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData`  

```csharp
private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData;
```

- `private Game.Citizens.HouseholdInitializeSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Citizens.HouseholdInitializeSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public HouseholdInitializeSystem()`  

```csharp
[Preserve]
	public HouseholdInitializeSystem()
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
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<ModificationBarrier4>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_CityConfigurationSystem = base.World.GetOrCreateSystemManaged<CityConfigurationSystem>();
		m_PersonalCarSelectData = new PersonalCarSelectData(this);
		m_CarPrefabGroup = GetEntityQuery(PersonalCarSelectData.GetEntityQueryDesc());
		m_CitizenPrefabGroup = GetEntityQuery(ComponentType.ReadOnly<CitizenData>(), ComponentType.ReadOnly<ArchetypeData>());
		m_HouseholdPetPrefabGroup = GetEntityQuery(ComponentType.ReadOnly<HouseholdPetData>(), ComponentType.ReadOnly<ArchetypeData>());
		m_Additions = GetEntityQuery(ComponentType.ReadWrite<Household>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadWrite<HouseholdCitizen>(), ComponentType.ReadOnly<CurrentBuilding>(), ComponentType.ReadWrite<Game.Economy.Resources>(), ComponentType.Exclude<Temp>());
		RequireForUpdate(m_Additions);
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
		m_PersonalCarSelectData.PreUpdate(this, m_CityConfigurationSystem, m_CarPrefabGroup, Allocator.TempJob, out var jobHandle);
		JobHandle outJobHandle;
		JobHandle outJobHandle2;
		JobHandle outJobHandle3;
		JobHandle outJobHandle4;
		JobHandle deps;
		JobHandle jobHandle2 = JobChunkExtensions.ScheduleParallel(new InitializeHouseholdJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_CurrentBuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_ResourceType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Economy_Resources_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_TouristHouseholdType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_TouristHousehold_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CommuterHouseholdType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_CommuterHousehold_RO_ComponentTypeHandle, ref base.CheckedStateRef),
			m_HouseholdType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Citizens_Household_RW_ComponentTypeHandle, ref base.CheckedStateRef),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_TransformData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_HouseholdData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_DynamicHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_DynamicHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OutsideConnectionDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_OutsideConnectionData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CitizenPrefabs = m_CitizenPrefabGroup.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_HouseholdPetPrefabs = m_HouseholdPetPrefabGroup.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle2),
			m_CitizenPrefabArchetypes = m_CitizenPrefabGroup.ToComponentDataListAsync<ArchetypeData>(base.World.UpdateAllocator.ToAllocator, out outJobHandle3),
			m_HouseholdPetArchetypes = m_HouseholdPetPrefabGroup.ToComponentDataListAsync<ArchetypeData>(base.World.UpdateAllocator.ToAllocator, out outJobHandle4),
			m_StatisticsQueue = m_CityStatisticsSystem.GetSafeStatisticsQueue(out deps),
			m_RandomSeed = RandomSeed.Next(),
			m_PersonalCarSelectData = m_PersonalCarSelectData
		}, m_Additions, JobUtils.CombineDependencies(base.Dependency, outJobHandle, outJobHandle2, outJobHandle3, outJobHandle4, deps, jobHandle));
		m_PersonalCarSelectData.PostUpdate(jobHandle2);
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle2);
		m_CityStatisticsSystem.AddWriter(jobHandle2);
		base.Dependency = jobHandle2;
	}
```


## Nested types

- `Game.Citizens.HouseholdInitializeSystem+InitializeHouseholdJob`  
- `Game.Citizens.HouseholdInitializeSystem+TypeHandle`  

