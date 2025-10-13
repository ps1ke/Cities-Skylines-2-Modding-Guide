# Game.Simulation.FirePathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct FirePathfindSetup
{
    private Unity.Entities.EntityQuery m_FireEngineQuery;
    private Unity.Entities.EntityQuery m_EmergencyShelterQuery;
    private Unity.Entities.EntityQuery m_EvacuationTransportQuery;
    private Unity.Entities.EntityQuery m_EvacuationRequestQuery;
    private Unity.Entities.EntityQuery m_FireRescueRequestQuery;
    private Unity.Entities.EntityTypeHandle m_EntityType;
    private Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathOwner> m_PathOwnerType;
    private Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.FireRescueRequest> m_FireRescueRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.EvacuationRequest> m_EvacuationRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Buildings.FireStation> m_FireStationType;
    private Unity.Entities.ComponentTypeHandle<Game.Buildings.EmergencyShelter> m_EmergencyShelterType;
    private Unity.Entities.ComponentTypeHandle<Game.Vehicles.FireEngine> m_FireEngineType;
    private Unity.Entities.ComponentTypeHandle<Game.Vehicles.PublicTransport> m_PublicTransportType;
    private Unity.Entities.BufferTypeHandle<Game.Pathfind.PathElement> m_PathElementType;
    private Unity.Entities.BufferTypeHandle<Game.Simulation.ServiceDispatch> m_ServiceDispatchType;
    private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformationData;
    private Unity.Entities.ComponentLookup<Game.Simulation.FireRescueRequest> m_FireRescueRequestData;
    private Unity.Entities.ComponentLookup<Game.Simulation.EvacuationRequest> m_EvacuationRequestData;
    private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections;
    private Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData;
    private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData;
    private Unity.Entities.ComponentLookup<Game.Areas.District> m_DistrictData;
    private Unity.Entities.ComponentLookup<Game.Buildings.FireStation> m_FireStationData;
    private Unity.Entities.ComponentLookup<Game.Vehicles.FireEngine> m_FireEngineData;
    private Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransportData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData;
    private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements;
    private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts;
    private Unity.Entities.ComponentLookup<Game.City.City> m_CityData;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;
    private Game.Simulation.CitySystem m_CitySystem;

    public FirePathfindSetup(Game.Simulation.PathfindSetupSystem system);

    public Unity.Jobs.JobHandle SetupEmergencyShelters(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupEvacuationRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupEvacuationTransport(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupFireEngines(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupFireRescueRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_FireEngineQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireEngineQuery;
```

- `private Unity.Entities.EntityQuery m_EmergencyShelterQuery`  

```csharp
private Unity.Entities.EntityQuery m_EmergencyShelterQuery;
```

- `private Unity.Entities.EntityQuery m_EvacuationTransportQuery`  

```csharp
private Unity.Entities.EntityQuery m_EvacuationTransportQuery;
```

- `private Unity.Entities.EntityQuery m_EvacuationRequestQuery`  

```csharp
private Unity.Entities.EntityQuery m_EvacuationRequestQuery;
```

- `private Unity.Entities.EntityQuery m_FireRescueRequestQuery`  

```csharp
private Unity.Entities.EntityQuery m_FireRescueRequestQuery;
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

- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.FireRescueRequest> m_FireRescueRequestType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Simulation.FireRescueRequest> m_FireRescueRequestType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.EvacuationRequest> m_EvacuationRequestType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Simulation.EvacuationRequest> m_EvacuationRequestType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.FireStation> m_FireStationType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Buildings.FireStation> m_FireStationType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.EmergencyShelter> m_EmergencyShelterType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Buildings.EmergencyShelter> m_EmergencyShelterType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.FireEngine> m_FireEngineType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Vehicles.FireEngine> m_FireEngineType;
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

- `private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformationData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformationData;
```

- `private Unity.Entities.ComponentLookup<Game.Simulation.FireRescueRequest> m_FireRescueRequestData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Simulation.FireRescueRequest> m_FireRescueRequestData;
```

- `private Unity.Entities.ComponentLookup<Game.Simulation.EvacuationRequest> m_EvacuationRequestData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Simulation.EvacuationRequest> m_EvacuationRequestData;
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

- `private Unity.Entities.ComponentLookup<Game.Buildings.FireStation> m_FireStationData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.FireStation> m_FireStationData;
```

- `private Unity.Entities.ComponentLookup<Game.Vehicles.FireEngine> m_FireEngineData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Vehicles.FireEngine> m_FireEngineData;
```

- `private Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransportData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransportData;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData;
```

- `private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements`  

```csharp
private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements;
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

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```


## Constructors

- `public FirePathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

```csharp
public FirePathfindSetup(PathfindSetupSystem system)
	{
		m_FireEngineQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Buildings.FireStation>(),
				ComponentType.ReadOnly<Game.Vehicles.FireEngine>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Game.Buildings.ServiceUpgrade>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_EmergencyShelterQuery = system.GetSetupQuery(ComponentType.ReadOnly<Game.Buildings.EmergencyShelter>(), ComponentType.ReadOnly<ServiceDispatch>(), ComponentType.Exclude<Temp>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Deleted>());
		m_EvacuationTransportQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Buildings.EmergencyShelter>(),
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
		m_EvacuationRequestQuery = system.GetSetupQuery(ComponentType.ReadOnly<EvacuationRequest>(), ComponentType.Exclude<Dispatched>(), ComponentType.Exclude<PathInformation>());
		m_FireRescueRequestQuery = system.GetSetupQuery(ComponentType.ReadOnly<FireRescueRequest>(), ComponentType.Exclude<Dispatched>(), ComponentType.Exclude<PathInformation>());
		m_EntityType = system.GetEntityTypeHandle();
		m_PathOwnerType = system.GetComponentTypeHandle<PathOwner>(isReadOnly: true);
		m_OwnerType = system.GetComponentTypeHandle<Owner>(isReadOnly: true);
		m_ServiceRequestType = system.GetComponentTypeHandle<ServiceRequest>(isReadOnly: true);
		m_FireRescueRequestType = system.GetComponentTypeHandle<FireRescueRequest>(isReadOnly: true);
		m_EvacuationRequestType = system.GetComponentTypeHandle<EvacuationRequest>(isReadOnly: true);
		m_FireStationType = system.GetComponentTypeHandle<Game.Buildings.FireStation>(isReadOnly: true);
		m_EmergencyShelterType = system.GetComponentTypeHandle<Game.Buildings.EmergencyShelter>(isReadOnly: true);
		m_FireEngineType = system.GetComponentTypeHandle<Game.Vehicles.FireEngine>(isReadOnly: true);
		m_PublicTransportType = system.GetComponentTypeHandle<Game.Vehicles.PublicTransport>(isReadOnly: true);
		m_PathElementType = system.GetBufferTypeHandle<PathElement>(isReadOnly: true);
		m_ServiceDispatchType = system.GetBufferTypeHandle<ServiceDispatch>(isReadOnly: true);
		m_PathInformationData = system.GetComponentLookup<PathInformation>(isReadOnly: true);
		m_FireRescueRequestData = system.GetComponentLookup<FireRescueRequest>(isReadOnly: true);
		m_EvacuationRequestData = system.GetComponentLookup<EvacuationRequest>(isReadOnly: true);
		m_OutsideConnections = system.GetComponentLookup<Game.Objects.OutsideConnection>(isReadOnly: true);
		m_CompositionData = system.GetComponentLookup<Composition>(isReadOnly: true);
		m_CurrentDistrictData = system.GetComponentLookup<CurrentDistrict>(isReadOnly: true);
		m_DistrictData = system.GetComponentLookup<District>(isReadOnly: true);
		m_FireStationData = system.GetComponentLookup<Game.Buildings.FireStation>(isReadOnly: true);
		m_FireEngineData = system.GetComponentLookup<Game.Vehicles.FireEngine>(isReadOnly: true);
		m_PublicTransportData = system.GetComponentLookup<Game.Vehicles.PublicTransport>(isReadOnly: true);
		m_NetCompositionData = system.GetComponentLookup<NetCompositionData>(isReadOnly: true);
		m_PathElements = system.GetBufferLookup<PathElement>(isReadOnly: true);
		m_ServiceDistricts = system.GetBufferLookup<ServiceDistrict>(isReadOnly: true);
		m_CityData = system.GetComponentLookup<Game.City.City>(isReadOnly: true);
		m_AreaSearchSystem = system.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_NetSearchSystem = system.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
		m_CitySystem = system.World.GetOrCreateSystemManaged<CitySystem>();
	}
```


## Methods

- `public SetupEmergencyShelters(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupEmergencyShelters(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_EmergencyShelterType.Update(system);
		m_ServiceDistricts.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupEmergencySheltersJob
		{
			m_EntityType = m_EntityType,
			m_EmergencyShelterType = m_EmergencyShelterType,
			m_ServiceDistricts = m_ServiceDistricts,
			m_SetupData = setupData
		}, m_EmergencyShelterQuery, inputDeps);
	}
```

- `public SetupEvacuationRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupEvacuationRequest(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_ServiceRequestType.Update(system);
		m_EvacuationRequestType.Update(system);
		m_EvacuationRequestData.Update(system);
		m_CurrentDistrictData.Update(system);
		m_PublicTransportData.Update(system);
		m_ServiceDistricts.Update(system);
		return JobChunkExtensions.ScheduleParallel(new EvacuationRequestsJob
		{
			m_EntityType = m_EntityType,
			m_ServiceRequestType = m_ServiceRequestType,
			m_EvacuationRequestType = m_EvacuationRequestType,
			m_EvacuationRequestData = m_EvacuationRequestData,
			m_CurrentDistrictData = m_CurrentDistrictData,
			m_PublicTransportData = m_PublicTransportData,
			m_ServiceDistricts = m_ServiceDistricts,
			m_SetupData = setupData
		}, m_EvacuationRequestQuery, inputDeps);
	}
```

- `public SetupEvacuationTransport(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupEvacuationTransport(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_EmergencyShelterType.Update(system);
		m_PublicTransportType.Update(system);
		m_PathOwnerType.Update(system);
		m_OwnerType.Update(system);
		m_PathElementType.Update(system);
		m_ServiceDispatchType.Update(system);
		m_PathInformationData.Update(system);
		m_PathElements.Update(system);
		m_ServiceDistricts.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupEvacuationTransportJob
		{
			m_EntityType = m_EntityType,
			m_EmergencyShelterType = m_EmergencyShelterType,
			m_PublicTransportType = m_PublicTransportType,
			m_PathOwnerType = m_PathOwnerType,
			m_OwnerType = m_OwnerType,
			m_PathElementType = m_PathElementType,
			m_ServiceDispatchType = m_ServiceDispatchType,
			m_PathInformationData = m_PathInformationData,
			m_PathElements = m_PathElements,
			m_ServiceDistricts = m_ServiceDistricts,
			m_SetupData = setupData
		}, m_EvacuationTransportQuery, inputDeps);
	}
```

- `public SetupFireEngines(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupFireEngines(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_FireStationType.Update(system);
		m_FireEngineType.Update(system);
		m_PathOwnerType.Update(system);
		m_OwnerType.Update(system);
		m_PathElementType.Update(system);
		m_ServiceDispatchType.Update(system);
		m_PathInformationData.Update(system);
		m_FireRescueRequestData.Update(system);
		m_PathElements.Update(system);
		m_ServiceDistricts.Update(system);
		m_OutsideConnections.Update(system);
		m_CityData.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupFireEnginesJob
		{
			m_EntityType = m_EntityType,
			m_FireStationType = m_FireStationType,
			m_FireEngineType = m_FireEngineType,
			m_PathOwnerType = m_PathOwnerType,
			m_OwnerType = m_OwnerType,
			m_PathElementType = m_PathElementType,
			m_ServiceDispatchType = m_ServiceDispatchType,
			m_PathInformationData = m_PathInformationData,
			m_FireRescueRequestData = m_FireRescueRequestData,
			m_PathElements = m_PathElements,
			m_ServiceDistricts = m_ServiceDistricts,
			m_OutsideConnections = m_OutsideConnections,
			m_CityData = m_CityData,
			m_City = m_CitySystem.City,
			m_SetupData = setupData
		}, m_FireEngineQuery, inputDeps);
	}
```

- `public SetupFireRescueRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupFireRescueRequest(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_ServiceRequestType.Update(system);
		m_FireRescueRequestType.Update(system);
		m_FireRescueRequestData.Update(system);
		m_CompositionData.Update(system);
		m_CurrentDistrictData.Update(system);
		m_DistrictData.Update(system);
		m_FireEngineData.Update(system);
		m_FireStationData.Update(system);
		m_NetCompositionData.Update(system);
		m_ServiceDistricts.Update(system);
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new FireRescueRequestsJob
		{
			m_EntityType = m_EntityType,
			m_ServiceRequestType = m_ServiceRequestType,
			m_FireRescueRequestType = m_FireRescueRequestType,
			m_FireRescueRequestData = m_FireRescueRequestData,
			m_CompositionData = m_CompositionData,
			m_CurrentDistrictData = m_CurrentDistrictData,
			m_DistrictData = m_DistrictData,
			m_FireEngineData = m_FireEngineData,
			m_FireStationData = m_FireStationData,
			m_NetCompositionData = m_NetCompositionData,
			m_ServiceDistricts = m_ServiceDistricts,
			m_AreaTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies),
			m_NetTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies2),
			m_SetupData = setupData
		}, m_FireRescueRequestQuery, JobHandle.CombineDependencies(inputDeps, dependencies, dependencies2));
		m_AreaSearchSystem.AddSearchTreeReader(jobHandle);
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
		return jobHandle;
	}
```


## Nested types

- `Game.Simulation.FirePathfindSetup+SetupFireEnginesJob`  
- `Game.Simulation.FirePathfindSetup+SetupEmergencySheltersJob`  
- `Game.Simulation.FirePathfindSetup+SetupEvacuationTransportJob`  
- `Game.Simulation.FirePathfindSetup+EvacuationRequestsJob`  
- `Game.Simulation.FirePathfindSetup+FireRescueRequestsJob`  

