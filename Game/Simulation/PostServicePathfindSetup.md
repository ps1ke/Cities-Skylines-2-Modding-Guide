# Game.Simulation.PostServicePathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct PostServicePathfindSetup
{
    private Unity.Entities.EntityQuery m_PostVanQuery;
    private Unity.Entities.EntityQuery m_MailTransferQuery;
    private Unity.Entities.EntityQuery m_MailBoxQuery;
    private Unity.Entities.EntityQuery m_PostVanRequestQuery;
    private Unity.Entities.EntityTypeHandle m_EntityType;
    private Unity.Entities.ComponentTypeHandle<Game.Pathfind.PathOwner> m_PathOwnerType;
    private Unity.Entities.ComponentTypeHandle<Game.Common.Owner> m_OwnerType;
    private Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnectionType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.ServiceRequest> m_ServiceRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Simulation.PostVanRequest> m_PostVanRequestType;
    private Unity.Entities.ComponentTypeHandle<Game.Buildings.PostFacility> m_PostFacilityType;
    private Unity.Entities.ComponentTypeHandle<Game.Vehicles.PostVan> m_PostVanType;
    private Unity.Entities.ComponentTypeHandle<Game.Routes.MailBox> m_MailBoxType;
    private Unity.Entities.ComponentTypeHandle<Game.Routes.TransportStop> m_TransportStopType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabRefType;
    private Unity.Entities.BufferTypeHandle<Game.Pathfind.PathElement> m_PathElementType;
    private Unity.Entities.BufferTypeHandle<Game.Simulation.ServiceDispatch> m_ServiceDispatchType;
    private Unity.Entities.BufferTypeHandle<Game.Economy.Resources> m_ResourcesType;
    private Unity.Entities.BufferTypeHandle<Game.Companies.TradeCost> m_TradeCostType;
    private Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType;
    private Unity.Entities.ComponentLookup<Game.Pathfind.PathInformation> m_PathInformationData;
    private Unity.Entities.ComponentLookup<Game.Simulation.PostVanRequest> m_PostVanRequestData;
    private Unity.Entities.ComponentLookup<Game.Buildings.PostFacility> m_PostFacilityData;
    private Unity.Entities.ComponentLookup<Game.Vehicles.PostVan> m_PostVanData;
    private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData;
    private Unity.Entities.ComponentLookup<Game.Companies.StorageLimitData> m_StorageLimitData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.StorageCompanyData> m_StorageCompanyData;
    private Unity.Entities.ComponentLookup<Game.Prefabs.MailBoxData> m_MailBoxData;
    private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements;
    private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts;

    public PostServicePathfindSetup(Game.Simulation.PathfindSetupSystem system);

    public Unity.Jobs.JobHandle SetupMailBoxes(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupMailTransfer(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupPostVanRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupPostVans(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_PostVanQuery`  

```csharp
private Unity.Entities.EntityQuery m_PostVanQuery;
```

- `private Unity.Entities.EntityQuery m_MailTransferQuery`  

```csharp
private Unity.Entities.EntityQuery m_MailTransferQuery;
```

- `private Unity.Entities.EntityQuery m_MailBoxQuery`  

```csharp
private Unity.Entities.EntityQuery m_MailBoxQuery;
```

- `private Unity.Entities.EntityQuery m_PostVanRequestQuery`  

```csharp
private Unity.Entities.EntityQuery m_PostVanRequestQuery;
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

- `private Unity.Entities.ComponentTypeHandle<Game.Simulation.PostVanRequest> m_PostVanRequestType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Simulation.PostVanRequest> m_PostVanRequestType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Buildings.PostFacility> m_PostFacilityType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Buildings.PostFacility> m_PostFacilityType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Vehicles.PostVan> m_PostVanType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Vehicles.PostVan> m_PostVanType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Routes.MailBox> m_MailBoxType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Routes.MailBox> m_MailBoxType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Routes.TransportStop> m_TransportStopType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Routes.TransportStop> m_TransportStopType;
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

- `private Unity.Entities.ComponentLookup<Game.Simulation.PostVanRequest> m_PostVanRequestData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Simulation.PostVanRequest> m_PostVanRequestData;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.PostFacility> m_PostFacilityData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.PostFacility> m_PostFacilityData;
```

- `private Unity.Entities.ComponentLookup<Game.Vehicles.PostVan> m_PostVanData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Vehicles.PostVan> m_PostVanData;
```

- `private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Areas.CurrentDistrict> m_CurrentDistrictData;
```

- `private Unity.Entities.ComponentLookup<Game.Companies.StorageLimitData> m_StorageLimitData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Companies.StorageLimitData> m_StorageLimitData;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.StorageCompanyData> m_StorageCompanyData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.StorageCompanyData> m_StorageCompanyData;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.MailBoxData> m_MailBoxData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.MailBoxData> m_MailBoxData;
```

- `private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements`  

```csharp
private Unity.Entities.BufferLookup<Game.Pathfind.PathElement> m_PathElements;
```

- `private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts`  

```csharp
private Unity.Entities.BufferLookup<Game.Areas.ServiceDistrict> m_ServiceDistricts;
```


## Constructors

- `public PostServicePathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

```csharp
public PostServicePathfindSetup(Game.Simulation.PathfindSetupSystem system);
```


## Methods

- `public SetupMailBoxes(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupMailBoxes(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetupMailTransfer(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupMailTransfer(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetupPostVanRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupPostVanRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```

- `public SetupPostVans(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public Unity.Jobs.JobHandle SetupPostVans(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
```


## Nested types

- `Game.Simulation.PostServicePathfindSetup+SetupPostVansJob`  
- `Game.Simulation.PostServicePathfindSetup+SetupMailTransferJob`  
- `Game.Simulation.PostServicePathfindSetup+SetupMailBoxesJob`  
- `Game.Simulation.PostServicePathfindSetup+PostVanRequestsJob`  

