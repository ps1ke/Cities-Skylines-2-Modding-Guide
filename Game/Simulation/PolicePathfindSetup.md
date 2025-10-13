# Game.Simulation.PolicePathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct PolicePathfindSetup
{
    private Unity.Entities.EntityQuery m_PolicePatrolQuery;
    private Unity.Entities.EntityQuery m_CrimeProducerQuery;
    private Unity.Entities.EntityQuery m_PrisonerTransportQuery;
    private Unity.Entities.EntityQuery m_PrisonerTransportRequestQuery;
    private Unity.Entities.EntityQuery m_PoliceRequestQuery;
    private Unity.Entities.EntityTypeHandle m_EntityType;
    private Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathOwner> m_PathOwnerType;
    private Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.PrisonerTransportRequest> m_PrisonerTransportRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.PolicePatrolRequest> m_PolicePatrolRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.PoliceEmergencyRequest> m_PoliceEmergencyRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Buildings.PoliceStation> m_PoliceStationType;
    private Unity.Entities.ComponentTypeHandle<Game.Buildings.CrimeProducer> m_CrimeProducerType;
    private Unity.Entities.ComponentTypeHandle<Game.Buildings.Prison> m_PrisonType;
    private Unity.Entities.ComponentTypeHandle<Game.Vehicles.PoliceCar> m_PoliceCarType;
    private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Helicopter> m_HelicopterType;
    private Unity.Entities.ComponentTypeHandle<Game.Vehicles.PublicTransport> m_PublicTransportType;
    private Unity.Entities.BufferTypeHandle<Game.Pathfind.PathElement> m_PathElementType;
    private Unity.Entities.BufferTypeHandle<Game.Simulation.ServiceDispatch> m_ServiceDispatchType;
    private Unity.Entities.BufferTypeHandle<Game.Vehicles.Passenger> m_PassengerType;
    private Unity.Entities.BufferTypeHandle<Game.Buildings.Renter> m_RenterType;
    private Unity.Entities.BufferTypeHandle<Game.Companies.Employee> m_EmployeeType;
    private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformationData;
    private Unity.Entities.ComponentLookup<Game.Simulation.PolicePatrolRequest> m_PolicePatrolRequestData;
    private Unity.Entities.ComponentLookup<Game.Simulation.PoliceEmergencyRequest> m_PoliceEmergencyRequestData;
    private Unity.Entities.ComponentLookup<Game.Simulation.PrisonerTransportRequest> m_PrisonerTransportRequestData;
    private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections;
    private Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData;
    private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData;
    private Unity.Entities.ComponentLookup<Game.Areas.District> m_DistrictData;
    private Unity.Entities.ComponentLookup<Game.Buildings.PoliceStation> m_PoliceStationData;
    private Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData;
    private Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData;
    private Unity.Entities.ComponentLookup<Game.Vehicles.PoliceCar> m_PoliceCarData;
    private Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransportData;
    private Unity.Entities.ComponentLookup<Game.Events.AccidentSite> m_AccidentSiteData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData;
    private Unity.Entities.ComponentLookup<Game.City.City> m_CityData;
    private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements;
    private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts;
    private Unity.Entities.BufferLookup<Game.Events.TargetElement> m_TargetElements;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Simulation.CitySystem m_CitySystem;

    public PolicePathfindSetup(Game.Simulation.PathfindSetupSystem system);

    public Unity.Jobs.JobHandle SetupCrimeProducer(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupPolicePatrols(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupPoliceRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupPrisonerTransport(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupPrisonerTransportRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PolicePatrolQuery`  

```csharp
private Unity.Entities.EntityQuery m_PolicePatrolQuery;
```

- `private Unity.Entities.EntityQuery m_CrimeProducerQuery`  

```csharp
private Unity.Entities.EntityQuery m_CrimeProducerQuery;
```

- `private Unity.Entities.EntityQuery m_PrisonerTransportQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrisonerTransportQuery;
```

- `private Unity.Entities.EntityQuery m_PrisonerTransportRequestQuery`  

```csharp
private Unity.Entities.EntityQuery m_PrisonerTransportRequestQuery;
```

- `private Unity.Entities.EntityQuery m_PoliceRequestQuery`  

```csharp
private Unity.Entities.EntityQuery m_PoliceRequestQuery;
```

- `private Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
private Unity.Entities.EntityTypeHandle m_EntityType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathOwner> m_PathOwnerType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathOwner> m_PathOwnerType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.PrisonerTransportRequest> m_PrisonerTransportRequestType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Simulation.PrisonerTransportRequest> m_PrisonerTransportRequestType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.PolicePatrolRequest> m_PolicePatrolRequestType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Simulation.PolicePatrolRequest> m_PolicePatrolRequestType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.PoliceEmergencyRequest> m_PoliceEmergencyRequestType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Simulation.PoliceEmergencyRequest> m_PoliceEmergencyRequestType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.PoliceStation> m_PoliceStationType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Buildings.PoliceStation> m_PoliceStationType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.CrimeProducer> m_CrimeProducerType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Buildings.CrimeProducer> m_CrimeProducerType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.Prison> m_PrisonType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Buildings.Prison> m_PrisonType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.PoliceCar> m_PoliceCarType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Vehicles.PoliceCar> m_PoliceCarType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Helicopter> m_HelicopterType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Helicopter> m_HelicopterType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.PublicTransport> m_PublicTransportType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Vehicles.PublicTransport> m_PublicTransportType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Pathfind.PathElement> m_PathElementType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Pathfind.PathElement> m_PathElementType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Simulation.ServiceDispatch> m_ServiceDispatchType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Simulation.ServiceDispatch> m_ServiceDispatchType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Vehicles.Passenger> m_PassengerType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Vehicles.Passenger> m_PassengerType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Buildings.Renter> m_RenterType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Buildings.Renter> m_RenterType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Companies.Employee> m_EmployeeType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Companies.Employee> m_EmployeeType;
```

- `private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformationData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformationData;
```

- `private Unity.Entities.ComponentLookup<Game.Simulation.PolicePatrolRequest> m_PolicePatrolRequestData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Simulation.PolicePatrolRequest> m_PolicePatrolRequestData;
```

- `private Unity.Entities.ComponentLookup<Game.Simulation.PoliceEmergencyRequest> m_PoliceEmergencyRequestData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Simulation.PoliceEmergencyRequest> m_PoliceEmergencyRequestData;
```

- `private Unity.Entities.ComponentLookup<Game.Simulation.PrisonerTransportRequest> m_PrisonerTransportRequestData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Simulation.PrisonerTransportRequest> m_PrisonerTransportRequestData;
```

- `private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections`  

```csharp
private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections;
```

- `private Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData;
```

- `private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData;
```

- `private Unity.Entities.ComponentLookup<Game.Areas.District> m_DistrictData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Areas.District> m_DistrictData;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.PoliceStation> m_PoliceStationData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.PoliceStation> m_PoliceStationData;
```

- `private Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData;
```

- `private Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData;
```

- `private Unity.Entities.ComponentLookup<Game.Vehicles.PoliceCar> m_PoliceCarData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Vehicles.PoliceCar> m_PoliceCarData;
```

- `private Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransportData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransportData;
```

- `private Unity.Entities.ComponentLookup<Game.Events.AccidentSite> m_AccidentSiteData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Events.AccidentSite> m_AccidentSiteData;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData;
```

- `private Unity.Entities.ComponentLookup<Game.City.City> m_CityData`  

```csharp
private Unity.Entities.ComponentLookup<Game.City.City> m_CityData;
```

- `private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements`  

```csharp
private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements;
```

- `private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts`  

```csharp
private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts;
```

- `private Unity.Entities.BufferLookup<Game.Events.TargetElement> m_TargetElements`  

```csharp
private Unity.Entities.BufferLookup<Game.Events.TargetElement> m_TargetElements;
```

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```


## Constructors

- `public PolicePathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

```csharp
public PolicePathfindSetup(PathfindSetupSystem system)
	{
		m_PolicePatrolQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Buildings.PoliceStation>(),
				ComponentType.ReadOnly<Game.Vehicles.PoliceCar>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Game.Buildings.ServiceUpgrade>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_CrimeProducerQuery = system.GetSetupQuery(ComponentType.ReadOnly<CrimeProducer>(), ComponentType.Exclude<PropertyOnMarket>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Temp>());
		m_PrisonerTransportQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Buildings.Prison>(),
				ComponentType.ReadOnly<Game.Vehicles.PublicTransport>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Game.Buildings.ServiceUpgrade>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_PrisonerTransportRequestQuery = system.GetSetupQuery(ComponentType.ReadOnly<PrisonerTransportRequest>(), ComponentType.Exclude<Dispatched>(), ComponentType.Exclude<PathInformation>());
		m_PoliceRequestQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<PolicePatrolRequest>(),
				ComponentType.ReadOnly<PoliceEmergencyRequest>()
			},
			None = new ComponentType[2]
			{
				ComponentType.Exclude<Dispatched>(),
				ComponentType.Exclude<PathInformation>()
			}
		});
		m_EntityType = system.GetEntityTypeHandle();
		m_PathOwnerType = system.GetComponentTypeHandle<PathOwner>(isReadOnly: true);
		m_OwnerType = system.GetComponentTypeHandle<Owner>(isReadOnly: true);
		m_ServiceRequestType = system.GetComponentTypeHandle<ServiceRequest>(isReadOnly: true);
		m_PrisonerTransportRequestType = system.GetComponentTypeHandle<PrisonerTransportRequest>(isReadOnly: true);
		m_PolicePatrolRequestType = system.GetComponentTypeHandle<PolicePatrolRequest>(isReadOnly: true);
		m_PoliceEmergencyRequestType = system.GetComponentTypeHandle<PoliceEmergencyRequest>(isReadOnly: true);
		m_PoliceStationType = system.GetComponentTypeHandle<Game.Buildings.PoliceStation>(isReadOnly: true);
		m_CrimeProducerType = system.GetComponentTypeHandle<CrimeProducer>(isReadOnly: true);
		m_PrisonType = system.GetComponentTypeHandle<Game.Buildings.Prison>(isReadOnly: true);
		m_PoliceCarType = system.GetComponentTypeHandle<Game.Vehicles.PoliceCar>(isReadOnly: true);
		m_HelicopterType = system.GetComponentTypeHandle<Helicopter>(isReadOnly: true);
		m_PublicTransportType = system.GetComponentTypeHandle<Game.Vehicles.PublicTransport>(isReadOnly: true);
		m_PathElementType = system.GetBufferTypeHandle<PathElement>(isReadOnly: true);
		m_ServiceDispatchType = system.GetBufferTypeHandle<ServiceDispatch>(isReadOnly: true);
		m_PassengerType = system.GetBufferTypeHandle<Passenger>(isReadOnly: true);
		m_RenterType = system.GetBufferTypeHandle<Renter>(isReadOnly: true);
		m_EmployeeType = system.GetBufferTypeHandle<Employee>(isReadOnly: true);
		m_PathInformationData = system.GetComponentLookup<PathInformation>(isReadOnly: true);
		m_PolicePatrolRequestData = system.GetComponentLookup<PolicePatrolRequest>(isReadOnly: true);
		m_PoliceEmergencyRequestData = system.GetComponentLookup<PoliceEmergencyRequest>(isReadOnly: true);
		m_PrisonerTransportRequestData = system.GetComponentLookup<PrisonerTransportRequest>(isReadOnly: true);
		m_OutsideConnections = system.GetComponentLookup<Game.Objects.OutsideConnection>(isReadOnly: true);
		m_CompositionData = system.GetComponentLookup<Composition>(isReadOnly: true);
		m_CurrentDistrictData = system.GetComponentLookup<CurrentDistrict>(isReadOnly: true);
		m_DistrictData = system.GetComponentLookup<District>(isReadOnly: true);
		m_PoliceStationData = system.GetComponentLookup<Game.Buildings.PoliceStation>(isReadOnly: true);
		m_CreatureData = system.GetComponentLookup<Creature>(isReadOnly: true);
		m_VehicleData = system.GetComponentLookup<Vehicle>(isReadOnly: true);
		m_PoliceCarData = system.GetComponentLookup<Game.Vehicles.PoliceCar>(isReadOnly: true);
		m_PublicTransportData = system.GetComponentLookup<Game.Vehicles.PublicTransport>(isReadOnly: true);
		m_AccidentSiteData = system.GetComponentLookup<AccidentSite>(isReadOnly: true);
		m_NetCompositionData = system.GetComponentLookup<NetCompositionData>(isReadOnly: true);
		m_CityData = system.GetComponentLookup<Game.City.City>(isReadOnly: true);
		m_PathElements = system.GetBufferLookup<PathElement>(isReadOnly: true);
		m_ServiceDistricts = system.GetBufferLookup<ServiceDistrict>(isReadOnly: true);
		m_TargetElements = system.GetBufferLookup<TargetElement>(isReadOnly: true);
		m_AreaSearchSystem = system.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_NetSearchSystem = system.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_CitySystem = system.World.GetOrCreateSystemManaged<CitySystem>();
	}
```


## Methods

- `public SetupCrimeProducer(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupCrimeProducer(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_RenterType.Update(system);
		m_EmployeeType.Update(system);
		m_CrimeProducerType.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupCrimeProducersJob
		{
			m_EntityType = m_EntityType,
			m_CrimeProducerType = m_CrimeProducerType,
			m_RenterType = m_RenterType,
			m_EmployeeType = m_EmployeeType,
			m_SetupData = setupData
		}, m_CrimeProducerQuery, inputDeps);
	}
```

- `public SetupPolicePatrols(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupPolicePatrols(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_PoliceStationType.Update(system);
		m_PoliceCarType.Update(system);
		m_HelicopterType.Update(system);
		m_PathOwnerType.Update(system);
		m_OwnerType.Update(system);
		m_PathElementType.Update(system);
		m_ServiceDispatchType.Update(system);
		m_PassengerType.Update(system);
		m_PathInformationData.Update(system);
		m_PoliceEmergencyRequestData.Update(system);
		m_PathElements.Update(system);
		m_ServiceDistricts.Update(system);
		m_OutsideConnections.Update(system);
		m_CityData.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupPolicePatrolsJob
		{
			m_EntityType = m_EntityType,
			m_PoliceStationType = m_PoliceStationType,
			m_PoliceCarType = m_PoliceCarType,
			m_HelicopterType = m_HelicopterType,
			m_PathOwnerType = m_PathOwnerType,
			m_OwnerType = m_OwnerType,
			m_PathElementType = m_PathElementType,
			m_ServiceDispatchType = m_ServiceDispatchType,
			m_PassengerType = m_PassengerType,
			m_PathInformationData = m_PathInformationData,
			m_PoliceEmergencyRequestData = m_PoliceEmergencyRequestData,
			m_PathElements = m_PathElements,
			m_ServiceDistricts = m_ServiceDistricts,
			m_OutsideConnections = m_OutsideConnections,
			m_CityData = m_CityData,
			m_City = m_CitySystem.City,
			m_SetupData = setupData
		}, m_PolicePatrolQuery, inputDeps);
	}
```

- `public SetupPoliceRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupPoliceRequest(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_ServiceRequestType.Update(system);
		m_PolicePatrolRequestType.Update(system);
		m_PoliceEmergencyRequestType.Update(system);
		m_PolicePatrolRequestData.Update(system);
		m_PoliceEmergencyRequestData.Update(system);
		m_CompositionData.Update(system);
		m_CurrentDistrictData.Update(system);
		m_DistrictData.Update(system);
		m_CreatureData.Update(system);
		m_VehicleData.Update(system);
		m_PoliceCarData.Update(system);
		m_PoliceStationData.Update(system);
		m_AccidentSiteData.Update(system);
		m_NetCompositionData.Update(system);
		m_ServiceDistricts.Update(system);
		m_TargetElements.Update(system);
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new PoliceRequestsJob
		{
			m_EntityType = m_EntityType,
			m_ServiceRequestType = m_ServiceRequestType,
			m_PolicePatrolRequestType = m_PolicePatrolRequestType,
			m_PoliceEmergencyRequestType = m_PoliceEmergencyRequestType,
			m_PolicePatrolRequestData = m_PolicePatrolRequestData,
			m_PoliceEmergencyRequestData = m_PoliceEmergencyRequestData,
			m_CompositionData = m_CompositionData,
			m_CurrentDistrictData = m_CurrentDistrictData,
			m_DistrictData = m_DistrictData,
			m_CreatureData = m_CreatureData,
			m_VehicleData = m_VehicleData,
			m_PoliceCarData = m_PoliceCarData,
			m_PoliceStationData = m_PoliceStationData,
			m_AccidentSiteData = m_AccidentSiteData,
			m_NetCompositionData = m_NetCompositionData,
			m_ServiceDistricts = m_ServiceDistricts,
			m_TargetElements = m_TargetElements,
			m_AreaTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies),
			m_NetTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies2),
			m_SetupData = setupData
		}, m_PoliceRequestQuery, JobHandle.CombineDependencies(inputDeps, dependencies, dependencies2));
		m_AreaSearchSystem.AddSearchTreeReader(jobHandle);
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
		return jobHandle;
	}
