# Game.Simulation.ResourcePathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Entities.EntityQuery m_ResourceSellerQuery`  
- `private Unity.Entities.EntityQuery m_ExportTargetQuery`  
- `private Unity.Entities.EntityQuery m_StorageQuery`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Unity.Entities.EntityTypeHandle m_EntityType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnectionType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Companies.StorageCompany> m_StorageCompanyType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabType`  
- `private Unity.Entities.BufferTypeHandle<Game.Companies.TradeCost> m_TradeCostType`  
- `private Unity.Entities.BufferTypeHandle<Game.Companies.StorageTransferRequest> m_StorageTransferRequestType`  
- `private Unity.Entities.BufferTypeHandle<Game.Economy.Resources> m_ResourceType`  
- `private Unity.Entities.BufferTypeHandle<Game.Vehicles.OwnedVehicle> m_OwnedVehicleType`  
- `private Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType`  
- `private Unity.Entities.BufferTypeHandle<Game.Citizens.TripNeeded> m_TripNeededType`  
- `private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections`  
- `private Unity.Entities.ComponentLookup<Game.Companies.ServiceCompanyData> m_ServiceCompanies`  
- `private Unity.Entities.ComponentLookup<Game.Companies.ServiceAvailable> m_ServiceAvailables`  
- `private Unity.Entities.ComponentLookup<Game.Companies.StorageCompany> m_StorageCompanys`  
- `private Unity.Entities.ComponentLookup<Game.Companies.StorageLimitData> m_StorageLimits`  
- `private Unity.Entities.ComponentLookup<Game.Companies.TransportCompanyData> m_TransportCompanyData`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.CargoTransportStation> m_CargoTransportStations`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_IndustrialProcessDatas`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDatas`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.StorageCompanyData> m_StorageCompanyDatas`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableBuildingDatas`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_BuildingDatas`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Buildings`  
- `private Unity.Entities.ComponentLookup<Game.Vehicles.DeliveryTruck> m_DeliveryTrucks`  
- `private Unity.Entities.BufferLookup<Game.Economy.Resources> m_Resources`  
- `private Unity.Entities.BufferLookup<Game.Companies.TradeCost> m_TradeCosts`  
- `private Unity.Entities.BufferLookup<Game.Vehicles.GuestVehicle> m_GuestVehicleBufs`  
- `private Unity.Entities.BufferLookup<Game.Vehicles.LayoutElement> m_LayoutElementBufs`  
- `public static readonly System.Single kOutsideConnectionAmountBasedPenalty`  
- `public static readonly System.Single kCargoStationAmountBasedPenalty`  
- `public static readonly System.Single kCargoStationPerRequestPenalty`  
- `public static readonly System.Int32 kCargoStationVehiclePenalty`  
- `public static readonly System.Int32 kCargoStationMaxRequestAmount`  
- `public static readonly System.Int32 kCargoStationMaxTripNeededQueue`  

## Constructors

- `public ResourcePathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

## Methods

- `public SetupResourceExport(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupResourceSeller(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupStorageTransfer(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Simulation.ResourcePathfindSetup+SetupResourceSellerJob`  
- `Game.Simulation.ResourcePathfindSetup+SetupResourceExportJob`  
- `Game.Simulation.ResourcePathfindSetup+SetupStorageTransferJob`  

