# Game.Simulation.HealthcarePathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct HealthcarePathfindSetup
{
    private Unity.Entities.EntityQuery m_AmbulanceQuery;
    private Unity.Entities.EntityQuery m_HospitalQuery;
    private Unity.Entities.EntityQuery m_HearseQuery;
    private Unity.Entities.EntityQuery m_HealthcareRequestQuery;
    private Unity.Entities.EntityTypeHandle m_EntityType;
    private Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
    private Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathOwner> m_PathOwnerType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.HealthcareRequest> m_HealthcareRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Buildings.Hospital> m_HospitalType;
    private Unity.Entities.ComponentTypeHandle<Game.Buildings.DeathcareFacility> m_DeathcareFacilityType;
    private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Hearse> m_HearseType;
    private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Ambulance> m_AmbulanceType;
    private Unity.Entities.ComponentLookup<Game.Simulation.HealthcareRequest> m_HealthcareRequestData;
    private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData;
    private Unity.Entities.ComponentLookup<Game.Areas.District> m_DistrictData;
    private Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_CitizenData;
    private Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblemData;
    private Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData;
    private Unity.Entities.ComponentLookup<Game.Vehicles.Ambulance> m_AmbulanceData;
    private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts;
    private Unity.Entities.ComponentLookup<Game.City.City> m_CityData;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Simulation.CitySystem m_CitySystem;

    public HealthcarePathfindSetup(Game.Simulation.PathfindSetupSystem system);

    public Unity.Jobs.JobHandle SetupAmbulances(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupHealthcareRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupHearses(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupHospitals(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_AmbulanceQuery`  

```csharp
private Unity.Entities.EntityQuery m_AmbulanceQuery;
```

- `private Unity.Entities.EntityQuery m_HospitalQuery`  

```csharp
private Unity.Entities.EntityQuery m_HospitalQuery;
```

- `private Unity.Entities.EntityQuery m_HearseQuery`  

```csharp
private Unity.Entities.EntityQuery m_HearseQuery;
```

- `private Unity.Entities.EntityQuery m_HealthcareRequestQuery`  

```csharp
private Unity.Entities.EntityQuery m_HealthcareRequestQuery;
```

- `private Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
private Unity.Entities.EntityTypeHandle m_EntityType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathOwner> m_PathOwnerType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathOwner> m_PathOwnerType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.HealthcareRequest> m_HealthcareRequestType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Simulation.HealthcareRequest> m_HealthcareRequestType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.Hospital> m_HospitalType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Buildings.Hospital> m_HospitalType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.DeathcareFacility> m_DeathcareFacilityType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Buildings.DeathcareFacility> m_DeathcareFacilityType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Hearse> m_HearseType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Hearse> m_HearseType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Ambulance> m_AmbulanceType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Ambulance> m_AmbulanceType;
```

- `private Unity.Entities.ComponentLookup<Game.Simulation.HealthcareRequest> m_HealthcareRequestData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Simulation.HealthcareRequest> m_HealthcareRequestData;
```

- `private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData;
```

- `private Unity.Entities.ComponentLookup<Game.Areas.District> m_DistrictData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Areas.District> m_DistrictData;
```

- `private Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_CitizenData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Citizens.Citizen> m_CitizenData;
```

- `private Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblemData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Citizens.HealthProblem> m_HealthProblemData;
```

- `private Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData;
```

- `private Unity.Entities.ComponentLookup<Game.Vehicles.Ambulance> m_AmbulanceData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Vehicles.Ambulance> m_AmbulanceData;
```

- `private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts`  

```csharp
private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts;
```

- `private Unity.Entities.ComponentLookup<Game.City.City> m_CityData`  

```csharp
private Unity.Entities.ComponentLookup<Game.City.City> m_CityData;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```


## Constructors

- `public HealthcarePathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

```csharp
public HealthcarePathfindSetup(Game.Simulation.PathfindSetupSystem system);
```


## Methods

- `public SetupAmbulances(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupAmbulances(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetupHealthcareRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupHealthcareRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetupHearses(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupHearses(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetupHospitals(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupHospitals(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Simulation.HealthcarePathfindSetup+SetupAmbulancesJob`  
- `Game.Simulation.HealthcarePathfindSetup+SetupHospitalsJob`  
- `Game.Simulation.HealthcarePathfindSetup+SetupHearsesJob`  
- `Game.Simulation.HealthcarePathfindSetup+HealthcareRequestsJob`  

