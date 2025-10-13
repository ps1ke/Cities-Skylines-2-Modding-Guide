# Game.Simulation.ResourcePathfindSetup

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct ResourcePathfindSetup
{
    private Unity.Entities.EntityQuery m_ResourceSellerQuery;
    private Unity.Entities.EntityQuery m_ExportTargetQuery;
    private Unity.Entities.EntityQuery m_StorageQuery;
    private Game.Prefabs.ResourceSystem m_ResourceSystem;
    private Unity.Entities.EntityTypeHandle m_EntityType;
    private Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnectionType;
    private Unity.Entities.ComponentTypeHandle<Game.Companies.StorageCompany> m_StorageCompanyType;
    private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabType;
    private Unity.Entities.BufferTypeHandle<Game.Companies.TradeCost> m_TradeCostType;
    private Unity.Entities.BufferTypeHandle<Game.Companies.StorageTransferRequest> m_StorageTransferRequestType;
    private Unity.Entities.BufferTypeHandle<Game.Economy.Resources> m_ResourceType;
    private Unity.Entities.BufferTypeHandle<Game.Vehicles.OwnedVehicle> m_OwnedVehicleType;
    private Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType;
    private Unity.Entities.BufferTypeHandle<Game.Citizens.TripNeeded> m_TripNeededType;
    private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections;
    private Unity.Entities.ComponentLookup<Game.Companies.ServiceCompanyData> m_ServiceCompanies;
    private Unity.Entities.ComponentLookup<Game.Companies.ServiceAvailable> m_ServiceAvailables;
    private Unity.Entities.ComponentLookup<Game.Companies.StorageCompany> m_StorageCompanys;
    private Unity.Entities.ComponentLookup<Game.Companies.StorageLimitData> m_StorageLimits;
    private Unity.Entities.ComponentLookup<Game.Companies.TransportCompanyData> m_TransportCompanyData;
    private Unity.Entities.ComponentLookup<Game.Buildings.CargoTransportStation> m_CargoTransportStations;
    private Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters;
    private Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs;
    private Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_IndustrialProcessDatas;
    private Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDatas;
    private Unity.Entities.ComponentLookup<Game.Prefabs.StorageCompanyData> m_StorageCompanyDatas;
    private Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableBuildingDatas;
    private Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_BuildingDatas;
    private Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Buildings;
    private Unity.Entities.ComponentLookup<Game.Vehicles.DeliveryTruck> m_DeliveryTrucks;
    private Unity.Entities.BufferLookup<Game.Economy.Resources> m_Resources;
    private Unity.Entities.BufferLookup<Game.Companies.TradeCost> m_TradeCosts;
    private Unity.Entities.BufferLookup<Game.Vehicles.GuestVehicle> m_GuestVehicleBufs;
    private Unity.Entities.BufferLookup<Game.Vehicles.LayoutElement> m_LayoutElementBufs;
    public static readonly System.Single kOutsideConnectionAmountBasedPenalty;
    public static readonly System.Single kCargoStationAmountBasedPenalty;
    public static readonly System.Single kCargoStationPerRequestPenalty;
    public static readonly System.Int32 kCargoStationVehiclePenalty;
    public static readonly System.Int32 kCargoStationMaxRequestAmount;
    public static readonly System.Int32 kCargoStationMaxTripNeededQueue;

    public ResourcePathfindSetup(Game.Simulation.PathfindSetupSystem system);

    public Unity.Jobs.JobHandle SetupResourceExport(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupResourceSeller(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
    public Unity.Jobs.JobHandle SetupStorageTransfer(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps);
}
```


## Fields

- `private Unity.Entities.EntityQuery m_ResourceSellerQuery`  

```csharp
private Unity.Entities.EntityQuery m_ResourceSellerQuery;
```

- `private Unity.Entities.EntityQuery m_ExportTargetQuery`  

```csharp
private Unity.Entities.EntityQuery m_ExportTargetQuery;
```

- `private Unity.Entities.EntityQuery m_StorageQuery`  

```csharp
private Unity.Entities.EntityQuery m_StorageQuery;
```

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```

- `private Unity.Entities.EntityTypeHandle m_EntityType`  

```csharp
private Unity.Entities.EntityTypeHandle m_EntityType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnectionType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Objects.OutsideConnection> m_OutsideConnectionType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Companies.StorageCompany> m_StorageCompanyType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Companies.StorageCompany> m_StorageCompanyType;
```

- `private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabType`  

```csharp
private Unity.Entities.ComponentTypeHandle<Game.Prefabs.PrefabRef> m_PrefabType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Companies.TradeCost> m_TradeCostType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Companies.TradeCost> m_TradeCostType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Companies.StorageTransferRequest> m_StorageTransferRequestType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Companies.StorageTransferRequest> m_StorageTransferRequestType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Economy.Resources> m_ResourceType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Economy.Resources> m_ResourceType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Vehicles.OwnedVehicle> m_OwnedVehicleType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Vehicles.OwnedVehicle> m_OwnedVehicleType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Buildings.InstalledUpgrade> m_InstalledUpgradeType;
```

- `private Unity.Entities.BufferTypeHandle<Game.Citizens.TripNeeded> m_TripNeededType`  

```csharp
private Unity.Entities.BufferTypeHandle<Game.Citizens.TripNeeded> m_TripNeededType;
```

- `private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections`  

```csharp
private Unity.Entities.ComponentLookup<Game.Objects.OutsideConnection> m_OutsideConnections;
```

- `private Unity.Entities.ComponentLookup<Game.Companies.ServiceCompanyData> m_ServiceCompanies`  

```csharp
private Unity.Entities.ComponentLookup<Game.Companies.ServiceCompanyData> m_ServiceCompanies;
```

- `private Unity.Entities.ComponentLookup<Game.Companies.ServiceAvailable> m_ServiceAvailables`  

```csharp
private Unity.Entities.ComponentLookup<Game.Companies.ServiceAvailable> m_ServiceAvailables;
```

- `private Unity.Entities.ComponentLookup<Game.Companies.StorageCompany> m_StorageCompanys`  

```csharp
private Unity.Entities.ComponentLookup<Game.Companies.StorageCompany> m_StorageCompanys;
```

- `private Unity.Entities.ComponentLookup<Game.Companies.StorageLimitData> m_StorageLimits`  

```csharp
private Unity.Entities.ComponentLookup<Game.Companies.StorageLimitData> m_StorageLimits;
```

- `private Unity.Entities.ComponentLookup<Game.Companies.TransportCompanyData> m_TransportCompanyData`  

```csharp
private Unity.Entities.ComponentLookup<Game.Companies.TransportCompanyData> m_TransportCompanyData;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.CargoTransportStation> m_CargoTransportStations`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.CargoTransportStation> m_CargoTransportStations;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenters;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_Prefabs;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_IndustrialProcessDatas`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.IndustrialProcessData> m_IndustrialProcessDatas;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDatas`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.ResourceData> m_ResourceDatas;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.StorageCompanyData> m_StorageCompanyDatas`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.StorageCompanyData> m_StorageCompanyDatas;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableBuildingDatas`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.SpawnableBuildingData> m_SpawnableBuildingDatas;
```

- `private Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_BuildingDatas`  

```csharp
private Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_BuildingDatas;
```

- `private Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Buildings`  

```csharp
private Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Buildings;
```

- `private Unity.Entities.ComponentLookup<Game.Vehicles.DeliveryTruck> m_DeliveryTrucks`  

```csharp
private Unity.Entities.ComponentLookup<Game.Vehicles.DeliveryTruck> m_DeliveryTrucks;
```

- `private Unity.Entities.BufferLookup<Game.Economy.Resources> m_Resources`  

```csharp
private Unity.Entities.BufferLookup<Game.Economy.Resources> m_Resources;
```

- `private Unity.Entities.BufferLookup<Game.Companies.TradeCost> m_TradeCosts`  

```csharp
private Unity.Entities.BufferLookup<Game.Companies.TradeCost> m_TradeCosts;
```

- `private Unity.Entities.BufferLookup<Game.Vehicles.GuestVehicle> m_GuestVehicleBufs`  

```csharp
private Unity.Entities.BufferLookup<Game.Vehicles.GuestVehicle> m_GuestVehicleBufs;
```

- `private Unity.Entities.BufferLookup<Game.Vehicles.LayoutElement> m_LayoutElementBufs`  

```csharp
private Unity.Entities.BufferLookup<Game.Vehicles.LayoutElement> m_LayoutElementBufs;
```

- `public static readonly System.Single kOutsideConnectionAmountBasedPenalty`  

```csharp
public static readonly System.Single kOutsideConnectionAmountBasedPenalty;
```

- `public static readonly System.Single kCargoStationAmountBasedPenalty`  

```csharp
public static readonly System.Single kCargoStationAmountBasedPenalty;
```

- `public static readonly System.Single kCargoStationPerRequestPenalty`  

```csharp
public static readonly System.Single kCargoStationPerRequestPenalty;
```

- `public static readonly System.Int32 kCargoStationVehiclePenalty`  

```csharp
public static readonly System.Int32 kCargoStationVehiclePenalty;
```

- `public static readonly System.Int32 kCargoStationMaxRequestAmount`  

```csharp
public static readonly System.Int32 kCargoStationMaxRequestAmount;
```

- `public static readonly System.Int32 kCargoStationMaxTripNeededQueue`  

```csharp
public static readonly System.Int32 kCargoStationMaxTripNeededQueue;
```


## Constructors

- `public ResourcePathfindSetup(Game.Simulation.PathfindSetupSystem system)`  

```csharp
public ResourcePathfindSetup(PathfindSetupSystem system)
	{
		m_ResourceSystem = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<ResourceSystem>();
		m_ResourceSellerQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadOnly<Game.Economy.Resources>()
			},
			Any = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Companies.StorageCompany>(),
				ComponentType.ReadOnly<Game.Buildings.CargoTransportStation>(),
				ComponentType.ReadOnly<ResourceSeller>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_ExportTargetQuery = system.GetSetupQuery(ComponentType.ReadOnly<Game.Companies.StorageCompany>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.ReadOnly<Game.Economy.Resources>(), ComponentType.ReadOnly<TradeCost>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Temp>());
		m_StorageQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			All = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Companies.StorageCompany>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Game.Companies.ProcessingCompany>(),
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_EntityType = system.GetEntityTypeHandle();
		m_OutsideConnectionType = system.GetComponentTypeHandle<Game.Objects.OutsideConnection>(isReadOnly: true);
		m_StorageCompanyType = system.GetComponentTypeHandle<Game.Companies.StorageCompany>(isReadOnly: true);
		m_PrefabType = system.GetComponentTypeHandle<PrefabRef>(isReadOnly: true);
		m_TradeCostType = system.GetBufferTypeHandle<TradeCost>(isReadOnly: true);
		m_StorageTransferRequestType = system.GetBufferTypeHandle<StorageTransferRequest>(isReadOnly: true);
		m_TripNeededType = system.GetBufferTypeHandle<TripNeeded>(isReadOnly: true);
		m_OwnedVehicleType = system.GetBufferTypeHandle<OwnedVehicle>(isReadOnly: true);
		m_ResourceType = system.GetBufferTypeHandle<Game.Economy.Resources>(isReadOnly: true);
		m_InstalledUpgradeType = system.GetBufferTypeHandle<InstalledUpgrade>(isReadOnly: true);
		m_OutsideConnections = system.GetComponentLookup<Game.Objects.OutsideConnection>(isReadOnly: true);
		m_ServiceCompanies = system.GetComponentLookup<ServiceCompanyData>(isReadOnly: true);
		m_ServiceAvailables = system.GetComponentLookup<ServiceAvailable>(isReadOnly: true);
		m_StorageCompanys = system.GetComponentLookup<Game.Companies.StorageCompany>(isReadOnly: true);
		m_StorageLimits = system.GetComponentLookup<StorageLimitData>(isReadOnly: true);
		m_TransportCompanyData = system.GetComponentLookup<TransportCompanyData>(isReadOnly: true);
		m_PropertyRenters = system.GetComponentLookup<PropertyRenter>(isReadOnly: true);
		m_Prefabs = system.GetComponentLookup<PrefabRef>(isReadOnly: true);
		m_IndustrialProcessDatas = system.GetComponentLookup<IndustrialProcessData>(isReadOnly: true);
		m_ResourceDatas = system.GetComponentLookup<ResourceData>(isReadOnly: true);
		m_StorageCompanyDatas = system.GetComponentLookup<StorageCompanyData>(isReadOnly: true);
		m_SpawnableBuildingDatas = system.GetComponentLookup<SpawnableBuildingData>(isReadOnly: true);
		m_BuildingDatas = system.GetComponentLookup<BuildingData>(isReadOnly: true);
		m_Buildings = system.GetComponentLookup<Building>(isReadOnly: true);
		m_DeliveryTrucks = system.GetComponentLookup<Game.Vehicles.DeliveryTruck>(isReadOnly: true);
		m_Resources = system.GetBufferLookup<Game.Economy.Resources>(isReadOnly: true);
		m_TradeCosts = system.GetBufferLookup<TradeCost>(isReadOnly: true);
		m_GuestVehicleBufs = system.GetBufferLookup<GuestVehicle>(isReadOnly: true);
		m_LayoutElementBufs = system.GetBufferLookup<LayoutElement>(isReadOnly: true);
		m_CargoTransportStations = system.GetComponentLookup<Game.Buildings.CargoTransportStation>(isReadOnly: true);
	}
```


## Methods

- `public SetupResourceExport(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupResourceExport(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_StorageLimits.Update(system);
		m_PrefabType.Update(system);
		m_ResourceType.Update(system);
		m_OwnedVehicleType.Update(system);
		m_TripNeededType.Update(system);
		m_TradeCostType.Update(system);
		m_InstalledUpgradeType.Update(system);
		m_StorageCompanyDatas.Update(system);
		m_TransportCompanyData.Update(system);
		m_BuildingDatas.Update(system);
		m_SpawnableBuildingDatas.Update(system);
		m_Prefabs.Update(system);
		m_PropertyRenters.Update(system);
		m_CargoTransportStations.Update(system);
		m_Buildings.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupResourceExportJob
		{
			m_EntityType = m_EntityType,
			m_Limits = m_StorageLimits,
			m_PrefabType = m_PrefabType,
			m_ResourceType = m_ResourceType,
			m_OwnedVehicles = m_OwnedVehicleType,
			m_TripNeededType = m_TripNeededType,
			m_TradeCosts = m_TradeCostType,
			m_InstalledUpgradeType = m_InstalledUpgradeType,
			m_StorageCompanyDatas = m_StorageCompanyDatas,
			m_TransportCompanyData = m_TransportCompanyData,
			m_BuildingDatas = m_BuildingDatas,
			m_SpawnableBuildingData = m_SpawnableBuildingDatas,
			m_Prefabs = m_Prefabs,
			m_Properties = m_PropertyRenters,
			m_CargoTransportStations = m_CargoTransportStations,
			m_Buildings = m_Buildings,
			m_SetupData = setupData
		}, m_ExportTargetQuery, inputDeps);
	}
```

- `public SetupResourceSeller(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupResourceSeller(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_Resources.Update(system);
		m_IndustrialProcessDatas.Update(system);
		m_CargoTransportStations.Update(system);
		m_StorageCompanyDatas.Update(system);
		m_PropertyRenters.Update(system);
		m_TradeCosts.Update(system);
		m_ServiceAvailables.Update(system);
		m_OutsideConnections.Update(system);
		m_StorageTransferRequestType.Update(system);
		m_TripNeededType.Update(system);
		m_Prefabs.Update(system);
		m_Buildings.Update(system);
		m_DeliveryTrucks.Update(system);
		m_GuestVehicleBufs.Update(system);
		m_LayoutElementBufs.Update(system);
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new SetupResourceSellerJob
		{
			m_EntityType = m_EntityType,
			m_StorageTransferRequestType = m_StorageTransferRequestType,
			m_TripNeededType = m_TripNeededType,
			m_Resources = m_Resources,
			m_IndustrialProcessDatas = m_IndustrialProcessDatas,
			m_CargoTransportStations = m_CargoTransportStations,
			m_StorageCompanyDatas = m_StorageCompanyDatas,
			m_PropertyRenters = m_PropertyRenters,
			m_TradeCosts = m_TradeCosts,
			m_ServiceAvailables = m_ServiceAvailables,
			m_OutsideConnections = m_OutsideConnections,
			m_Prefabs = m_Prefabs,
			m_Buildings = m_Buildings,
			m_DeliveryTrucks = m_DeliveryTrucks,
			m_GuestVehicleBufs = m_GuestVehicleBufs,
			m_LayoutElementBufs = m_LayoutElementBufs,
			m_SetupData = setupData
		}, m_ResourceSellerQuery, inputDeps);
		m_ResourceSystem.AddPrefabsReader(jobHandle);
		return jobHandle;
	}
```

- `public SetupStorageTransfer(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupStorageTransfer(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_StorageCompanyType.Update(system);
		m_OutsideConnectionType.Update(system);
		m_CargoTransportStations.Update(system);
		m_PrefabType.Update(system);
		m_ResourceType.Update(system);
		m_TradeCostType.Update(system);
		m_InstalledUpgradeType.Update(system);
		m_StorageTransferRequestType.Update(system);
		m_TripNeededType.Update(system);
		m_OwnedVehicleType.Update(system);
		m_Buildings.Update(system);
		m_StorageLimits.Update(system);
		m_StorageCompanyDatas.Update(system);
		m_TransportCompanyData.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupStorageTransferJob
		{
			m_EntityType = m_EntityType,
			m_StorageType = m_StorageCompanyType,
			m_OutsideConnectionType = m_OutsideConnectionType,
			m_CargoTransportStations = m_CargoTransportStations,
			m_PrefabType = m_PrefabType,
			m_ResourceType = m_ResourceType,
			m_TradeCostType = m_TradeCostType,
			m_InstalledUpgradeType = m_InstalledUpgradeType,
			m_StorageTransferRequestType = m_StorageTransferRequestType,
			m_TripNeededType = m_TripNeededType,
			m_OwnedVehicleType = m_OwnedVehicleType,
			m_Buildings = m_Buildings,
			m_StorageLimits = m_StorageLimits,
			m_StorageCompanyDatas = m_StorageCompanyDatas,
			m_TransportCompanyDatas = m_TransportCompanyData,
			m_SetupData = setupData
		}, m_StorageQuery, inputDeps);
	}
```


## Nested types

- `Game.Simulation.ResourcePathfindSetup+SetupResourceSellerJob`  
- `Game.Simulation.ResourcePathfindSetup+SetupResourceExportJob`  
- `Game.Simulation.ResourcePathfindSetup+SetupStorageTransferJob`  

