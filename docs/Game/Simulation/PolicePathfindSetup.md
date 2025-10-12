# Game.Simulation.PolicePathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Entities.EntityQuery m_PolicePatrolQuery`  
- `private Unity.Entities.EntityQuery m_CrimeProducerQuery`  
- `private Unity.Entities.EntityQuery m_PrisonerTransportQuery`  
- `private Unity.Entities.EntityQuery m_PrisonerTransportRequestQuery`  
- `private Unity.Entities.EntityQuery m_PoliceRequestQuery`  
- `private Unity.Entities.EntityTypeHandle m_EntityType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathOwner> m_PathOwnerType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.PrisonerTransportRequest> m_PrisonerTransportRequestType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.PolicePatrolRequest> m_PolicePatrolRequestType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.PoliceEmergencyRequest> m_PoliceEmergencyRequestType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.PoliceStation> m_PoliceStationType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.CrimeProducer> m_CrimeProducerType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.Prison> m_PrisonType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.PoliceCar> m_PoliceCarType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Helicopter> m_HelicopterType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.PublicTransport> m_PublicTransportType`  
- `private Unity.Entities.BufferTypeHandle<Game.Pathfind.PathElement> m_PathElementType`  
- `private Unity.Entities.BufferTypeHandle<Game.Simulation.ServiceDispatch> m_ServiceDispatchType`  
- `private Unity.Entities.BufferTypeHandle<Game.Vehicles.Passenger> m_PassengerType`  
- `private Unity.Entities.BufferTypeHandle<Game.Buildings.Renter> m_RenterType`  
- `private Unity.Entities.BufferTypeHandle<Game.Companies.Employee> m_EmployeeType`  
- `private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformationData`  
- `private Unity.Entities.ComponentLookup<Game.Simulation.PolicePatrolRequest> m_PolicePatrolRequestData`  
- `private Unity.Entities.ComponentLookup<Game.Simulation.PoliceEmergencyRequest> m_PoliceEmergencyRequestData`  
- `private Unity.Entities.ComponentLookup<Game.Simulation.PrisonerTransportRequest> m_PrisonerTransportRequestData`  
- `private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections`  
- `private Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData`  
- `private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData`  
- `private Unity.Entities.ComponentLookup<Game.Areas.District> m_DistrictData`  
- `private Unity.Entities.ComponentLookup<Game.Buildings.PoliceStation> m_PoliceStationData`  
- `private Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData`  
- `private Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData`  
- `private Unity.Entities.ComponentLookup<Game.Vehicles.PoliceCar> m_PoliceCarData`  
- `private Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransportData`  
- `private Unity.Entities.ComponentLookup<Game.Events.AccidentSite> m_AccidentSiteData`  
- `private Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData`  
- `private Unity.Entities.ComponentLookup<Game.City.City> m_CityData`  
- `private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements`  
- `private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts`  
- `private Unity.Entities.BufferLookup<Game.Events.TargetElement> m_TargetElements`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  

## Constructors

- `public PolicePathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

## Methods

- `public SetupCrimeProducer(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupPolicePatrols(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupPoliceRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupPrisonerTransport(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupPrisonerTransportRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Simulation.PolicePathfindSetup+SetupPolicePatrolsJob`  
- `Game.Simulation.PolicePathfindSetup+SetupCrimeProducersJob`  
- `Game.Simulation.PolicePathfindSetup+SetupPrisonerTransportJob`  
- `Game.Simulation.PolicePathfindSetup+PrisonerTransportRequestsJob`  
- `Game.Simulation.PolicePathfindSetup+PoliceRequestsJob`  