```

- `public SetupPrisonerTransport(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupPrisonerTransport(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_PrisonType.Update(system);
		m_PublicTransportType.Update(system);
		m_PathOwnerType.Update(system);
		m_OwnerType.Update(system);
		m_PathElementType.Update(system);
		m_ServiceDispatchType.Update(system);
		m_PathInformationData.Update(system);
		m_PathElements.Update(system);
		m_ServiceDistricts.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupPrisonerTransportJob
		{
			m_EntityType = m_EntityType,
			m_PrisonType = m_PrisonType,
			m_PublicTransportType = m_PublicTransportType,
			m_PathOwnerType = m_PathOwnerType,
			m_OwnerType = m_OwnerType,
			m_PathElementType = m_PathElementType,
			m_ServiceDispatchType = m_ServiceDispatchType,
			m_PathInformationData = m_PathInformationData,
			m_PathElements = m_PathElements,
			m_ServiceDistricts = m_ServiceDistricts,
			m_SetupData = setupData
		}, m_PrisonerTransportQuery, inputDeps);
	}
```

- `public SetupPrisonerTransportRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupPrisonerTransportRequest(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_ServiceRequestType.Update(system);
		m_PrisonerTransportRequestType.Update(system);
		m_PrisonerTransportRequestData.Update(system);
		m_CurrentDistrictData.Update(system);
		m_PublicTransportData.Update(system);
		m_ServiceDistricts.Update(system);
		return JobChunkExtensions.ScheduleParallel(new PrisonerTransportRequestsJob
		{
			m_EntityType = m_EntityType,
			m_ServiceRequestType = m_ServiceRequestType,
			m_PrisonerTransportRequestType = m_PrisonerTransportRequestType,
			m_PrisonerTransportRequestData = m_PrisonerTransportRequestData,
			m_CurrentDistrictData = m_CurrentDistrictData,
			m_PublicTransportData = m_PublicTransportData,
			m_ServiceDistricts = m_ServiceDistricts,
			m_SetupData = setupData
		}, m_PrisonerTransportRequestQuery, inputDeps);
	}
```


## Nested types

- `Game.Simulation.PolicePathfindSetup+SetupPolicePatrolsJob`  
- `Game.Simulation.PolicePathfindSetup+SetupCrimeProducersJob`  
- `Game.Simulation.PolicePathfindSetup+SetupPrisonerTransportJob`  
- `Game.Simulation.PolicePathfindSetup+PrisonerTransportRequestsJob`  
- `Game.Simulation.PolicePathfindSetup+PoliceRequestsJob`  

