# Game.Simulation.CitizenPathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct CitizenPathfindSetup
{
    private Unity.Entities.EntityQuery m_LeisureProviderQuery;
    private Unity.Entities.EntityQuery m_TouristTargetQuery;
    private Unity.Entities.EntityQuery m_SchoolQuery;
    private Unity.Entities.EntityQuery m_FreeWorkplaceQuery;
    private Unity.Entities.EntityQuery m_AttractionQuery;
    private Unity.Entities.EntityQuery m_HomelessShelterQuery;
    private Unity.Entities.EntityQuery m_FindHomeQuery;
    private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem;
    private Game.Simulation.AirPollutionSystem m_AirPollutionSystem;
    private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem;
    private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem;
    private Game.Simulation.CitySystem m_CitySystem;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Game.Simulation.LeisureSystem m_LeisureSystem;
    private Game.Simulation.TaxSystem m_TaxSystem;
    private Unity.Entities.EntityQuery m_EconomyParameterQuery;
    private Unity.Entities.EntityQuery m_HealthcareParameterQuery;
    private Unity.Entities.EntityQuery m_ParkParameterQuery;
    private Unity.Entities.EntityQuery m_EducationParameterQuery;
    private Unity.Entities.EntityQuery m_TelecomParameterQuery;
    private Unity.Entities.EntityQuery m_GarbageParameterQuery;
    private Unity.Entities.EntityQuery m_PoliceParameterQuery;
    private Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery;
    private Unity.Entities.EntityQuery m_ServiceFeeParameterQuery;
    private Unity.Entities.EntityTypeHandle m_EntityType;
    private Unity.Entities.ComponentTypeHandle<Game.Companies.ServiceAvailable> m_ServiceAvailableType;
    private Unity.Entities.ComponentTypeHandle<Game.Companies.FreeWorkplaces> m_FreeWorkplaceType;
    private Unity.Entities.ComponentTypeHandle<Game.Companies.WorkProvider> m_WorkProviderType;
    private Unity.Entities.ComponentTypeHandle<Game.City.CityServiceUpkeep> m_CityServiceType;
    private Unity.Entities.ComponentTypeHandle<Game.Buildings.Building> m_BuildingType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
    private Unity.Entities.BufferTypeHandle<Game.Buildings.Renter> m_RenterType;
    private Unity.Entities.BufferTypeHandle<Game.Buildings.Student> m_StudentType;
    private Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_UpgradeType;
    private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections;
    private Unity.Entities.ComponentLookup<Game.Companies.ServiceCompanyData> m_ServiceDatas;
    private Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Buildings;
    private Unity.Entities.ComponentLookup<Game.Citizens.Household> m_Households;
    private Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> m_HomelessHouseholds;
    private Unity.Entities.ComponentLookup<Game.Citizens.Worker> m_Workers;
    private Unity.Entities.ComponentLookup<Game.Citizens.Student> m_Students;
    private Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_Citizens;
    private Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblems;
    private Unity.Entities.ComponentLookup<Game.Citizens.TouristHousehold> m_TouristHouseholds;
    private Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizens;
    private Unity.Entities.ComponentLookup<Game.Objects.Transform> m_Transforms;
    private Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingDatas;
    private Unity.Entities.BufferLookup<Game.Buildings.Efficiency> m_Efficiencies;
    private Unity.Entities.ComponentLookup<Game.Companies.LodgingProvider> m_LodgingProviders;
    private Unity.Entities.ComponentLookup<Game.Buildings.AttractivenessProvider> m_AttractivenessProviders;
    private Unity.Entities.ComponentLookup<Game.Buildings.PropertyOnMarket> m_PropertiesOnMarket;
    private Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters;
    private Unity.Entities.ComponentLookup<Game.Buildings.CrimeProducer> m_Crimes;
    private Unity.Entities.ComponentLookup<Game.Buildings.Park> m_Parks;
    private Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_Abandoneds;
    private Unity.Entities.ComponentLookup<Game.Buildings.ElectricityConsumer> m_ElectricityConsumers;
    private Unity.Entities.ComponentLookup<Game.Buildings.WaterConsumer> m_WaterConsumers;
    private Unity.Entities.ComponentLookup<Game.Buildings.GarbageProducer> m_GarbageProducers;
    private Unity.Entities.ComponentLookup<Game.Buildings.MailProducer> m_MailProducers;
    private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInfos;
    private Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs;
    private Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_IndustrialProcessDatas;
    private Unity.Entities.ComponentLookup<Game.Prefabs.LeisureProviderData> m_LeisureProviderDatas;
    private Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDatas;
    private Unity.Entities.ComponentLookup<Game.Prefabs.SchoolData> m_SchoolDatas;
    private Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_PrefabBuildingDatas;
    private Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_BuildingProperties;
    private Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableDatas;
    private Unity.Entities.ComponentLookup<Game.Prefabs.Locked> m_Lockeds;
    private Unity.Entities.BufferLookup<Game.Economy.Resources> m_Resources;
    private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts;
    private Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> m_Availabilities;
    private Unity.Entities.BufferLookup<Game.Net.ServiceCoverage> m_ServiceCoverages;
    private Unity.Entities.BufferLookup<Game.Buildings.Renter> m_Renters;
    private Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifiers;
    private Unity.Entities.BufferLookup<Game.Vehicles.OwnedVehicle> m_OwnedVehicles;

    public CitizenPathfindSetup(Game.Simulation.PathfindSetupSystem system);

    public Unity.Jobs.JobHandle SetupAttraction(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupFindHome(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupHomeless(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupJobSeekerTo(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupLeisureTarget(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupSchoolSeekerTo(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupTouristTarget(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_LeisureProviderQuery`  

```csharp
private Unity.Entities.EntityQuery m_LeisureProviderQuery;
```

- `private Unity.Entities.EntityQuery m_TouristTargetQuery`  

```csharp
private Unity.Entities.EntityQuery m_TouristTargetQuery;
```

- `private Unity.Entities.EntityQuery m_SchoolQuery`  

```csharp
private Unity.Entities.EntityQuery m_SchoolQuery;
```

- `private Unity.Entities.EntityQuery m_FreeWorkplaceQuery`  

```csharp
private Unity.Entities.EntityQuery m_FreeWorkplaceQuery;
```

- `private Unity.Entities.EntityQuery m_AttractionQuery`  

```csharp
private Unity.Entities.EntityQuery m_AttractionQuery;
```

- `private Unity.Entities.EntityQuery m_HomelessShelterQuery`  

```csharp
private Unity.Entities.EntityQuery m_HomelessShelterQuery;
```

- `private Unity.Entities.EntityQuery m_FindHomeQuery`  

```csharp
private Unity.Entities.EntityQuery m_FindHomeQuery;
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

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Game.Simulation.LeisureSystem m_LeisureSystem`  

```csharp
private Game.Simulation.LeisureSystem m_LeisureSystem;
```

- `private Game.Simulation.TaxSystem m_TaxSystem`  

```csharp
private Game.Simulation.TaxSystem m_TaxSystem;
```

- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EconomyParameterQuery;
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

- `private Unity.Entities.EntityQuery m_ServiceFeeParameterQuery`  

```csharp
private Unity.Entities.EntityQuery m_ServiceFeeParameterQuery;
```

- `private Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
private Unity.Entities.EntityTypeHandle m_EntityType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Companies.ServiceAvailable> m_ServiceAvailableType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Companies.ServiceAvailable> m_ServiceAvailableType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Companies.FreeWorkplaces> m_FreeWorkplaceType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Companies.FreeWorkplaces> m_FreeWorkplaceType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Companies.WorkProvider> m_WorkProviderType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Companies.WorkProvider> m_WorkProviderType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.City.CityServiceUpkeep> m_CityServiceType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.City.CityServiceUpkeep> m_CityServiceType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.Building> m_BuildingType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Buildings.Building> m_BuildingType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Buildings.Renter> m_RenterType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Buildings.Renter> m_RenterType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Buildings.Student> m_StudentType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Buildings.Student> m_StudentType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_UpgradeType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_UpgradeType;
```

- `private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections`  

```csharp
private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections;
```

- `private Unity.Entities.ComponentLookup<Game.Companies.ServiceCompanyData> m_ServiceDatas`  

```csharp
private Unity.Entities.ComponentLookup<Game.Companies.ServiceCompanyData> m_ServiceDatas;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Buildings`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Buildings;
```

- `private Unity.Entities.ComponentLookup<Game.Citizens.Household> m_Households`  

```csharp
private Unity.Entities.ComponentLookup<Game.Citizens.Household> m_Households;
```

- `private Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> m_HomelessHouseholds`  

```csharp
private Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> m_HomelessHouseholds;
```

- `private Unity.Entities.ComponentLookup<Game.Citizens.Worker> m_Workers`  

```csharp
private Unity.Entities.ComponentLookup<Game.Citizens.Worker> m_Workers;
```

- `private Unity.Entities.ComponentLookup<Game.Citizens.Student> m_Students`  

```csharp
private Unity.Entities.ComponentLookup<Game.Citizens.Student> m_Students;
```

- `private Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_Citizens`  

```csharp
private Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_Citizens;
```

- `private Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblems`  

```csharp
private Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblems;
```

- `private Unity.Entities.ComponentLookup<Game.Citizens.TouristHousehold> m_TouristHouseholds`  

```csharp
private Unity.Entities.ComponentLookup<Game.Citizens.TouristHousehold> m_TouristHouseholds;
```

- `private Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizens`  

```csharp
private Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizens;
```

- `private Unity.Entities.ComponentLookup<Game.Objects.Transform> m_Transforms`  

```csharp
private Unity.Entities.ComponentLookup<Game.Objects.Transform> m_Transforms;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingDatas`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingDatas;
```

- `private Unity.Entities.BufferLookup<Game.Buildings.Efficiency> m_Efficiencies`  

```csharp
private Unity.Entities.BufferLookup<Game.Buildings.Efficiency> m_Efficiencies;
```

- `private Unity.Entities.ComponentLookup<Game.Companies.LodgingProvider> m_LodgingProviders`  

```csharp
private Unity.Entities.ComponentLookup<Game.Companies.LodgingProvider> m_LodgingProviders;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.AttractivenessProvider> m_AttractivenessProviders`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.AttractivenessProvider> m_AttractivenessProviders;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.PropertyOnMarket> m_PropertiesOnMarket`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.PropertyOnMarket> m_PropertiesOnMarket;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.CrimeProducer> m_Crimes`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.CrimeProducer> m_Crimes;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.Park> m_Parks`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.Park> m_Parks;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_Abandoneds`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_Abandoneds;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.ElectricityConsumer> m_ElectricityConsumers`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.ElectricityConsumer> m_ElectricityConsumers;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.WaterConsumer> m_WaterConsumers`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.WaterConsumer> m_WaterConsumers;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.GarbageProducer> m_GarbageProducers`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.GarbageProducer> m_GarbageProducers;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.MailProducer> m_MailProducers`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.MailProducer> m_MailProducers;
```

- `private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInfos`  

```csharp
private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInfos;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_IndustrialProcessDatas`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_IndustrialProcessDatas;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.LeisureProviderData> m_LeisureProviderDatas`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.LeisureProviderData> m_LeisureProviderDatas;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDatas`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDatas;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.SchoolData> m_SchoolDatas`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.SchoolData> m_SchoolDatas;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_PrefabBuildingDatas`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_PrefabBuildingDatas;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_BuildingProperties`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_BuildingProperties;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableDatas`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableDatas;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.Locked> m_Lockeds`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.Locked> m_Lockeds;
```

- `private Unity.Entities.BufferLookup<Game.Economy.Resources> m_Resources`  

```csharp
private Unity.Entities.BufferLookup<Game.Economy.Resources> m_Resources;
```

- `private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts`  

```csharp
private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts;
```

- `private Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> m_Availabilities`  

```csharp
private Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> m_Availabilities;
```

- `private Unity.Entities.BufferLookup<Game.Net.ServiceCoverage> m_ServiceCoverages`  

```csharp
private Unity.Entities.BufferLookup<Game.Net.ServiceCoverage> m_ServiceCoverages;
```

- `private Unity.Entities.BufferLookup<Game.Buildings.Renter> m_Renters`  

```csharp
private Unity.Entities.BufferLookup<Game.Buildings.Renter> m_Renters;
```

- `private Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifiers`  

```csharp
private Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifiers;
```

- `private Unity.Entities.BufferLookup<Game.Vehicles.OwnedVehicle> m_OwnedVehicles`  

```csharp
private Unity.Entities.BufferLookup<Game.Vehicles.OwnedVehicle> m_OwnedVehicles;
```


## Constructors

- `public CitizenPathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

```csharp
public CitizenPathfindSetup(PathfindSetupSystem system)
	{
		m_LeisureProviderQuery = system.GetSetupQuery(ComponentType.ReadOnly<Game.Buildings.LeisureProvider>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>());
		m_TouristTargetQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			All = new ComponentType[0],
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<LodgingProvider>(),
				ComponentType.ReadOnly<AttractivenessProvider>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_SchoolQuery = system.GetSetupQuery(ComponentType.ReadOnly<Game.Buildings.School>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Game.Buildings.ServiceUpgrade>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Temp>());
		m_FreeWorkplaceQuery = system.GetSetupQuery(ComponentType.ReadOnly<FreeWorkplaces>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Temp>());
		m_AttractionQuery = system.GetSetupQuery(ComponentType.ReadOnly<Building>(), ComponentType.ReadOnly<AttractivenessProvider>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Temp>());
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
		m_HomelessShelterQuery = system.GetSetupQuery(entityQueryDesc);
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
		m_FindHomeQuery = system.GetSetupQuery(entityQueryDesc, entityQueryDesc2);
		m_GroundPollutionSystem = system.World.GetOrCreateSystemManaged<GroundPollutionSystem>();
		m_AirPollutionSystem = system.World.GetOrCreateSystemManaged<AirPollutionSystem>();
		m_NoisePollutionSystem = system.World.GetOrCreateSystemManaged<NoisePollutionSystem>();
		m_TelecomCoverageSystem = system.World.GetOrCreateSystemManaged<TelecomCoverageSystem>();
		m_CitySystem = system.World.GetOrCreateSystemManaged<CitySystem>();
		m_ResourceSystem = system.World.GetOrCreateSystemManaged<ResourceSystem>();
		m_LeisureSystem = system.World.GetOrCreateSystemManaged<LeisureSystem>();
		m_TaxSystem = system.World.GetOrCreateSystemManaged<TaxSystem>();
		m_EconomyParameterQuery = system.GetSetupQuery(ComponentType.ReadOnly<EconomyParameterData>());
		m_HealthcareParameterQuery = system.GetSetupQuery(ComponentType.ReadOnly<HealthcareParameterData>());
		m_ParkParameterQuery = system.GetSetupQuery(ComponentType.ReadOnly<ParkParameterData>());
		m_EducationParameterQuery = system.GetSetupQuery(ComponentType.ReadOnly<EducationParameterData>());
		m_TelecomParameterQuery = system.GetSetupQuery(ComponentType.ReadOnly<TelecomParameterData>());
		m_GarbageParameterQuery = system.GetSetupQuery(ComponentType.ReadOnly<GarbageParameterData>());
		m_PoliceParameterQuery = system.GetSetupQuery(ComponentType.ReadOnly<PoliceConfigurationData>());
		m_CitizenHappinessParameterQuery = system.GetSetupQuery(ComponentType.ReadOnly<CitizenHappinessParameterData>());
		m_ServiceFeeParameterQuery = system.GetSetupQuery(ComponentType.ReadOnly<ServiceFeeParameterData>());
		m_EntityType = system.GetEntityTypeHandle();
		m_ServiceAvailableType = system.GetComponentTypeHandle<ServiceAvailable>(isReadOnly: true);
		m_FreeWorkplaceType = system.GetComponentTypeHandle<FreeWorkplaces>(isReadOnly: true);
		m_WorkProviderType = system.GetComponentTypeHandle<WorkProvider>(isReadOnly: true);
		m_CityServiceType = system.GetComponentTypeHandle<CityServiceUpkeep>(isReadOnly: true);
		m_BuildingType = system.GetComponentTypeHandle<Building>(isReadOnly: true);
		m_PrefabRefType = system.GetComponentTypeHandle<PrefabRef>(isReadOnly: true);
		m_RenterType = system.GetBufferTypeHandle<Renter>(isReadOnly: true);
		m_StudentType = system.GetBufferTypeHandle<Game.Buildings.Student>(isReadOnly: true);
		m_UpgradeType = system.GetBufferTypeHandle<InstalledUpgrade>(isReadOnly: true);
		m_Buildings = system.GetComponentLookup<Building>(isReadOnly: true);
		m_Households = system.GetComponentLookup<Household>(isReadOnly: true);
		m_HomelessHouseholds = system.GetComponentLookup<HomelessHousehold>(isReadOnly: true);
		m_OutsideConnections = system.GetComponentLookup<Game.Objects.OutsideConnection>(isReadOnly: true);
		m_ServiceDatas = system.GetComponentLookup<ServiceCompanyData>(isReadOnly: true);
		m_Workers = system.GetComponentLookup<Worker>(isReadOnly: true);
		m_Students = system.GetComponentLookup<Game.Citizens.Student>(isReadOnly: true);
		m_Citizens = system.GetComponentLookup<Citizen>(isReadOnly: true);
		m_TouristHouseholds = system.GetComponentLookup<TouristHousehold>(isReadOnly: true);
		m_HealthProblems = system.GetComponentLookup<HealthProblem>(isReadOnly: true);
		m_Transforms = system.GetComponentLookup<Game.Objects.Transform>(isReadOnly: true);
		m_BuildingDatas = system.GetComponentLookup<Building>(isReadOnly: true);
		m_Efficiencies = system.GetBufferLookup<Efficiency>(isReadOnly: true);
		m_AttractivenessProviders = system.GetComponentLookup<AttractivenessProvider>(isReadOnly: true);
		m_LodgingProviders = system.GetComponentLookup<LodgingProvider>(isReadOnly: true);
		m_PropertiesOnMarket = system.GetComponentLookup<PropertyOnMarket>(isReadOnly: true);
		m_PropertyRenters = system.GetComponentLookup<PropertyRenter>(isReadOnly: true);
		m_Crimes = system.GetComponentLookup<CrimeProducer>(isReadOnly: true);
		m_Parks = system.GetComponentLookup<Game.Buildings.Park>(isReadOnly: true);
		m_Abandoneds = system.GetComponentLookup<Abandoned>(isReadOnly: true);
		m_ElectricityConsumers = system.GetComponentLookup<ElectricityConsumer>(isReadOnly: true);
		m_WaterConsumers = system.GetComponentLookup<WaterConsumer>(isReadOnly: true);
		m_GarbageProducers = system.GetComponentLookup<GarbageProducer>(isReadOnly: true);
		m_MailProducers = system.GetComponentLookup<MailProducer>(isReadOnly: true);
		m_PathInfos = system.GetComponentLookup<PathInformation>(isReadOnly: true);
		m_Prefabs = system.GetComponentLookup<PrefabRef>(isReadOnly: true);
		m_IndustrialProcessDatas = system.GetComponentLookup<IndustrialProcessData>(isReadOnly: true);
		m_LeisureProviderDatas = system.GetComponentLookup<LeisureProviderData>(isReadOnly: true);
		m_ResourceDatas = system.GetComponentLookup<ResourceData>(isReadOnly: true);
		m_SchoolDatas = system.GetComponentLookup<SchoolData>(isReadOnly: true);
		m_PrefabBuildingDatas = system.GetComponentLookup<BuildingData>(isReadOnly: true);
		m_BuildingProperties = system.GetComponentLookup<BuildingPropertyData>(isReadOnly: true);
		m_SpawnableDatas = system.GetComponentLookup<SpawnableBuildingData>(isReadOnly: true);
		m_Lockeds = system.GetComponentLookup<Locked>(isReadOnly: true);
		m_Resources = system.GetBufferLookup<Game.Economy.Resources>(isReadOnly: true);
		m_ServiceDistricts = system.GetBufferLookup<ServiceDistrict>(isReadOnly: true);
		m_Availabilities = system.GetBufferLookup<ResourceAvailability>(isReadOnly: true);
		m_ServiceCoverages = system.GetBufferLookup<Game.Net.ServiceCoverage>(isReadOnly: true);
		m_Renters = system.GetBufferLookup<Renter>(isReadOnly: true);
		m_CityModifiers = system.GetBufferLookup<CityModifier>(isReadOnly: true);
		m_OwnedVehicles = system.GetBufferLookup<OwnedVehicle>(isReadOnly: true);
		m_HouseholdCitizens = system.GetBufferLookup<HouseholdCitizen>(isReadOnly: true);
	}
```


## Methods

- `public SetupAttraction(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupAttraction(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_AttractivenessProviders.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupAttractionJob
		{
			m_EntityType = m_EntityType,
			m_AttractivenessProviders = m_AttractivenessProviders,
			m_SetupData = setupData
		}, m_AttractionQuery, inputDeps);
	}
```

- `public SetupFindHome(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupFindHome(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_RenterType.Update(system);
		m_PrefabRefType.Update(system);
		m_BuildingType.Update(system);
		m_Buildings.Update(system);
		m_Households.Update(system);
		m_HomelessHouseholds.Update(system);
		m_PrefabBuildingDatas.Update(system);
		m_ServiceCoverages.Update(system);
		m_PropertiesOnMarket.Update(system);
		m_Availabilities.Update(system);
		m_SpawnableDatas.Update(system);
		m_BuildingProperties.Update(system);
		m_BuildingDatas.Update(system);
		m_PathInfos.Update(system);
		m_Prefabs.Update(system);
		m_Renters.Update(system);
		m_ServiceCoverages.Update(system);
		m_Workers.Update(system);
		m_Students.Update(system);
		m_PropertyRenters.Update(system);
		m_ResourceDatas.Update(system);
		m_Citizens.Update(system);
		m_Crimes.Update(system);
		m_Lockeds.Update(system);
		m_Transforms.Update(system);
		m_CityModifiers.Update(system);
		m_HealthProblems.Update(system);
		m_HouseholdCitizens.Update(system);
		m_OwnedVehicles.Update(system);
		m_Abandoneds.Update(system);
		m_Parks.Update(system);
		m_ElectricityConsumers.Update(system);
		m_WaterConsumers.Update(system);
		m_GarbageProducers.Update(system);
		m_MailProducers.Update(system);
		m_Resources.Update(system);
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle dependencies3;
		JobHandle dependencies4;
		return JobChunkExtensions.ScheduleParallel(new SetupFindHomeJob
		{
			m_EntityType = m_EntityType,
			m_RenterType = m_RenterType,
			m_PrefabType = m_PrefabRefType,
			m_Buildings = m_Buildings,
			m_Households = m_Households,
			m_HomelessHouseholds = m_HomelessHouseholds,
			m_BuildingDatas = m_PrefabBuildingDatas,
			m_Coverages = m_ServiceCoverages,
			m_PropertiesOnMarket = m_PropertiesOnMarket,
			m_Availabilities = m_Availabilities,
			m_SpawnableDatas = m_SpawnableDatas,
			m_BuildingProperties = m_BuildingProperties,
			m_PrefabRefs = m_Prefabs,
			m_ServiceCoverages = m_ServiceCoverages,
			m_Citizens = m_Citizens,
			m_Crimes = m_Crimes,
			m_Lockeds = m_Lockeds,
			m_Transforms = m_Transforms,
			m_CityModifiers = m_CityModifiers,
			m_HouseholdCitizens = m_HouseholdCitizens,
			m_Abandoneds = m_Abandoneds,
			m_Parks = m_Parks,
			m_ElectricityConsumers = m_ElectricityConsumers,
			m_WaterConsumers = m_WaterConsumers,
			m_GarbageProducers = m_GarbageProducers,
			m_MailProducers = m_MailProducers,
			m_HealthProblems = m_HealthProblems,
			m_Workers = m_Workers,
			m_Students = m_Students,
			m_ResourcesBufs = m_Resources,
			m_TaxRates = m_TaxSystem.GetTaxRates(),
			m_PollutionMap = m_GroundPollutionSystem.GetMap(readOnly: true, out dependencies),
			m_AirPollutionMap = m_AirPollutionSystem.GetMap(readOnly: true, out dependencies2),
			m_NoiseMap = m_NoisePollutionSystem.GetMap(readOnly: true, out dependencies3),
			m_TelecomCoverages = m_TelecomCoverageSystem.GetData(readOnly: true, out dependencies4),
			m_HealthcareParameters = m_HealthcareParameterQuery.GetSingleton<HealthcareParameterData>(),
			m_ParkParameters = m_ParkParameterQuery.GetSingleton<ParkParameterData>(),
			m_EducationParameters = m_EducationParameterQuery.GetSingleton<EducationParameterData>(),
			m_EconomyParameters = m_EconomyParameterQuery.GetSingleton<EconomyParameterData>(),
			m_TelecomParameters = m_TelecomParameterQuery.GetSingleton<TelecomParameterData>(),
			m_GarbageParameters = m_GarbageParameterQuery.GetSingleton<GarbageParameterData>(),
			m_PoliceParameters = m_PoliceParameterQuery.GetSingleton<PoliceConfigurationData>(),
			m_ServiceFeeParameterData = m_ServiceFeeParameterQuery.GetSingleton<ServiceFeeParameterData>(),
			m_CitizenHappinessParameterData = m_CitizenHappinessParameterQuery.GetSingleton<CitizenHappinessParameterData>(),
			m_City = m_CitySystem.City,
			m_SetupData = setupData
		}, m_FindHomeQuery, JobUtils.CombineDependencies(inputDeps, dependencies, dependencies2, dependencies3, dependencies4));
	}
```

- `public SetupHomeless(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupHomeless(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_RenterType.Update(system);
		m_PrefabRefType.Update(system);
		m_BuildingType.Update(system);
		m_PrefabBuildingDatas.Update(system);
		m_ServiceCoverages.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupHomelessJob
		{
			m_EntityType = m_EntityType,
			m_RenterType = m_RenterType,
			m_PrefabType = m_PrefabRefType,
			m_BuildingType = m_BuildingType,
			m_BuildingProperties = m_BuildingProperties,
			m_BuildingDatas = m_PrefabBuildingDatas,
			m_Coverages = m_ServiceCoverages,
			m_SetupData = setupData
		}, m_HomelessShelterQuery, inputDeps);
	}
```

- `public SetupJobSeekerTo(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupJobSeekerTo(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_FreeWorkplaceType.Update(system);
		m_WorkProviderType.Update(system);
		m_CityServiceType.Update(system);
		m_OutsideConnections.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupJobSeekerToJob
		{
			m_EntityType = m_EntityType,
			m_FreeWorkplaceType = m_FreeWorkplaceType,
			m_WorkProviderType = m_WorkProviderType,
			m_CityServiceType = m_CityServiceType,
			m_OutsideConnections = m_OutsideConnections,
			m_SetupData = setupData
		}, m_FreeWorkplaceQuery, inputDeps);
	}
```

- `public SetupLeisureTarget(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupLeisureTarget(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_ServiceAvailableType.Update(system);
		m_PrefabRefType.Update(system);
		m_LeisureProviderDatas.Update(system);
		m_Resources.Update(system);
		m_IndustrialProcessDatas.Update(system);
		m_ResourceDatas.Update(system);
		m_ServiceDatas.Update(system);
		m_BuildingDatas.Update(system);
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new SetupLeisureTargetJob
		{
			m_EntityType = m_EntityType,
			m_ServiceAvailableType = m_ServiceAvailableType,
			m_PrefabType = m_PrefabRefType,
			m_LeisureProviderDatas = m_LeisureProviderDatas,
			m_Resources = m_Resources,
			m_IndustrialProcessDatas = m_IndustrialProcessDatas,
			m_ResourceDatas = m_ResourceDatas,
			m_ServiceDatas = m_ServiceDatas,
			m_BuildingDatas = m_BuildingDatas,
			m_ResourcePrefabs = m_ResourceSystem.GetPrefabs(),
			m_SetupData = setupData,
			m_LeisureSystemUpdateInterval = m_LeisureSystem.GetUpdateInterval(SystemUpdatePhase.GameSimulation)
		}, m_LeisureProviderQuery, inputDeps);
		m_ResourceSystem.AddPrefabsReader(jobHandle);
		return jobHandle;
	}
```

- `public SetupSchoolSeekerTo(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupSchoolSeekerTo(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_PrefabRefType.Update(system);
		m_StudentType.Update(system);
		m_UpgradeType.Update(system);
		m_SchoolDatas.Update(system);
		m_Efficiencies.Update(system);
		m_ServiceDistricts.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupSchoolSeekerToJob
		{
			m_EntityType = m_EntityType,
			m_PrefabRefType = m_PrefabRefType,
			m_StudentType = m_StudentType,
			m_UpgradeType = m_UpgradeType,
			m_SchoolDatas = m_SchoolDatas,
			m_Efficiencies = m_Efficiencies,
			m_ServiceDistricts = m_ServiceDistricts,
			m_SetupData = setupData
		}, m_SchoolQuery, inputDeps);
	}
```

- `public SetupTouristTarget(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupTouristTarget(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_TouristHouseholds.Update(system);
		m_LodgingProviders.Update(system);
		m_PropertyRenters.Update(system);
		m_BuildingDatas.Update(system);
		m_Availabilities.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupTouristTargetJob
		{
			m_EntityType = m_EntityType,
			m_LodgingProviders = m_LodgingProviders,
			m_TouristHouseholds = m_TouristHouseholds,
			m_PropertyRenters = m_PropertyRenters,
			m_BuildingDatas = m_BuildingDatas,
			m_ResourceAvailabilityBufs = m_Availabilities,
			m_SetupData = setupData
		}, m_TouristTargetQuery, inputDeps);
	}
```


## Nested types

- `Game.Simulation.CitizenPathfindSetup+SetupTouristTargetJob`  
- `Game.Simulation.CitizenPathfindSetup+SetupLeisureTargetJob`  
- `Game.Simulation.CitizenPathfindSetup+SetupSchoolSeekerToJob`  
- `Game.Simulation.CitizenPathfindSetup+SetupJobSeekerToJob`  
- `Game.Simulation.CitizenPathfindSetup+SetupAttractionJob`  
- `Game.Simulation.CitizenPathfindSetup+SetupHomelessJob`  
- `Game.Simulation.CitizenPathfindSetup+SetupFindHomeJob`  

