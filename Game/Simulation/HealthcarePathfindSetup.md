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
public HealthcarePathfindSetup(PathfindSetupSystem system)
	{
		m_AmbulanceQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Hospital>(),
				ComponentType.ReadOnly<Ambulance>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<ServiceUpgrade>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_HospitalQuery = system.GetSetupQuery(ComponentType.ReadOnly<Hospital>(), ComponentType.ReadOnly<ServiceDispatch>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Deleted>());
		m_HearseQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<DeathcareFacility>(),
				ComponentType.ReadOnly<Hearse>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<ServiceUpgrade>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_HealthcareRequestQuery = system.GetSetupQuery(ComponentType.ReadOnly<HealthcareRequest>(), ComponentType.Exclude<Dispatched>(), ComponentType.Exclude<PathInformation>());
		m_EntityType = system.GetEntityTypeHandle();
		m_OwnerType = system.GetComponentTypeHandle<Owner>(isReadOnly: true);
		m_PathOwnerType = system.GetComponentTypeHandle<PathOwner>(isReadOnly: true);
		m_ServiceRequestType = system.GetComponentTypeHandle<ServiceRequest>(isReadOnly: true);
		m_HealthcareRequestType = system.GetComponentTypeHandle<HealthcareRequest>(isReadOnly: true);
		m_HospitalType = system.GetComponentTypeHandle<Hospital>(isReadOnly: true);
		m_DeathcareFacilityType = system.GetComponentTypeHandle<DeathcareFacility>(isReadOnly: true);
		m_HearseType = system.GetComponentTypeHandle<Hearse>(isReadOnly: true);
		m_AmbulanceType = system.GetComponentTypeHandle<Ambulance>(isReadOnly: true);
		m_HealthcareRequestData = system.GetComponentLookup<HealthcareRequest>(isReadOnly: true);
		m_CurrentDistrictData = system.GetComponentLookup<CurrentDistrict>(isReadOnly: true);
		m_DistrictData = system.GetComponentLookup<District>(isReadOnly: true);
		m_CitizenData = system.GetComponentLookup<Citizen>(isReadOnly: true);
		m_HealthProblemData = system.GetComponentLookup<HealthProblem>(isReadOnly: true);
		m_VehicleData = system.GetComponentLookup<Vehicle>(isReadOnly: true);
		m_AmbulanceData = system.GetComponentLookup<Ambulance>(isReadOnly: true);
		m_ServiceDistricts = system.GetBufferLookup<ServiceDistrict>(isReadOnly: true);
		m_CityData = system.GetComponentLookup<Game.City.City>(isReadOnly: true);
		m_AreaSearchSystem = system.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_CitySystem = system.World.GetOrCreateSystemManaged<CitySystem>();
	}
```


## Methods

- `public SetupAmbulances(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupAmbulances(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_HospitalType.Update(system);
		m_AmbulanceType.Update(system);
		m_OwnerType.Update(system);
		m_PathOwnerType.Update(system);
		m_ServiceDistricts.Update(system);
		m_CityData.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupAmbulancesJob
		{
			m_EntityType = m_EntityType,
			m_HospitalType = m_HospitalType,
			m_AmbulanceType = m_AmbulanceType,
			m_OwnerType = m_OwnerType,
			m_PathOwnerType = m_PathOwnerType,
			m_ServiceDistricts = m_ServiceDistricts,
			m_CityData = m_CityData,
			m_City = m_CitySystem.City,
			m_SetupData = setupData
		}, m_AmbulanceQuery, inputDeps);
	}
```

- `public SetupHealthcareRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupHealthcareRequest(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_ServiceRequestType.Update(system);
		m_HealthcareRequestType.Update(system);
		m_HealthcareRequestData.Update(system);
		m_CurrentDistrictData.Update(system);
		m_DistrictData.Update(system);
		m_VehicleData.Update(system);
		m_ServiceDistricts.Update(system);
		JobHandle dependencies;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new HealthcareRequestsJob
		{
			m_EntityType = m_EntityType,
			m_ServiceRequestType = m_ServiceRequestType,
			m_HealthcareRequestType = m_HealthcareRequestType,
			m_HealthcareRequestData = m_HealthcareRequestData,
			m_CurrentDistrictData = m_CurrentDistrictData,
			m_DistrictData = m_DistrictData,
			m_VehicleData = m_VehicleData,
			m_ServiceDistricts = m_ServiceDistricts,
			m_AreaTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies),
			m_SetupData = setupData
		}, m_HealthcareRequestQuery, JobHandle.CombineDependencies(inputDeps, dependencies));
		m_AreaSearchSystem.AddSearchTreeReader(jobHandle);
		return jobHandle;
	}
```

- `public SetupHearses(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupHearses(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_DeathcareFacilityType.Update(system);
		m_HearseType.Update(system);
		m_OwnerType.Update(system);
		m_PathOwnerType.Update(system);
		m_ServiceDistricts.Update(system);
		m_CityData.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupHearsesJob
		{
			m_EntityType = m_EntityType,
			m_DeathcareFacilityType = m_DeathcareFacilityType,
			m_HearseType = m_HearseType,
			m_CityData = m_CityData,
			m_OwnerType = m_OwnerType,
			m_PathOwnerType = m_PathOwnerType,
			m_ServiceDistricts = m_ServiceDistricts,
			m_SetupData = setupData,
			m_City = m_CitySystem.City
		}, m_HearseQuery, inputDeps);
	}
```

- `public SetupHospitals(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupHospitals(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_HospitalType.Update(system);
		m_CitizenData.Update(system);
		m_HealthProblemData.Update(system);
		m_AmbulanceData.Update(system);
		m_ServiceDistricts.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupHospitalsJob
		{
			m_EntityType = m_EntityType,
			m_HospitalType = m_HospitalType,
			m_CitizenData = m_CitizenData,
			m_HealthProblemData = m_HealthProblemData,
			m_AmbulanceData = m_AmbulanceData,
			m_ServiceDistricts = m_ServiceDistricts,
			m_SetupData = setupData
		}, m_HospitalQuery, inputDeps);
	}
```


## Nested types

- `Game.Simulation.HealthcarePathfindSetup+SetupAmbulancesJob`  
- `Game.Simulation.HealthcarePathfindSetup+SetupHospitalsJob`  
- `Game.Simulation.HealthcarePathfindSetup+SetupHearsesJob`  
- `Game.Simulation.HealthcarePathfindSetup+HealthcareRequestsJob`  

