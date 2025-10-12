# Game.Simulation.GarbagePathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Entities.EntityQuery m_GarbageCollectorQuery`  
- `private Unity.Entities.EntityQuery m_GarbageTransferQuery`  
- `private Unity.Entities.EntityQuery m_GarbageCollectionRequestQuery`  
- `private Unity.Entities.EntityTypeHandle m_EntityType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathOwner> m_PathOwnerType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnectionType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.GarbageCollectionRequest> m_GarbageCollectionRequestType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.GarbageFacility> m_GarbageFacilityType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.GarbageTruck> m_GarbageTruckType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  
- `private Unity.Entities.BufferTypeHandle<Game.Pathfind.PathElement> m_PathElementType`  
- `private Unity.Entities.BufferTypeHandle<Game.Simulation.ServiceDispatch> m_ServiceDispatchType`  
- `private Unity.Entities.BufferTypeHandle<Game.Economy.Resources> m_ResourcesType`  
- `private Unity.Entities.BufferTypeHandle<Game.Companies.TradeCost> m_TradeCostType`  
- `private Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType`  
- `private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformationData`  
- `private Unity.Entities.ComponentLookup<Game.Simulation.GarbageCollectionRequest> m_GarbageCollectionRequestData`  
- `private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections`  
- `private Unity.Entities.ComponentLookup<Game.City.City> m_CityData`  
- `private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData`  
- `private Unity.Entities.ComponentLookup<Game.Vehicles.GarbageTruck> m_GarbageTruckData`  
- `private Unity.Entities.ComponentLookup<Game.Companies.StorageLimitData> m_StorageLimitData`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.StorageCompanyData> m_StorageCompanyData`  
- `private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements`  
- `private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts`  
- `private Game.Simulation.CitySystem m_CitySystem`  

## Constructors

- `public GarbagePathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

## Methods

- `public SetupGarbageCollector(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupGarbageCollectorRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupGarbageTransfer(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Simulation.GarbagePathfindSetup+SetupGarbageCollectorsJob`  
- `Game.Simulation.GarbagePathfindSetup+SetupGarbageTransferJob`  
- `Game.Simulation.GarbagePathfindSetup+GarbageCollectorRequestsJob`  

