# Game.Simulation.RentAdjustSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class RentAdjustSystem : Game.GameSystemBase
{
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_DemandParameterQuery;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.EndFrameBarrier m_EndFrameBarrier;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Game.Notifications.IconCommandSystem m_IconCommandSystem;
    private Unity.Entities.EntityQuery m_HealthcareParameterQuery;
    private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
    private Unity.Entities.EntityQuery m_ParkParameterQuery;
    private Unity.Entities.EntityQuery m_EducationParameterQuery;
    private Unity.Entities.EntityQuery m_TelecomParameterQuery;
    private Unity.Entities.EntityQuery m_GarbageParameterQuery;
    private Unity.Entities.EntityQuery m_PoliceParameterQuery;
    private Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery;
    private Unity.Entities.EntityQuery m_BuildingParameterQuery;
    private Unity.Entities.EntityQuery m_PollutionParameterQuery;
    private Unity.Entities.EntityQuery m_BuildingQuery;
    protected System.Int32 cycles;
    private Game.Simulation.RentAdjustSystem+TypeHandle __TypeHandle;
    public static readonly System.Int32 kUpdatesPerDay;

    public RentAdjustSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public virtual System.Int32 GetUpdateInterval(Game.SystemUpdatePhase phase);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnUpdate();
}
```


## Fields

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
```

- `private Unity.Entities.EntityQuery m_DemandParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_DemandParameterQuery;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.EndFrameBarrier m_EndFrameBarrier`  

```csharp
private Game.EndFrameBarrier m_EndFrameBarrier;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
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

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  

```csharp
private Game.Notifications.IconCommandSystem m_IconCommandSystem;
```

- `private Unity.Entities.EntityQuery m_HealthcareParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareParameterQuery;
```

- `private Unity.Entities.EntityQuery m_ExtractorParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExtractorParameterQuery;
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

- `private Unity.Entities.EntityQuery m_BuildingParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingParameterQuery;
```

- `private Unity.Entities.EntityQuery m_PollutionParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_PollutionParameterQuery;
```

- `private Unity.Entities.EntityQuery m_BuildingQuery`  

```csharp
private Unity.Entities.EntityQuery m_BuildingQuery;
```

- `protected System.Int32 cycles`  

```csharp
protected System.Int32 cycles;
```

- `private Game.Simulation.RentAdjustSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Simulation.RentAdjustSystem+TypeHandle __TypeHandle;
```

- `public static readonly System.Int32 kUpdatesPerDay`  

```csharp
public static readonly System.Int32 kUpdatesPerDay;
```


## Constructors

- `public RentAdjustSystem()`  

