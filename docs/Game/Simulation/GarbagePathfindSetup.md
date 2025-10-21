# Game.Simulation.GarbagePathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct GarbagePathfindSetup
{
    private Unity.Entities.EntityQuery m_GarbageCollectorQuery;
    private Unity.Entities.EntityQuery m_GarbageTransferQuery;
    private Unity.Entities.EntityQuery m_GarbageCollectionRequestQuery;
    private Unity.Entities.EntityTypeHandle m_EntityType;
    private Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathOwner> m_PathOwnerType;
    private Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
    private Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnectionType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.GarbageCollectionRequest> m_GarbageCollectionRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Buildings.GarbageFacility> m_GarbageFacilityType;
    private Unity.Entities.ComponentTypeHandle<Game.Vehicles.GarbageTruck> m_GarbageTruckType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
    private Unity.Entities.BufferTypeHandle<Game.Pathfind.PathElement> m_PathElementType;
    private Unity.Entities.BufferTypeHandle<Game.Simulation.ServiceDispatch> m_ServiceDispatchType;
    private Unity.Entities.BufferTypeHandle<Game.Economy.Resources> m_ResourcesType;
    private Unity.Entities.BufferTypeHandle<Game.Companies.TradeCost> m_TradeCostType;
    private Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType;
    private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformationData;
    private Unity.Entities.ComponentLookup<Game.Simulation.GarbageCollectionRequest> m_GarbageCollectionRequestData;
    private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections;
    private Unity.Entities.ComponentLookup<Game.City.City> m_CityData;
    private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData;
    private Unity.Entities.ComponentLookup<Game.Vehicles.GarbageTruck> m_GarbageTruckData;
    private Unity.Entities.ComponentLookup<Game.Companies.StorageLimitData> m_StorageLimitData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.StorageCompanyData> m_StorageCompanyData;
    private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements;
    private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts;
    private Game.Simulation.CitySystem m_CitySystem;

    public GarbagePathfindSetup(Game.Simulation.PathfindSetupSystem system);

    public Unity.Jobs.JobHandle SetupGarbageCollector(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupGarbageCollectorRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupGarbageTransfer(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_GarbageCollectorQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageCollectorQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageTransferQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageTransferQuery;
```

- `private Unity.Entities.EntityQuery m_GarbageCollectionRequestQuery`  

```csharp
private Unity.Entities.EntityQuery m_GarbageCollectionRequestQuery;
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

- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.GarbageCollectionRequest> m_GarbageCollectionRequestType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Simulation.GarbageCollectionRequest> m_GarbageCollectionRequestType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.GarbageFacility> m_GarbageFacilityType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Buildings.GarbageFacility> m_GarbageFacilityType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.GarbageTruck> m_GarbageTruckType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Vehicles.GarbageTruck> m_GarbageTruckType;
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

- `private Unity.Entities.BufferTypeHandle<Game.Economy.Resources> m_ResourcesType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Economy.Resources> m_ResourcesType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Companies.TradeCost> m_TradeCostType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Companies.TradeCost> m_TradeCostType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType;
```

- `private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformationData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformationData;
```

- `private Unity.Entities.ComponentLookup<Game.Simulation.GarbageCollectionRequest> m_GarbageCollectionRequestData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Simulation.GarbageCollectionRequest> m_GarbageCollectionRequestData;
```

- `private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections`  

```csharp
private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections;
```

- `private Unity.Entities.ComponentLookup<Game.City.City> m_CityData`  

```csharp
private Unity.Entities.ComponentLookup<Game.City.City> m_CityData;
```

- `private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData;
```

- `private Unity.Entities.ComponentLookup<Game.Vehicles.GarbageTruck> m_GarbageTruckData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Vehicles.GarbageTruck> m_GarbageTruckData;
```

- `private Unity.Entities.ComponentLookup<Game.Companies.StorageLimitData> m_StorageLimitData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Companies.StorageLimitData> m_StorageLimitData;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.StorageCompanyData> m_StorageCompanyData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.StorageCompanyData> m_StorageCompanyData;
```

- `private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements`  

```csharp
private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements;
```

- `private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts`  

```csharp
private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts;
```

- `private Game.Simulation.CitySystem m_CitySystem`  

```csharp
private Game.Simulation.CitySystem m_CitySystem;
```


## Constructors

- `public GarbagePathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

```csharp
public GarbagePathfindSetup(Game.Simulation.PathfindSetupSystem system);
```


## Methods

- `public SetupGarbageCollector(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupGarbageCollector(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetupGarbageCollectorRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupGarbageCollectorRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetupGarbageTransfer(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupGarbageTransfer(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Simulation.GarbagePathfindSetup+SetupGarbageCollectorsJob`  
- `Game.Simulation.GarbagePathfindSetup+SetupGarbageTransferJob`  
- `Game.Simulation.GarbagePathfindSetup+GarbageCollectorRequestsJob`  

