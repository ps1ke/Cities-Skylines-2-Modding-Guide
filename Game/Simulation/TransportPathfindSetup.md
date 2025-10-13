# Game.Simulation.TransportPathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct TransportPathfindSetup
{
    private Unity.Entities.EntityQuery m_TransportVehicleQuery;
    private Unity.Entities.EntityQuery m_TaxiQuery;
    private Unity.Entities.EntityQuery m_TransportVehicleRequestQuery;
    private Unity.Entities.EntityQuery m_TaxiRequestQuery;
    private Unity.Entities.EntityTypeHandle m_EntityType;
    private Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathOwner> m_PathOwnerType;
    private Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
    private Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnectionType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.TransportVehicleRequest> m_TransportVehicleRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.TaxiRequest> m_TaxiRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Buildings.TransportDepot> m_TransportDepotType;
    private Unity.Entities.ComponentTypeHandle<Game.Vehicles.CargoTransport> m_CargoTransportType;
    private Unity.Entities.ComponentTypeHandle<Game.Vehicles.PublicTransport> m_PublicTransportType;
    private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Taxi> m_TaxiType;
    private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Controller> m_ControllerType;
    private Unity.Entities.ComponentTypeHandle<Game.Routes.Color> m_RouteColorType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
    private Unity.Entities.BufferTypeHandle<Game.Pathfind.PathElement> m_PathElementType;
    private Unity.Entities.BufferTypeHandle<Game.Simulation.ServiceDispatch> m_ServiceDispatchType;
    private Unity.Entities.BufferTypeHandle<Game.Vehicles.LayoutElement> m_LayoutElementType;
    private Unity.Entities.ComponentLookup<Game.Simulation.TransportVehicleRequest> m_TransportVehicleRequestData;
    private Unity.Entities.ComponentLookup<Game.Simulation.TaxiRequest> m_TaxiRequestData;
    private Unity.Entities.ComponentLookup<Game.Routes.VehicleModel> m_VehicleModelData;
    private Unity.Entities.ComponentLookup<Game.Routes.Color> m_RouteColorData;
    private Unity.Entities.ComponentLookup<Game.Buildings.TransportDepot> m_TransportDepotData;
    private Unity.Entities.ComponentLookup<Game.Vehicles.CargoTransport> m_CargoTransportData;
    private Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransportData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.TransportLineData> m_TransportLineData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.TransportDepotData> m_PrefabTransportDepotData;
    private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts;
    private Unity.Entities.BufferLookup<Game.Routes.RouteWaypoint> m_Waypoints;

    public TransportPathfindSetup(Game.Simulation.PathfindSetupSystem system);

    public Unity.Jobs.JobHandle SetupRouteWaypoints(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupTaxi(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupTaxiRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupTransportVehicle(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupTransportVehicleRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_TransportVehicleQuery`  

```csharp
private Unity.Entities.EntityQuery m_TransportVehicleQuery;
```

- `private Unity.Entities.EntityQuery m_TaxiQuery`  

```csharp
private Unity.Entities.EntityQuery m_TaxiQuery;
```

- `private Unity.Entities.EntityQuery m_TransportVehicleRequestQuery`  

```csharp
private Unity.Entities.EntityQuery m_TransportVehicleRequestQuery;
```

- `private Unity.Entities.EntityQuery m_TaxiRequestQuery`  

```csharp
private Unity.Entities.EntityQuery m_TaxiRequestQuery;
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

- `private Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnectionType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnectionType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.TransportVehicleRequest> m_TransportVehicleRequestType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Simulation.TransportVehicleRequest> m_TransportVehicleRequestType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.TaxiRequest> m_TaxiRequestType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Simulation.TaxiRequest> m_TaxiRequestType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.TransportDepot> m_TransportDepotType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Buildings.TransportDepot> m_TransportDepotType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.CargoTransport> m_CargoTransportType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Vehicles.CargoTransport> m_CargoTransportType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.PublicTransport> m_PublicTransportType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Vehicles.PublicTransport> m_PublicTransportType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Taxi> m_TaxiType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Taxi> m_TaxiType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Controller> m_ControllerType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Vehicles.Controller> m_ControllerType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Routes.Color> m_RouteColorType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Routes.Color> m_RouteColorType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Pathfind.PathElement> m_PathElementType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Pathfind.PathElement> m_PathElementType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Simulation.ServiceDispatch> m_ServiceDispatchType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Simulation.ServiceDispatch> m_ServiceDispatchType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Vehicles.LayoutElement> m_LayoutElementType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Vehicles.LayoutElement> m_LayoutElementType;
```

- `private Unity.Entities.ComponentLookup<Game.Simulation.TransportVehicleRequest> m_TransportVehicleRequestData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Simulation.TransportVehicleRequest> m_TransportVehicleRequestData;
```

- `private Unity.Entities.ComponentLookup<Game.Simulation.TaxiRequest> m_TaxiRequestData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Simulation.TaxiRequest> m_TaxiRequestData;
```

- `private Unity.Entities.ComponentLookup<Game.Routes.VehicleModel> m_VehicleModelData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Routes.VehicleModel> m_VehicleModelData;
```

- `private Unity.Entities.ComponentLookup<Game.Routes.Color> m_RouteColorData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Routes.Color> m_RouteColorData;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.TransportDepot> m_TransportDepotData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.TransportDepot> m_TransportDepotData;
```

- `private Unity.Entities.ComponentLookup<Game.Vehicles.CargoTransport> m_CargoTransportData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Vehicles.CargoTransport> m_CargoTransportData;
```

- `private Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransportData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Vehicles.PublicTransport> m_PublicTransportData;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.TransportLineData> m_TransportLineData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.TransportLineData> m_TransportLineData;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.TransportDepotData> m_PrefabTransportDepotData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.TransportDepotData> m_PrefabTransportDepotData;
```

- `private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts`  

```csharp
private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts;
```

- `private Unity.Entities.BufferLookup<Game.Routes.RouteWaypoint> m_Waypoints`  

```csharp
private Unity.Entities.BufferLookup<Game.Routes.RouteWaypoint> m_Waypoints;
```


## Constructors

- `public TransportPathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

```csharp
public TransportPathfindSetup(PathfindSetupSystem system)
	{
		m_TransportVehicleQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Buildings.TransportDepot>(),
				ComponentType.ReadOnly<Game.Vehicles.CargoTransport>(),
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
		m_TaxiQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Buildings.TransportDepot>(),
				ComponentType.ReadOnly<Game.Vehicles.Taxi>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Game.Buildings.ServiceUpgrade>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_TransportVehicleRequestQuery = system.GetSetupQuery(ComponentType.ReadOnly<TransportVehicleRequest>(), ComponentType.Exclude<Dispatched>(), ComponentType.Exclude<PathInformation>());
		m_TaxiRequestQuery = system.GetSetupQuery(ComponentType.ReadOnly<TaxiRequest>(), ComponentType.Exclude<Dispatched>(), ComponentType.Exclude<PathInformation>());
		m_EntityType = system.GetEntityTypeHandle();
		m_PathOwnerType = system.GetComponentTypeHandle<PathOwner>(isReadOnly: true);
		m_OwnerType = system.GetComponentTypeHandle<Owner>(isReadOnly: true);
		m_OutsideConnectionType = system.GetComponentTypeHandle<Game.Objects.OutsideConnection>(isReadOnly: true);
		m_ServiceRequestType = system.GetComponentTypeHandle<ServiceRequest>(isReadOnly: true);
		m_TransportVehicleRequestType = system.GetComponentTypeHandle<TransportVehicleRequest>(isReadOnly: true);
		m_TaxiRequestType = system.GetComponentTypeHandle<TaxiRequest>(isReadOnly: true);
		m_TransportDepotType = system.GetComponentTypeHandle<Game.Buildings.TransportDepot>(isReadOnly: true);
		m_CargoTransportType = system.GetComponentTypeHandle<Game.Vehicles.CargoTransport>(isReadOnly: true);
		m_PublicTransportType = system.GetComponentTypeHandle<Game.Vehicles.PublicTransport>(isReadOnly: true);
		m_TaxiType = system.GetComponentTypeHandle<Game.Vehicles.Taxi>(isReadOnly: true);
		m_ControllerType = system.GetComponentTypeHandle<Controller>(isReadOnly: true);
		m_RouteColorType = system.GetComponentTypeHandle<Game.Routes.Color>(isReadOnly: true);
		m_PrefabRefType = system.GetComponentTypeHandle<PrefabRef>(isReadOnly: true);
		m_PathElementType = system.GetBufferTypeHandle<PathElement>(isReadOnly: true);
		m_ServiceDispatchType = system.GetBufferTypeHandle<ServiceDispatch>(isReadOnly: true);
		m_LayoutElementType = system.GetBufferTypeHandle<LayoutElement>(isReadOnly: true);
		m_TransportVehicleRequestData = system.GetComponentLookup<TransportVehicleRequest>(isReadOnly: true);
		m_TaxiRequestData = system.GetComponentLookup<TaxiRequest>(isReadOnly: true);
		m_VehicleModelData = system.GetComponentLookup<VehicleModel>(isReadOnly: true);
		m_RouteColorData = system.GetComponentLookup<Game.Routes.Color>(isReadOnly: true);
		m_TransportDepotData = system.GetComponentLookup<Game.Buildings.TransportDepot>(isReadOnly: true);
		m_CargoTransportData = system.GetComponentLookup<Game.Vehicles.CargoTransport>(isReadOnly: true);
		m_PublicTransportData = system.GetComponentLookup<Game.Vehicles.PublicTransport>(isReadOnly: true);
		m_TransportLineData = system.GetComponentLookup<TransportLineData>(isReadOnly: true);
		m_PrefabTransportDepotData = system.GetComponentLookup<TransportDepotData>(isReadOnly: true);
		m_ServiceDistricts = system.GetBufferLookup<ServiceDistrict>(isReadOnly: true);
		m_Waypoints = system.GetBufferLookup<RouteWaypoint>(isReadOnly: true);
	}
```


## Methods

- `public SetupRouteWaypoints(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupRouteWaypoints(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_Waypoints.Update(system);
		return IJobParallelForExtensions.Schedule(new SetupRouteWaypointsJob
		{
			m_Waypoints = m_Waypoints,
			m_SetupData = setupData
		}, setupData.Length, 1, inputDeps);
	}
```

- `public SetupTaxi(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupTaxi(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_TransportDepotType.Update(system);
		m_TaxiType.Update(system);
		m_OwnerType.Update(system);
		m_PathOwnerType.Update(system);
		m_OutsideConnectionType.Update(system);
		m_PrefabRefType.Update(system);
		m_PathElementType.Update(system);
		m_ServiceDispatchType.Update(system);
		m_TaxiRequestData.Update(system);
		m_TransportDepotData.Update(system);
		m_PrefabTransportDepotData.Update(system);
		m_ServiceDistricts.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupTaxisJob
		{
			m_EntityType = m_EntityType,
			m_TransportDepotType = m_TransportDepotType,
			m_TaxiType = m_TaxiType,
			m_OwnerType = m_OwnerType,
			m_PathOwnerType = m_PathOwnerType,
			m_OutsideConnectionType = m_OutsideConnectionType,
			m_PrefabRefType = m_PrefabRefType,
			m_PathElementType = m_PathElementType,
			m_ServiceDispatchType = m_ServiceDispatchType,
			m_TaxiRequestData = m_TaxiRequestData,
			m_TransportDepotData = m_TransportDepotData,
			m_PrefabTransportDepotData = m_PrefabTransportDepotData,
			m_ServiceDistricts = m_ServiceDistricts,
			m_SetupData = setupData
		}, m_TaxiQuery, inputDeps);
	}
```

- `public SetupTaxiRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupTaxiRequest(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_ServiceRequestType.Update(system);
		m_TaxiRequestType.Update(system);
		m_TaxiRequestData.Update(system);
		m_TransportDepotData.Update(system);
		m_ServiceDistricts.Update(system);
		return JobChunkExtensions.ScheduleParallel(new TaxiRequestsJob
		{
			m_EntityType = m_EntityType,
			m_ServiceRequestType = m_ServiceRequestType,
			m_TaxiRequestType = m_TaxiRequestType,
			m_TaxiRequestData = m_TaxiRequestData,
			m_TransportDepotData = m_TransportDepotData,
			m_ServiceDistricts = m_ServiceDistricts,
			m_SetupData = setupData
		}, m_TaxiRequestQuery, inputDeps);
	}
```

- `public SetupTransportVehicle(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupTransportVehicle(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_TransportDepotType.Update(system);
		m_CargoTransportType.Update(system);
		m_PublicTransportType.Update(system);
		m_ControllerType.Update(system);
		m_RouteColorType.Update(system);
		m_OwnerType.Update(system);
		m_PrefabRefType.Update(system);
		m_LayoutElementType.Update(system);
		m_TransportVehicleRequestData.Update(system);
		m_VehicleModelData.Update(system);
		m_RouteColorData.Update(system);
		m_PrefabTransportDepotData.Update(system);
		m_TransportLineData.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupTransportVehiclesJob
		{
			m_EntityType = m_EntityType,
			m_TransportDepotType = m_TransportDepotType,
			m_CargoTransportType = m_CargoTransportType,
			m_PublicTransportType = m_PublicTransportType,
			m_ControllerType = m_ControllerType,
			m_RouteColorType = m_RouteColorType,
			m_OwnerType = m_OwnerType,
			m_PrefabRefType = m_PrefabRefType,
			m_LayoutElementType = m_LayoutElementType,
			m_TransportVehicleRequestData = m_TransportVehicleRequestData,
			m_VehicleModelData = m_VehicleModelData,
			m_RouteColorData = m_RouteColorData,
			m_PrefabTransportDepotData = m_PrefabTransportDepotData,
			m_TransportLineData = m_TransportLineData,
			m_SetupData = setupData
		}, m_TransportVehicleQuery, inputDeps);
	}
```

- `public SetupTransportVehicleRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupTransportVehicleRequest(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_ServiceRequestType.Update(system);
		m_TransportVehicleRequestType.Update(system);
		m_TransportVehicleRequestData.Update(system);
		m_VehicleModelData.Update(system);
		m_PublicTransportData.Update(system);
		m_CargoTransportData.Update(system);
		m_TransportLineData.Update(system);
		m_PrefabTransportDepotData.Update(system);
		m_Waypoints.Update(system);
		return JobChunkExtensions.ScheduleParallel(new TransportVehicleRequestsJob
		{
			m_EntityType = m_EntityType,
			m_ServiceRequestType = m_ServiceRequestType,
			m_TransportVehicleRequestType = m_TransportVehicleRequestType,
			m_TransportVehicleRequestData = m_TransportVehicleRequestData,
			m_VehicleModelData = m_VehicleModelData,
			m_PublicTransportData = m_PublicTransportData,
			m_CargoTransportData = m_CargoTransportData,
			m_TransportLineData = m_TransportLineData,
			m_TransportDepotData = m_PrefabTransportDepotData,
			m_Waypoints = m_Waypoints,
			m_SetupData = setupData
		}, m_TransportVehicleRequestQuery, inputDeps);
	}
```


## Nested types

- `Game.Simulation.TransportPathfindSetup+SetupTransportVehiclesJob`  
- `Game.Simulation.TransportPathfindSetup+SetupTaxisJob`  
- `Game.Simulation.TransportPathfindSetup+SetupRouteWaypointsJob`  
- `Game.Simulation.TransportPathfindSetup+TransportVehicleRequestsJob`  
- `Game.Simulation.TransportPathfindSetup+TaxiRequestsJob`  