```csharp
[Preserve]
	public RentAdjustSystem()
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
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_EndFrameBarrier = base.World.GetOrCreateSystemManaged<EndFrameBarrier>();
		m_ResourceSystem = base.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_GroundPollutionSystem = base.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		m_AirPollutionSystem = base.World.GetOrCreateSystemManaged<AirPollutionSystem>();
		m_NoisePollutionSystem = base.World.GetOrCreateSystemManaged<NoisePollutionSystem>();
		m_TelecomCoverageSystem = base.World.GetOrCreateSystemManaged<TelecomCoverageSystem>();
		m_CitySystem = base.World.GetOrCreateSystemManaged<CitySystem>();
		m_TaxSystem = base.World.GetOrCreateSystemManaged<TaxSystem>();
		m_IconCommandSystem = base.World.GetOrCreateSystemManaged<IconCommandSystem>();
		m_EconomyParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_DemandParameterQuery = GetEntityQuery(ComponentType.ReadOnly<DemandParameterData>());
		m_BuildingParameterQuery = GetEntityQuery(ComponentType.ReadOnly<BuildingConfigurationData>());
		m_BuildingQuery = GetEntityQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<UpdateFrame>(), ComponentType.ReadWrite<Renter>(), ComponentType.Exclude<StorageProperty>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>());
		m_ExtractorParameterQuery = GetEntityQuery(ComponentType.ReadOnly<ExtractorParameterData>());
		m_HealthcareParameterQuery = GetEntityQuery(ComponentType.ReadOnly<HealthcareParameterData>());
		m_ParkParameterQuery = GetEntityQuery(ComponentType.ReadOnly<ParkParameterData>());
		m_EducationParameterQuery = GetEntityQuery(ComponentType.ReadOnly<EducationParameterData>());
		m_TelecomParameterQuery = GetEntityQuery(ComponentType.ReadOnly<TelecomParameterData>());
		m_GarbageParameterQuery = GetEntityQuery(ComponentType.ReadOnly<GarbageParameterData>());
		m_PoliceParameterQuery = GetEntityQuery(ComponentType.ReadOnly<PoliceConfigurationData>());
		m_CitizenHappinessParameterQuery = GetEntityQuery(ComponentType.ReadOnly<CitizenHappinessParameterData>());
		m_PollutionParameterQuery = GetEntityQuery(ComponentType.ReadOnly<PollutionParameterData>());
		RequireForUpdate(m_EconomyParameterQuery);
		RequireForUpdate(m_DemandParameterQuery);
		RequireForUpdate(m_HealthcareParameterQuery);
		RequireForUpdate(m_ParkParameterQuery);
		RequireForUpdate(m_EducationParameterQuery);
		RequireForUpdate(m_TelecomParameterQuery);
		RequireForUpdate(m_GarbageParameterQuery);
		RequireForUpdate(m_PoliceParameterQuery);
		RequireForUpdate(m_BuildingQuery);
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
		uint updateFrame = SimulationUtils.GetUpdateFrame(m_SimulationSystem.frameIndex, kUpdatesPerDay, 16);
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle dependencies3;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new AdjustRentJob
		{
			m_EntityType = InternalCompilerInterface.GetEntityTypeHandle(ref __TypeHandle.__Unity_Entities_Entity_TypeHandle, ref base.CheckedStateRef),
			m_RenterType = InternalCompilerInterface.GetBufferTypeHandle(ref __TypeHandle.__Game_Buildings_Renter_RW_BufferTypeHandle, ref base.CheckedStateRef),
			m_UpdateFrameType = GetSharedComponentTypeHandle<UpdateFrame>(),
			m_PropertyRenters = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyRenter_RW_ComponentLookup, ref base.CheckedStateRef),
			m_OnMarkets = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_PropertyOnMarket_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Buildings = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Building_RW_ComponentLookup, ref base.CheckedStateRef),
			m_Prefabs = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingProperties = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingPropertyData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_BuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WorkProviders = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_WorkProvider_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CompanyNotifications = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Companies_CompanyNotifications_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Attached = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Attached_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Lots = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Lot_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Geometries = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Areas_Geometry_RO_ComponentLookup, ref base.CheckedStateRef),
			m_LandValues = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Net_LandValue_RO_ComponentLookup, ref base.CheckedStateRef),
			m_WorkplaceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_WorkplaceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_HouseholdCitizenBufs = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Citizens_HouseholdCitizen_RO_BufferLookup, ref base.CheckedStateRef),
			m_SubAreas = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Areas_SubArea_RO_BufferLookup, ref base.CheckedStateRef),
			m_InstalledUpgrades = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Buildings_InstalledUpgrade_RO_BufferLookup, ref base.CheckedStateRef),
			m_Abandoned = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_Abandoned_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Destroyed = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Common_Destroyed_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Transforms = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Transform_RO_ComponentLookup, ref base.CheckedStateRef),
			m_CityModifiers = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_City_CityModifier_RO_BufferLookup, ref base.CheckedStateRef),
			m_HealthProblems = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_HealthProblem_RO_ComponentLookup, ref base.CheckedStateRef),
			m_SpawnableBuildingData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_SpawnableBuildingData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ZoneData = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZoneData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_BuildingNotifications = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_BuildingNotifications_RW_ComponentLookup, ref base.CheckedStateRef),
			m_ExtractorProperties = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Buildings_ExtractorProperty_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourcesBuf = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Economy_Resources_RO_BufferLookup, ref base.CheckedStateRef),
			m_OwnedVehicles = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_OwnedVehicle_RO_BufferLookup, ref base.CheckedStateRef),
			m_LayoutElements = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Vehicles_LayoutElement_RO_BufferLookup, ref base.CheckedStateRef),
			m_Workers = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Worker_RO_ComponentLookup, ref base.CheckedStateRef),
			m_Citizens = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Citizens_Citizen_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ProcessDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_IndustrialProcessData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_ResourceDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ResourceData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_TaxRates = m_TaxSystem.GetTaxRates(),
			m_PollutionMap = m_GroundPollutionSystem.GetMap(readOnly: true, out dependencies),
			m_AirPollutionMap = m_AirPollutionSystem.GetMap(readOnly: true, out dependencies2),
			m_NoiseMap = m_NoisePollutionSystem.GetMap(readOnly: true, out dependencies3),
			m_CitizenHappinessParameterData = m_CitizenHappinessParameterQuery.GetSingleton<CitizenHappinessParameterData>(),
			m_BuildingConfigurationData = m_BuildingParameterQuery.GetSingleton<BuildingConfigurationData>(),
			m_PollutionParameters = m_PollutionParameterQuery.GetSingleton<PollutionParameterData>(),
			m_DeliveryTrucks = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Vehicles_DeliveryTruck_RO_ComponentLookup, ref base.CheckedStateRef),
			m_ZonePropertiesDatas = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_ZonePropertiesData_RO_ComponentLookup, ref base.CheckedStateRef),
			m_EconomyParameterData = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
			m_City = m_CitySystem.City,
			m_UpdateFrameIndex = updateFrame,
			m_CommandBuffer = m_EndFrameBarrier.CreateCommandBuffer().AsParallelWriter(),
			m_IconCommandBuffer = m_IconCommandSystem.CreateCommandBuffer()
		}, m_BuildingQuery, JobUtils.CombineDependencies(dependencies, dependencies2, dependencies3, base.Dependency));
		m_EndFrameBarrier.AddJobHandleForProducer(jobHandle);
		m_ResourceSystem.AddPrefabsReader(jobHandle);
		m_GroundPollutionSystem.AddReader(jobHandle);
		m_AirPollutionSystem.AddReader(jobHandle);
		m_NoisePollutionSystem.AddReader(jobHandle);
		m_TelecomCoverageSystem.AddReader(jobHandle);
		m_TaxSystem.AddReader(jobHandle);
		m_IconCommandSystem.AddCommandBufferWriter(jobHandle);
		base.Dependency = jobHandle;
	}
```


## Nested types

- `Game.Simulation.RentAdjustSystem+AdjustRentJob`  
- `Game.Simulation.RentAdjustSystem+TypeHandle`  

