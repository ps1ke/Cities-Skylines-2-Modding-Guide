# Game.Simulation.RoadPathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct RoadPathfindSetup
{
    private Unity.Entities.EntityQuery m_MaintenanceProviderQuery;
    private Unity.Entities.EntityQuery m_RandomTrafficQuery;
    private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
    private Unity.Entities.EntityQuery m_MaintenanceRequestQuery;
    private Unity.Entities.EntityTypeHandle m_EntityType;
    private Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathOwner> m_PathOwnerType;
    private Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
    private Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnectionType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.MaintenanceRequest> m_MaintenanceRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Buildings.MaintenanceDepot> m_MaintenanceDepotType;
    private Unity.Entities.ComponentTypeHandle<Game.Vehicles.MaintenanceVehicle> m_MaintenanceVehicleType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
    private Unity.Entities.BufferTypeHandle<Game.Pathfind.PathElement> m_PathElementType;
    private Unity.Entities.BufferTypeHandle<Game.Simulation.ServiceDispatch> m_ServiceDispatchType;
    private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformationData;
    private Unity.Entities.ComponentLookup<Game.Simulation.RandomTrafficRequest> m_RandomTrafficRequestData;
    private Unity.Entities.ComponentLookup<Game.Simulation.MaintenanceRequest> m_MaintenanceRequestData;
    private Unity.Entities.ComponentLookup<Game.Objects.Surface> m_SurfaceData;
    private Unity.Entities.ComponentLookup<Game.Buildings.Park> m_ParkData;
    private Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData;
    private Unity.Entities.ComponentLookup<Game.Net.NetCondition> m_NetConditionData;
    private Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData;
    private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData;
    private Unity.Entities.ComponentLookup<Game.Areas.BorderDistrict> m_BorderDistrictData;
    private Unity.Entities.ComponentLookup<Game.Areas.District> m_DistrictData;
    private Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.MaintenanceDepotData> m_PrefabMaintenanceDepotData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.MaintenanceVehicleData> m_PrefabMaintenanceVehicleData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.TrafficSpawnerData> m_PrefabTrafficSpawnerData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.NetCompositionData> m_NetCompositionData;
    private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements;
    private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts;
    private Game.Areas.SearchSystem m_AreaSearchSystem;
    private Game.Net.SearchSystem m_NetSearchSystem;

    public RoadPathfindSetup(Game.Simulation.PathfindSetupSystem system);

    public Unity.Jobs.JobHandle SetupMaintenanceProviders(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupMaintenanceRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupOutsideConnections(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupRandomTraffic(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_MaintenanceProviderQuery`  

```csharp
private Unity.Entities.EntityQuery m_MaintenanceProviderQuery;
```

- `private Unity.Entities.EntityQuery m_RandomTrafficQuery`  

```csharp
private Unity.Entities.EntityQuery m_RandomTrafficQuery;
```

- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  

```csharp
private Unity.Entities.EntityQuery m_OutsideConnectionQuery;
```

- `private Unity.Entities.EntityQuery m_MaintenanceRequestQuery`  

```csharp
private Unity.Entities.EntityQuery m_MaintenanceRequestQuery;
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

- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.MaintenanceRequest> m_MaintenanceRequestType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Simulation.MaintenanceRequest> m_MaintenanceRequestType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.MaintenanceDepot> m_MaintenanceDepotType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Buildings.MaintenanceDepot> m_MaintenanceDepotType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.MaintenanceVehicle> m_MaintenanceVehicleType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Vehicles.MaintenanceVehicle> m_MaintenanceVehicleType;
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

- `private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformationData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformationData;
```

- `private Unity.Entities.ComponentLookup<Game.Simulation.RandomTrafficRequest> m_RandomTrafficRequestData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Simulation.RandomTrafficRequest> m_RandomTrafficRequestData;
```

- `private Unity.Entities.ComponentLookup<Game.Simulation.MaintenanceRequest> m_MaintenanceRequestData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Simulation.MaintenanceRequest> m_MaintenanceRequestData;
```

- `private Unity.Entities.ComponentLookup<Game.Objects.Surface> m_SurfaceData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Objects.Surface> m_SurfaceData;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.Park> m_ParkData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.Park> m_ParkData;
```

- `private Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Net.Edge> m_EdgeData;
```

- `private Unity.Entities.ComponentLookup<Game.Net.NetCondition> m_NetConditionData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Net.NetCondition> m_NetConditionData;
```

- `private Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Net.Composition> m_CompositionData;
```

- `private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData;
```

- `private Unity.Entities.ComponentLookup<Game.Areas.BorderDistrict> m_BorderDistrictData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Areas.BorderDistrict> m_BorderDistrictData;
```

- `private Unity.Entities.ComponentLookup<Game.Areas.District> m_DistrictData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Areas.District> m_DistrictData;
```

- `private Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Vehicles.Vehicle> m_VehicleData;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.MaintenanceDepotData> m_PrefabMaintenanceDepotData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.MaintenanceDepotData> m_PrefabMaintenanceDepotData;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.MaintenanceVehicleData> m_PrefabMaintenanceVehicleData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.MaintenanceVehicleData> m_PrefabMaintenanceVehicleData;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.TrafficSpawnerData> m_PrefabTrafficSpawnerData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.TrafficSpawnerData> m_PrefabTrafficSpawnerData;
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

- `private Game.Areas.SearchSystem m_AreaSearchSystem`  

```csharp
private Game.Areas.SearchSystem m_AreaSearchSystem;
```

- `private Game.Net.SearchSystem m_NetSearchSystem`  

```csharp
private Game.Net.SearchSystem m_NetSearchSystem;
```


## Constructors

- `public RoadPathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

```csharp
public RoadPathfindSetup(Game.Simulation.PathfindSetupSystem system);
```


## Methods

- `public SetupMaintenanceProviders(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupMaintenanceProviders(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetupMaintenanceRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupMaintenanceRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetupOutsideConnections(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupOutsideConnections(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetupRandomTraffic(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupRandomTraffic(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Simulation.RoadPathfindSetup+SetupMaintenanceProvidersJob`  
- `Game.Simulation.RoadPathfindSetup+SetupRandomTrafficJob`  
- `Game.Simulation.RoadPathfindSetup+SetupOutsideConnectionsJob`  
- `Game.Simulation.RoadPathfindSetup+MaintenanceRequestsJob`  

