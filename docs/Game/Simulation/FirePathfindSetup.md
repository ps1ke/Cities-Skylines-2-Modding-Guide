# Game.Simulation.FirePathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Entities.EntityQuery m_FireEngineQuery`  
- `private Unity.Entities.EntityQuery m_EmergencyShelterQuery`  
- `private Unity.Entities.EntityQuery m_EvacuationTransportQuery`  
- `private Unity.Entities.EntityQuery m_EvacuationRequestQuery`  
- `private Unity.Entities.EntityQuery m_FireRescueRequestQuery`  
- `private Unity.Entities.EntityTypeHandle m_EntityType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathOwner> m_PathOwnerType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.FireRescueRequest> m_FireRescueRequestType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.EvacuationRequest> m_EvacuationRequestType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.FireStation> m_FireStationType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.EmergencyShelter> m_EmergencyShelterType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.FireEngine> m_FireEngineType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.PublicTransport> m_PublicTransportType`  
- `private Unity.Entities.BufferTypeHandle<Game.Pathfind.PathElement> m_PathElementType`  
- `private Unity.Entities.BufferTypeHandle<Game.Simulation.ServiceDispatch> m_ServiceDispatchType`  
- `private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformationData`  
- `private Unity.Entities.ComponentLookup<Game.Simulation.FireRescueRequest> m_FireRescueRequestData`  
- `private Unity.Entities.ComponentLookup<Game.Simulation.EvacuationRequest> m_EvacuationRequestData`  
- `private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections`  
- `private Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData`  
- `private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData`  
- `private Unity.Entities.ComponentLookup<Game.Areas.District> m_DistrictData`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.FireStation> m_FireStationData`  
- `private Unity.Entities.ComponentLookup<Game.Vehicles.FireEngine> m_FireEngineData`  
- `private Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransportData`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData`  
- `private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements`  
- `private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts`  
- `private Unity.Entities.ComponentLookup<Game.City.City> m_CityData`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  

## Constructors

- `public FirePathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

## Methods

- `public SetupEmergencyShelters(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupEvacuationRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupEvacuationTransport(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupFireEngines(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupFireRescueRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Simulation.FirePathfindSetup+SetupFireEnginesJob`  
- `Game.Simulation.FirePathfindSetup+SetupEmergencySheltersJob`  
- `Game.Simulation.FirePathfindSetup+SetupEvacuationTransportJob`  
- `Game.Simulation.FirePathfindSetup+EvacuationRequestsJob`  
- `Game.Simulation.FirePathfindSetup+FireRescueRequestsJob`  

