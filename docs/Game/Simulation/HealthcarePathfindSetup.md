# Game.Simulation.HealthcarePathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `private Unity.Entities.EntityQuery m_AmbulanceQuery`  
- `private Unity.Entities.EntityQuery m_HospitalQuery`  
- `private Unity.Entities.EntityQuery m_HearseQuery`  
- `private Unity.Entities.EntityQuery m_HealthcareRequestQuery`  
- `private Unity.Entities.EntityTypeHandle m_EntityType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathOwner> m_PathOwnerType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.HealthcareRequest> m_HealthcareRequestType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.Hospital> m_HospitalType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.DeathcareFacility> m_DeathcareFacilityType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Hearse> m_HearseType`  
- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Ambulance> m_AmbulanceType`  
- `private Unity.Entities.ComponentLookup<Game.Simulation.HealthcareRequest> m_HealthcareRequestData`  
- `private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData`  
- `private Unity.Entities.ComponentLookup<Game.Areas.District> m_DistrictData`  
- `private Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_CitizenData`  
- `private Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblemData`  
- `private Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData`  
- `private Unity.Entities.ComponentLookup<Game.Vehicles.Ambulance> m_AmbulanceData`  
- `private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts`  
- `private Unity.Entities.ComponentLookup<Game.City.City> m_CityData`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  

## Constructors

- `public HealthcarePathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

## Methods

- `public SetupAmbulances(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupHealthcareRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupHearses(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  
- `public SetupHospitals(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

## Nested types

- `Game.Simulation.HealthcarePathfindSetup+SetupAmbulancesJob`  
- `Game.Simulation.HealthcarePathfindSetup+SetupHospitalsJob`  
- `Game.Simulation.HealthcarePathfindSetup+SetupHearsesJob`  
- `Game.Simulation.HealthcarePathfindSetup+HealthcareRequestsJob`  

