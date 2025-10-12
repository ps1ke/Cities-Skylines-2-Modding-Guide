# Game.Simulation.PostServicePathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Entities.EntityQuery m_PostVanQuery`  
- `private Unity.Entities.EntityQuery m_MailTransferQuery`  
- `private Unity.Entities.EntityQuery m_MailBoxQuery`  
- `private Unity.Entities.EntityQuery m_PostVanRequestQuery`  
- `private Unity.Entities.EntityTypeHandle m_EntityType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathOwner> m_PathOwnerType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnectionType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.PostVanRequest> m_PostVanRequestType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.PostFacility> m_PostFacilityType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.PostVan> m_PostVanType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Routes.MailBox> m_MailBoxType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Routes.TransportStop> m_TransportStopType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  
- `private Unity.Entities.BufferTypeHandle<Game.Pathfind.PathElement> m_PathElementType`  
- `private Unity.Entities.BufferTypeHandle<Game.Simulation.ServiceDispatch> m_ServiceDispatchType`  
- `private Unity.Entities.BufferTypeHandle<Game.Economy.Resources> m_ResourcesType`  
- `private Unity.Entities.BufferTypeHandle<Game.Companies.TradeCost> m_TradeCostType`  
- `private Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType`  
- `private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformationData`  
- `private Unity.Entities.ComponentLookup<Game.Simulation.PostVanRequest> m_PostVanRequestData`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.PostFacility> m_PostFacilityData`  
- `private Unity.Entities.ComponentLookup<Game.Vehicles.PostVan> m_PostVanData`  
- `private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData`  
- `private Unity.Entities.ComponentLookup<Game.Companies.StorageLimitData> m_StorageLimitData`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.StorageCompanyData> m_StorageCompanyData`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.MailBoxData> m_MailBoxData`  
- `private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements`  
- `private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts`  

## Constructors

- `public PostServicePathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

## Methods

- `public SetupMailBoxes(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupMailTransfer(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupPostVanRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupPostVans(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Simulation.PostServicePathfindSetup+SetupPostVansJob`  
- `Game.Simulation.PostServicePathfindSetup+SetupMailTransferJob`  
- `Game.Simulation.PostServicePathfindSetup+SetupMailBoxesJob`  
- `Game.Simulation.PostServicePathfindSetup+PostVanRequestsJob`  

