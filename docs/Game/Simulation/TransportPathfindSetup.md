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
public TransportPathfindSetup(Game.Simulation.PathfindSetupSystem system);
```


## Methods

- `public SetupRouteWaypoints(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupRouteWaypoints(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetupTaxi(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupTaxi(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetupTaxiRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupTaxiRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetupTransportVehicle(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupTransportVehicle(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetupTransportVehicleRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupTransportVehicleRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Simulation.TransportPathfindSetup+SetupTransportVehiclesJob`  
- `Game.Simulation.TransportPathfindSetup+SetupTaxisJob`  
- `Game.Simulation.TransportPathfindSetup+SetupRouteWaypointsJob`  
- `Game.Simulation.TransportPathfindSetup+TransportVehicleRequestsJob`  
- `Game.Simulation.TransportPathfindSetup+TaxiRequestsJob`  

