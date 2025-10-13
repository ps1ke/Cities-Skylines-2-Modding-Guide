# Game.Simulation.HouseholdFindPropertySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class HouseholdFindPropertySystem : Game.GameSystemBase
{
    public System.Boolean debugDisableHomeless;
    private Game.Debug.DebugWatchDistribution m_DefaultDistribution;
    private Game.Debug.DebugWatchDistribution m_EvaluateDistributionLow;
    private Game.Debug.DebugWatchDistribution m_EvaluateDistributionMedium;
    private Game.Debug.DebugWatchDistribution m_EvaluateDistributionHigh;
    private Game.Debug.DebugWatchDistribution m_EvaluateDistributionLowrent;
    private Unity.Entities.EntityQuery m_HouseholdQuery;
    private Unity.Entities.EntityQuery m_HomelessHouseholdQuery;
    private Unity.Entities.EntityQuery m_FreePropertyQuery;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Triggers.TriggerSystem m_TriggerSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem;
    private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem;
    private Unity.Entities.EntityQuery m_HealthcareParameterQuery;
    private Unity.Entities.EntityQuery m_ParkParameterQuery;
    private Unity.Entities.EntityQuery m_EducationParameterQuery;
    private Unity.Entities.EntityQuery m_TelecomParameterQuery;
    private Unity.Entities.EntityQuery m_GarbageParameterQuery;
    private Unity.Entities.EntityQuery m_PoliceParameterQuery;
    private Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery;
    private Game.Simulation.HouseholdFindPropertySystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kMaxProcessEntitiesPerUpdate;
    public static readonly System.Int32 kFindPropertyCoolDown;
    private static const System.Int32 UPDATE_INTERVAL;

    public HouseholdFindPropertySystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `public System.Boolean debugDisableHomeless`  

```csharp
public System.Boolean debugDisableHomeless;
```

- `private Game.Debug.DebugWatchDistribution m_DefaultDistribution`  

```csharp
private Game.Debug.DebugWatchDistribution m_DefaultDistribution;
```

- `private Game.Debug.DebugWatchDistribution m_EvaluateDistributionLow`  

```csharp
private Game.Debug.DebugWatchDistribution m_EvaluateDistributionLow;
```

- `private Game.Debug.DebugWatchDistribution m_EvaluateDistributionMedium`  

```csharp
private Game.Debug.DebugWatchDistribution m_EvaluateDistributionMedium;
```

- `private Game.Debug.DebugWatchDistribution m_EvaluateDistributionHigh`  

```csharp
private Game.Debug.DebugWatchDistribution m_EvaluateDistributionHigh;
```

- `private Game.Debug.DebugWatchDistribution m_EvaluateDistributionLowrent`  

```csharp
private Game.Debug.DebugWatchDistribution m_EvaluateDistributionLowrent;
```

- `private Unity.Entities.EntityQuery m_HouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HouseholdQuery;
```

- `private Unity.Entities.EntityQuery m_HomelessHouseholdQuery`  

```csharp
private Unity.Entities.EntityQuery m_HomelessHouseholdQuery;
```

- `private Unity.Entities.EntityQuery m_FreePropertyQuery`  

```csharp
private Unity.Entities.EntityQuery m_FreePropertyQuery;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  

```csharp
private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Triggers.TriggerSystem m_TriggerSystem`  

```csharp
private Game.Triggers.TriggerSystem m_TriggerSystem;
```

- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  

```csharp
private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
```

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  

```csharp
private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
```

- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  

```csharp
private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
```

- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  

```csharp
private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```

- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  

```csharp
private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem`  

```csharp
private Game.Simulation.PropertyProcessingSystem m_PropertyProcessingSystem;
```

- `private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem`  

```csharp
private Game.Simulation.CountResidentialPropertySystem m_CountResidentialPropertySystem;
```

- `private Unity.Entities.EntityQuery m_HealthcareParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareParameterQuery;
```

- `private Unity.Entities.EntityQuery m_ParkParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ParkParameterQuery;
```

- `private Unity.Entities.EntityQuery m_EducationParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EducationParameterQuery;
```

- `private Unity.Entities.EntityQuery m_TelecomParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_TelecomParameterQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageParameterQuery;
```

- `private Unity.Entities.EntityQuery m_PoliceParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_PoliceParameterQuery;
```

- `private Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery;
```

- `private Game.Simulation.HouseholdFindPropertySystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.HouseholdFindPropertySystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kMaxProcessEntitiesPerUpdate`  

```csharp
public static readonly System.Int32 kMaxProcessEntitiesPerUpdate;
```

- `public static readonly System.Int32 kFindPropertyCoolDown`  

```csharp
public static readonly System.Int32 kFindPropertyCoolDown;
```

- `private static const System.Int32 UPDATE_INTERVAL`  

```csharp
private static const System.Int32 UPDATE_INTERVAL;
```


## Constructors

- `public HouseholdFindPropertySystem()`  

```csharp
[Preserve]
	public HouseholdFindPropertySystem()
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
		m_PathfindSetupSystem = base.World.GetOrCreateSystemManaged<PathfindSetupSystem>();
		m_GroundPollutionSystem = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		m_AirPollutionSystem = base.World.GetOrCreateSystemManaged<AirPollutionSystem>();
		m_NoisePollutionSystem = base.World.GetOrCreateSystemManaged<NoisePollutionSystem>();
		m_TelecomCoverageSystem = base.World.GetOrCreateSystemManaged<TelecomCoverageSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_CityStatisticsSystem = base.World.GetOrCreateSystemManaged<CityStatisticsSystem>();
		m_TaxSystem = base.World.GetOrCreateSystemManaged<TaxSystem>();
		m_TriggerSystem = base.World.GetOrCreateSystemManaged<TriggerSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_PropertyProcessingSystem = base.World.GetOrCreateSystemManaged<PropertyProcessingSystem>();
		m_CountResidentialPropertySystem = base.World.GetOrCreateSystemManaged<CountResidentialPropertySystem>();
		m_HomelessHouseholdQuery = GetEntityQuery(ComponentType.ReadWrite<HomelessHousehold>(), ComponentType.ReadWrite<PropertySeeker>(), ComponentType.ReadOnly<HouseholdCitizen>(), ComponentType.Exclude<MovingAway>(), ComponentType.Exclude<TouristHousehold>(), ComponentType.Exclude<CommuterHousehold>(), ComponentType.Exclude<CurrentBuilding>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_HouseholdQuery = GetEntityQuery(ComponentType.ReadWrite<Household>(), ComponentType.ReadWrite<PropertySeeker>(), ComponentType.ReadOnly<HouseholdCitizen>(), ComponentType.Exclude<HomelessHousehold>(), ComponentType.Exclude<MovingAway>(), ComponentType.Exclude<TouristHousehold>(), ComponentType.Exclude<CommuterHousehold>(), ComponentType.Exclude<CurrentBuilding>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_DemandParameterQuery = GetEntityQuery(ComponentType.ReadOnly<DemandParameterData>());
		m_HealthcareParameterQuery = GetEntityQuery(ComponentType.ReadOnly<HealthcareParameterData>());
		m_ParkParameterQuery = GetEntityQuery(ComponentType.ReadOnly<ParkParameterData>());
		m_EducationParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EducationParameterData>());
		m_TelecomParameterQuery = GetEntityQuery(ComponentType.ReadOnly<TelecomParameterData>());
		m_GarbageParameterQuery = GetEntityQuery(ComponentType.ReadOnly<GarbageParameterData>());
		m_PoliceParameterQuery = GetEntityQuery(ComponentType.ReadOnly<PoliceConfigurationData>());
		m_CitizenHappinessParameterQuery = GetEntityQuery(ComponentType.ReadOnly<CitizenHappinessParameterData>());
		EntityQueryDesc entityQueryDesc = new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Building>() },
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Abandoned>(),
				ComponentType.ReadOnly<Game.Buildings.Park>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Temp>()
			}
		};
		EntityQueryDesc entityQueryDesc2 = new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<PropertyOnMarket>(),
				ComponentType.ReadOnly<ResidentialProperty>(),
				ComponentType.ReadOnly<Building>()
			},
			None = new ComponentType[5]
			{
				ComponentType.ReadOnly<Abandoned>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Condemned>()
			}
		};
		m_FreePropertyQuery = GetEntityQuery(entityQueryDesc, entityQueryDesc2);
		RequireForUpdate(m_EconomyParameterQuery);
		RequireForUpdate(m_HealthcareParameterQuery);
		RequireForUpdate(m_ParkParameterQuery);
		RequireForUpdate(m_EducationParameterQuery);
		RequireForUpdate(m_TelecomParameterQuery);
		RequireForUpdate(m_HouseholdQuery);
		RequireForUpdate(m_DemandParameterQuery);
		m_DefaultDistribution = new DebugWatchDistribution(persistent: true, relative: true);
		m_EvaluateDistributionLow = new DebugWatchDistribution(persistent: true, relative: true);
		m_EvaluateDistributionMedium = new DebugWatchDistribution(persistent: true, relative: true);
		m_EvaluateDistributionHigh = new DebugWatchDistribution(persistent: true, relative: true);
		m_EvaluateDistributionLowrent = new DebugWatchDistribution(persistent: true, relative: true);
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
		m_DefaultDistribution.Dispose();
		m_EvaluateDistributionLow.Dispose();
		m_EvaluateDistributionMedium.Dispose();
		m_EvaluateDistributionHigh.Dispose();
		m_EvaluateDistributionLowrent.Dispose();
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		NativeParallelHashMap<Entity, CachedPropertyInformation> cachedPropertyInfo = new NativeParallelHashMap<Entity, CachedPropertyInformation>(m_FreePropertyQuery.CalculateEntityCount(), Allocator.TempJob);
		JobHandle dependencies;
		NativeArray<GroundPollution> map = m_GroundPollutionSystem.GetMap(readOnly: true, out dependencies);
		JobHandle dependencies2;
		NativeArray<AirPollution> map2 = m_AirPollutionSystem.GetMap(readOnly: true, out dependencies2);
		JobHandle dependencies3;
		NativeArray<NoisePollution> map3 = m_NoisePollutionSystem.GetMap(readOnly: true, out dependencies3);
		JobHandle dependencies4;
		CellMapData<TelecomCoverage> data = m_TelecomCoverageSystem.GetData(readOnly: true, out dependencies4);
		PreparePropertyJob jobData = new PreparePropertyJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_BuildingProperties = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ParkDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ParkData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Renters = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_Renter_RO_BufferLookup, ref base.CheckedStateRef),
			m_Households = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Abandoneds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Parks = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Park_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnableDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingPropertyData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Buildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceCoverages = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ServiceCoverage_RO_BufferLookup, ref base.CheckedStateRef),
			m_Crimes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_CrimeProducer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Locked = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Transforms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_ElectricityConsumers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterConsumers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GarbageProducers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_GarbageProducer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MailProducers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_MailProducer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PollutionMap = map,
			m_AirPollutionMap = map2,
			m_NoiseMap = map3,
			m_TelecomCoverages = data,
			m_HealthcareParameters = m_HealthcareParameterQuery.GetSingleton<HealthcareParameterData>(),
			m_ParkParameters = m_ParkParameterQuery.GetSingleton<ParkParameterData>(),
			m_EducationParameters = m_EducationParameterQuery.GetSingleton<EducationParameterData>(),
			m_TelecomParameters = m_TelecomParameterQuery.GetSingleton<TelecomParameterData>(),
			m_GarbageParameters = m_GarbageParameterQuery.GetSingleton<GarbageParameterData>(),
			m_PoliceParameters = m_PoliceParameterQuery.GetSingleton<PoliceConfigurationData>(),
			m_CitizenHappinessParameterData = m_CitizenHappinessParameterQuery.GetSingleton<CitizenHappinessParameterData>(),
			m_City = m_CitySystem.City,
			m_PropertyData = cachedPropertyInfo.AsParallelWriter()
		};
		JobHandle outJobHandle;
		JobHandle outJobHandle2;
		JobHandle deps;
		FindPropertyJob jobData2 = new FindPropertyJob
		{
			m_HomelessHouseholdEntities = m_HomelessHouseholdQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle),
			m_MovedInHouseholdEntities = m_HouseholdQuery.ToEntityListAsync(base.World.UpdateAllocator.ToAllocator, out outJobHandle2),
			m_CachedPropertyInfo = cachedPropertyInfo,
			m_BuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertiesOnMarket = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyOnMarket_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Availabilities = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ResourceAvailability_RO_BufferLookup, ref base.CheckedStateRef),
			m_SpawnableDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingProperties = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Buildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathInformationBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Pathfind_PathInformations_RO_BufferLookup, ref base.CheckedStateRef),
			m_PrefabRefs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ServiceCoverages = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Net_ServiceCoverage_RO_BufferLookup, ref base.CheckedStateRef),
			m_Workers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Students = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Student_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HomelessHouseholds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HomelessHousehold_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Crimes = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_CrimeProducer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Lockeds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_Locked_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Transforms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_HealthProblems = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Abandoneds = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Parks = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Park_RO_ComponentLookup, ref base.CheckedStateRef),
			m_OwnedVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferLookup, ref base.CheckedStateRef),
			m_ElectricityConsumers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ElectricityConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WaterConsumers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_WaterConsumer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_GarbageProducers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_GarbageProducer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_MailProducers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_MailProducer_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Households = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Household_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentBuildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentBuilding_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CurrentTransports = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_CurrentTransport_RO_ComponentLookup, ref base.CheckedStateRef),
			m_PathInformations = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Pathfind_PathInformation_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CitizenBuffers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_PropertySeekers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Agents_PropertySeeker_RW_ComponentLookup, ref base.CheckedStateRef),
			m_PollutionMap = map,
			m_AirPollutionMap = map2,
			m_NoiseMap = map3,
			m_TelecomCoverages = data,
			m_ResidentialPropertyData = m_CountResidentialPropertySystem.GetResidentialPropertyData(),
			m_HealthcareParameters = m_HealthcareParameterQuery.GetSingleton<HealthcareParameterData>(),
			m_ParkParameters = m_ParkParameterQuery.GetSingleton<ParkParameterData>(),
			m_EducationParameters = m_EducationParameterQuery.GetSingleton<EducationParameterData>(),
			m_TelecomParameters = m_TelecomParameterQuery.GetSingleton<TelecomParameterData>(),
			m_GarbageParameters = m_GarbageParameterQuery.GetSingleton<GarbageParameterData>(),
			m_PoliceParameters = m_PoliceParameterQuery.GetSingleton<PoliceConfigurationData>(),
			m_CitizenHappinessParameterData = m_CitizenHappinessParameterQuery.GetSingleton<CitizenHappinessParameterData>(),
			m_TaxRates = m_TaxSystem.GetTaxRates(),
			m_EconomyParameters = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
			m_SimulationFrame = m_SimulationSystem.frameIndex,
			m_RentActionQueue = m_PropertyProcessingSystem.GetRentActionQueue(out deps).AsParallelWriter(),
			m_City = m_CitySystem.City,
			m_PathfindQueue = m_PathfindSetupSystem.GetQueue(this, 80, 16).AsParallelWriter(),
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer()
		};
		JobHandle job = JobChunkExtensions.ScheduleParallel(jobData, m_FreePropertyQuery, JobUtils.CombineDependencies(base.Dependency, dependencies, dependencies3, dependencies2, dependencies4, deps));
		base.Dependency = IJobExtensions.Schedule(jobData2, JobHandle.CombineDependencies(job, outJobHandle2, outJobHandle));
		m_EndFrameBarrier.AddJobHandleForProducer(base.Dependency);
		m_PathfindSetupSystem.AddQueueWriter(base.Dependency);
		m_AirPollutionSystem.AddReader(base.Dependency);
		m_NoisePollutionSystem.AddReader(base.Dependency);
		m_GroundPollutionSystem.AddReader(base.Dependency);
		m_TelecomCoverageSystem.AddReader(base.Dependency);
		m_TriggerSystem.AddActionBufferWriter(base.Dependency);
		m_CityStatisticsSystem.AddWriter(base.Dependency);
		m_TaxSystem.AddReader(base.Dependency);
		cachedPropertyInfo.Dispose(base.Dependency);
	}
```


## Nested types

- `Game.Simulation.HouseholdFindPropertySystem+CachedPropertyInformation`  
- `Game.Simulation.HouseholdFindPropertySystem+GenericApartmentQuality`  
- `Game.Simulation.HouseholdFindPropertySystem+PreparePropertyJob`  
- `Game.Simulation.HouseholdFindPropertySystem+FindPropertyJob`  
- `Game.Simulation.HouseholdFindPropertySystem+TypeHandle`  

