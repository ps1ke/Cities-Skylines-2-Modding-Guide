# Game.Simulation.PropertyProcessingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class PropertyProcessingSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_CommercialCompanyPrefabQuery;
    private Unity.Entities.EntityQuery m_IndustrialCompanyPrefabQuery;
    private Unity.Entities.EntityQuery m_PropertyGroupQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Entities.EntityArchetype m_RentEventArchetype;
    private Unity.Entities.EntityArchetype m_MovedEventArchetype;
    private Unity.Collections.NativeQueue<Game.Buildings.RentAction> m_RentActionQueue;
    private Unity.Collections.NativeList<Unity.Entities.Entity> m_ReservedProperties;
    private Unity.Jobs.JobHandle m_Writers;
    private Game.Simulation.PropertyProcessingSystem+TypeHandle __TypeHandle;

    public PropertyProcessingSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddWriter(Unity.Jobs.JobHandle writer);
    public Unity.Collections.NativeQueue<Game.Buildings.RentAction> GetRentActionQueue(Unity.Jobs.JobHandle& deps);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_CommercialCompanyPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_CommercialCompanyPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_IndustrialCompanyPrefabQuery`  

```csharp
private Unity.Entities.EntityQuery m_IndustrialCompanyPrefabQuery;
```

- `private Unity.Entities.EntityQuery m_PropertyGroupQuery`  

```csharp
private Unity.Entities.EntityQuery m_PropertyGroupQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Entities.EntityArchetype m_RentEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_RentEventArchetype;
```

- `private Unity.Entities.EntityArchetype m_MovedEventArchetype`  

```csharp
private Unity.Entities.EntityArchetype m_MovedEventArchetype;
```

- `private Unity.Collections.NativeQueue<Game.Buildings.RentAction> m_RentActionQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Buildings.RentAction> m_RentActionQueue;
```

- `private Unity.Collections.NativeList<Unity.Entities.Entity> m_ReservedProperties`  

```csharp
private Unity.Collections.NativeList<Unity.Entities.Entity> m_ReservedProperties;
```

- `private Unity.Jobs.JobHandle m_Writers`  

```csharp
private Unity.Jobs.JobHandle m_Writers;
```

- `private Game.Simulation.PropertyProcessingSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.PropertyProcessingSystem+TypeHandle __TypeHandle;
```


## Constructors

- `public PropertyProcessingSystem()`  

```csharp
[Preserve]
	public PropertyProcessingSystem()
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

- `public AddWriter(Unity.Jobs.JobHandle writer) : System.Void`  

```csharp
public void AddWriter(JobHandle writer)
	{
		m_Writers = JobHandle.CombineDependencies(m_Writers, writer);
	}
```

- `public GetRentActionQueue(Unity.Jobs.JobHandle& deps) : Unity.Collections.NativeQueue<Game.Buildings.RentAction>`  

```csharp
public NativeQueue<RentAction> GetRentActionQueue(out JobHandle deps)
	{
		Assert.IsTrue(base.Enabled, "Can not write to queue when system isn't running");
		deps = m_Writers;
		return m_RentActionQueue;
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
		m_RentActionQueue = new NativeQueue<RentAction>(Allocator.Persistent);
		m_ReservedProperties = new NativeList<Entity>(Allocator.Persistent);
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_RentEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<RentersUpdated>());
		m_MovedEventArchetype = base.EntityManager.CreateArchetype(ComponentType.ReadWrite<Game.Common.Event>(), ComponentType.ReadWrite<PathTargetMoved>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_PropertyGroupQuery = GetEntityQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Building>(),
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadWrite<PropertyToBeOnMarket>()
			},
			Any = new ComponentType[4]
			{
				ComponentType.ReadOnly<CommercialProperty>(),
				ComponentType.ReadOnly<ResidentialProperty>(),
				ComponentType.ReadOnly<IndustrialProperty>(),
				ComponentType.ReadOnly<ExtractorProperty>()
			},
			None = new ComponentType[2]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_CommercialCompanyPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<ArchetypeData>(), ComponentType.ReadOnly<CommercialCompanyData>(), ComponentType.ReadOnly<IndustrialProcessData>());
		m_IndustrialCompanyPrefabQuery = GetEntityQuery(ComponentType.ReadOnly<ArchetypeData>(), ComponentType.ReadOnly<IndustrialCompanyData>(), ComponentType.ReadOnly<IndustrialProcessData>(), ComponentType.Exclude<StorageCompanyData>());
		RequireForUpdate(m_EconomyParameterQuery);
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
		m_RentActionQueue.Dispose();
		m_ReservedProperties.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (!m_PropertyGroupQuery.IsEmptyIgnoreFilter)
		{
			JobHandle outJobHandle;
			JobHandle outJobHandle2;
			PutPropertyOnMarketJob jobData = new PutPropertyOnMarketJob
			{
				m_CommercialCompanyPrefabs = m_CommercialCompanyPrefabQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
				m_IndustrialCompanyPrefabs = m_IndustrialCompanyPrefabQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle2),
				m_Archetypes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ArchetypeData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
				m_PrefabType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_BuildingType = InternalCompilerInterface.GetComponentTypeHandle(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentTypeHandle, ref base.CheckedStateRef),
				m_BuildingPropertyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_PropertyOnMarkets = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyOnMarket_RO_ComponentLookup, ref base.CheckedStateRef),
				m_LandValues = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LandValue_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SpawnableBuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_IndustrialProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_BuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_ZoneDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
				m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
				m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
				m_Lots = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Lot_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Geometries = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Geometry_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Attacheds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
				m_Abandoneds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
				m_EconomyParameterData = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
				m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter()
			};
			base.Dependency = JobChunkExtensions.ScheduleParallel(jobData, m_PropertyGroupQuery, JobHandle.CombineDependencies(outJobHandle, outJobHandle2, base.Dependency));
			m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		}
		JobHandle deps;
		PropertyRentJob jobData2 = new PropertyRentJob
		{
			m_RentEventArchetype = m_RentEventArchetype,
			m_MovedEventArchetype = m_MovedEventArchetype,
			m_PropertiesOnMarket = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyOnMarket_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Renters = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RW_BufferLookup, ref base.CheckedStateRef),
			m_BuildingPropertyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ParkData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PrefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Companies = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_CompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Households = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Industrials = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_IndustrialCompany_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Commercials = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_CommercialCompany_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TriggerQueue = m_TriggerSystem.CreateActionBuffer(),
			m_BuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceCompanyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_ServiceCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_IndustrialProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WorkProviders = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_WorkProvider_RW_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdCitizens = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_Abandoneds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HomelessHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HomelessHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Parks = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Park_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Employees = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Companies_Employee_RO_BufferLookup, ref base.CheckedStateRef),
			m_SpawnableBuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Attacheds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ExtractorCompanyDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ExtractorCompanyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SubAreaBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_Geometries = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Geometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Lots = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Lot_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_Resources = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ZoneDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_StatisticsQueue = m_CityStatisticsSystem.GetStatisticsEventQueue(out deps),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer(),
			m_RentActionQueue = m_RentActionQueue,
			m_ReservedProperties = m_ReservedProperties,
			m_DebugDisableHomeless = false
		};
		base.Dependency = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(base.Dependency, m_Writers, deps));
		m_CityStatisticsSystem.AddWriter(base.Dependency);
		m_TriggerSystem.AddActionBufferWriter(base.Dependency);
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.PropertyProcessingSystem+PutPropertyOnMarketJob`  
- `Game.Simulation.PropertyProcessingSystem+PropertyRentJob`  
- `Game.Simulation.PropertyProcessingSystem+TypeHandle`  

