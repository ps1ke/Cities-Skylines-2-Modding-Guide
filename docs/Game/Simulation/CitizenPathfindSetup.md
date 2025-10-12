# Game.Simulation.CitizenPathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Entities.EntityQuery m_LeisureProviderQuery`  
- `private Unity.Entities.EntityQuery m_TouristTargetQuery`  
- `private Unity.Entities.EntityQuery m_SchoolQuery`  
- `private Unity.Entities.EntityQuery m_FreeWorkplaceQuery`  
- `private Unity.Entities.EntityQuery m_AttractionQuery`  
- `private Unity.Entities.EntityQuery m_HomelessShelterQuery`  
- `private Unity.Entities.EntityQuery m_FindHomeQuery`  
- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  
- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  
- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  
- `private Game.Simulation.TelecomCoverageSystem m_TelecomCoverageSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.LeisureSystem m_LeisureSystem`  
- `private Game.Simulation.TaxSystem m_TaxSystem`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityQuery m_HealthcareParameterQuery`  
- `private Unity.Entities.EntityQuery m_ParkParameterQuery`  
- `private Unity.Entities.EntityQuery m_EducationParameterQuery`  
- `private Unity.Entities.EntityQuery m_TelecomParameterQuery`  
- `private Unity.Entities.EntityQuery m_GarbageParameterQuery`  
- `private Unity.Entities.EntityQuery m_PoliceParameterQuery`  
- `private Unity.Entities.EntityQuery m_CitizenHappinessParameterQuery`  
- `private Unity.Entities.EntityQuery m_ServiceFeeParameterQuery`  
- `private Unity.Entities.EntityTypeHandle m_EntityType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Companies.ServiceAvailable> m_ServiceAvailableType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Companies.FreeWorkplaces> m_FreeWorkplaceType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Companies.WorkProvider> m_WorkProviderType`  
- `private Unity.Entities.ComponentTypeHandle<Game.City.CityServiceUpkeep> m_CityServiceType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.Building> m_BuildingType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  
- `private Unity.Entities.BufferTypeHandle<Game.Buildings.Renter> m_RenterType`  
- `private Unity.Entities.BufferTypeHandle<Game.Buildings.Student> m_StudentType`  
- `private Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_UpgradeType`  
- `private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections`  
- `private Unity.Entities.ComponentLookup<Game.Companies.ServiceCompanyData> m_ServiceDatas`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Buildings`  
- `private Unity.Entities.ComponentLookup<Game.Citizens.Household> m_Households`  
- `private Unity.Entities.ComponentLookup<Game.Citizens.HomelessHousehold> m_HomelessHouseholds`  
- `private Unity.Entities.ComponentLookup<Game.Citizens.Worker> m_Workers`  
- `private Unity.Entities.ComponentLookup<Game.Citizens.Student> m_Students`  
- `private Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_Citizens`  
- `private Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblems`  
- `private Unity.Entities.ComponentLookup<Game.Citizens.TouristHousehold> m_TouristHouseholds`  
- `private Unity.Entities.BufferLookup<Game.Citizens.HouseholdCitizen> m_HouseholdCitizens`  
- `private Unity.Entities.ComponentLookup<Game.Objects.Transform> m_Transforms`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.Building> m_BuildingDatas`  
- `private Unity.Entities.BufferLookup<Game.Buildings.Efficiency> m_Efficiencies`  
- `private Unity.Entities.ComponentLookup<Game.Companies.LodgingProvider> m_LodgingProviders`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.AttractivenessProvider> m_AttractivenessProviders`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.PropertyOnMarket> m_PropertiesOnMarket`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.CrimeProducer> m_Crimes`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.Park> m_Parks`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.Abandoned> m_Abandoneds`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.ElectricityConsumer> m_ElectricityConsumers`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.WaterConsumer> m_WaterConsumers`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.GarbageProducer> m_GarbageProducers`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.MailProducer> m_MailProducers`  
- `private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInfos`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_IndustrialProcessDatas`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.LeisureProviderData> m_LeisureProviderDatas`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDatas`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.SchoolData> m_SchoolDatas`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_PrefabBuildingDatas`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.BuildingPropertyData> m_BuildingProperties`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableDatas`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.Locked> m_Lockeds`  
- `private Unity.Entities.BufferLookup<Game.Economy.Resources> m_Resources`  
- `private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts`  
- `private Unity.Entities.BufferLookup<Game.Net.ResourceAvailability> m_Availabilities`  
- `private Unity.Entities.BufferLookup<Game.Net.ServiceCoverage> m_ServiceCoverages`  
- `private Unity.Entities.BufferLookup<Game.Buildings.Renter> m_Renters`  
- `private Unity.Entities.BufferLookup<Game.City.CityModifier> m_CityModifiers`  
- `private Unity.Entities.BufferLookup<Game.Vehicles.OwnedVehicle> m_OwnedVehicles`  

## Constructors

- `public CitizenPathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

## Methods

- `public SetupAttraction(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupFindHome(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupHomeless(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupJobSeekerTo(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupLeisureTarget(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupSchoolSeekerTo(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupTouristTarget(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Simulation.CitizenPathfindSetup+SetupTouristTargetJob`  
- `Game.Simulation.CitizenPathfindSetup+SetupLeisureTargetJob`  
- `Game.Simulation.CitizenPathfindSetup+SetupSchoolSeekerToJob`  
- `Game.Simulation.CitizenPathfindSetup+SetupJobSeekerToJob`  
- `Game.Simulation.CitizenPathfindSetup+SetupAttractionJob`  
- `Game.Simulation.CitizenPathfindSetup+SetupHomelessJob`  
- `Game.Simulation.CitizenPathfindSetup+SetupFindHomeJob`  

