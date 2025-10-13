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
public GarbagePathfindSetup(PathfindSetupSystem system)
	{
		m_GarbageCollectorQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Buildings.GarbageFacility>(),
				ComponentType.ReadOnly<Game.Vehicles.GarbageTruck>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Game.Buildings.ServiceUpgrade>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_GarbageTransferQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Buildings.GarbageFacility>(),
				ComponentType.ReadOnly<ServiceDispatch>(),
				ComponentType.ReadOnly<PrefabRef>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Temp>()
			}
		}, new EntityQueryDesc
		{
			All = new ComponentType[4]
			{
				ComponentType.ReadOnly<Game.Companies.StorageCompany>(),
				ComponentType.ReadOnly<PrefabRef>(),
				ComponentType.ReadOnly<Resources>(),
				ComponentType.ReadOnly<TradeCost>()
			},
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_GarbageCollectionRequestQuery = system.GetSetupQuery(ComponentType.ReadOnly<GarbageCollectionRequest>(), ComponentType.Exclude<Dispatched>(), ComponentType.Exclude<PathInformation>());
		m_EntityType = system.GetEntityTypeHandle();
		m_PathOwnerType = system.GetComponentTypeHandle<PathOwner>(isReadOnly: true);
		m_OwnerType = system.GetComponentTypeHandle<Owner>(isReadOnly: true);
		m_OutsideConnectionType = system.GetComponentTypeHandle<Game.Objects.OutsideConnection>(isReadOnly: true);
		m_ServiceRequestType = system.GetComponentTypeHandle<ServiceRequest>(isReadOnly: true);
		m_GarbageCollectionRequestType = system.GetComponentTypeHandle<GarbageCollectionRequest>(isReadOnly: true);
		m_GarbageFacilityType = system.GetComponentTypeHandle<Game.Buildings.GarbageFacility>(isReadOnly: true);
		m_GarbageTruckType = system.GetComponentTypeHandle<Game.Vehicles.GarbageTruck>(isReadOnly: true);
		m_PrefabRefType = system.GetComponentTypeHandle<PrefabRef>(isReadOnly: true);
		m_PathElementType = system.GetBufferTypeHandle<PathElement>(isReadOnly: true);
		m_ServiceDispatchType = system.GetBufferTypeHandle<ServiceDispatch>(isReadOnly: true);
		m_ResourcesType = system.GetBufferTypeHandle<Resources>(isReadOnly: true);
		m_TradeCostType = system.GetBufferTypeHandle<TradeCost>(isReadOnly: true);
		m_InstalledUpgradeType = system.GetBufferTypeHandle<InstalledUpgrade>(isReadOnly: true);
		m_PathInformationData = system.GetComponentLookup<PathInformation>(isReadOnly: true);
		m_GarbageCollectionRequestData = system.GetComponentLookup<GarbageCollectionRequest>(isReadOnly: true);
		m_OutsideConnections = system.GetComponentLookup<Game.Objects.OutsideConnection>(isReadOnly: true);
		m_CurrentDistrictData = system.GetComponentLookup<CurrentDistrict>(isReadOnly: true);
		m_GarbageTruckData = system.GetComponentLookup<Game.Vehicles.GarbageTruck>(isReadOnly: true);
		m_StorageLimitData = system.GetComponentLookup<StorageLimitData>(isReadOnly: true);
		m_StorageCompanyData = system.GetComponentLookup<StorageCompanyData>(isReadOnly: true);
		m_CityData = system.GetComponentLookup<Game.City.City>(isReadOnly: true);
		m_PathElements = system.GetBufferLookup<PathElement>(isReadOnly: true);
		m_ServiceDistricts = system.GetBufferLookup<ServiceDistrict>(isReadOnly: true);
		m_CitySystem = system.World.GetOrCreateSystemManaged<CitySystem>();
	}
```


## Methods

- `public SetupGarbageCollector(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupGarbageCollector(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_GarbageFacilityType.Update(system);
		m_GarbageTruckType.Update(system);
		m_PathOwnerType.Update(system);
		m_OwnerType.Update(system);
		m_PathElementType.Update(system);
		m_ServiceDispatchType.Update(system);
		m_PathInformationData.Update(system);
		m_GarbageCollectionRequestData.Update(system);
		m_PathElements.Update(system);
		m_ServiceDistricts.Update(system);
		m_OutsideConnections.Update(system);
		m_CityData.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupGarbageCollectorsJob
		{
			m_EntityType = m_EntityType,
			m_GarbageFacilityType = m_GarbageFacilityType,
			m_GarbageTruckType = m_GarbageTruckType,
			m_PathOwnerType = m_PathOwnerType,
			m_OwnerType = m_OwnerType,
			m_PathElementType = m_PathElementType,
			m_ServiceDispatchType = m_ServiceDispatchType,
			m_PathInformationData = m_PathInformationData,
			m_GarbageCollectionRequestData = m_GarbageCollectionRequestData,
			m_PathElements = m_PathElements,
			m_ServiceDistricts = m_ServiceDistricts,
			m_OutsideConnections = m_OutsideConnections,
			m_CityData = m_CityData,
			m_City = m_CitySystem.City,
			m_SetupData = setupData
		}, m_GarbageCollectorQuery, inputDeps);
	}
```

- `public SetupGarbageCollectorRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupGarbageCollectorRequest(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_ServiceRequestType.Update(system);
		m_GarbageCollectionRequestType.Update(system);
		m_GarbageCollectionRequestData.Update(system);
		m_CurrentDistrictData.Update(system);
		m_GarbageTruckData.Update(system);
		m_ServiceDistricts.Update(system);
		return JobChunkExtensions.ScheduleParallel(new GarbageCollectorRequestsJob
		{
			m_EntityType = m_EntityType,
			m_ServiceRequestType = m_ServiceRequestType,
			m_GarbageCollectionRequestType = m_GarbageCollectionRequestType,
			m_GarbageCollectionRequestData = m_GarbageCollectionRequestData,
			m_CurrentDistrictData = m_CurrentDistrictData,
			m_GarbageTruckData = m_GarbageTruckData,
			m_ServiceDistricts = m_ServiceDistricts,
			m_SetupData = setupData
		}, m_GarbageCollectionRequestQuery, inputDeps);
	}
```

- `public SetupGarbageTransfer(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupGarbageTransfer(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_GarbageFacilityType.Update(system);
		m_PrefabRefType.Update(system);
		m_OutsideConnectionType.Update(system);
		m_ResourcesType.Update(system);
		m_TradeCostType.Update(system);
		m_InstalledUpgradeType.Update(system);
		m_StorageCompanyData.Update(system);
		m_StorageLimitData.Update(system);
		m_ServiceDistricts.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupGarbageTransferJob
		{
			m_EntityType = m_EntityType,
			m_GarbageFacilityType = m_GarbageFacilityType,
			m_PrefabRefType = m_PrefabRefType,
			m_OutsideConnectionType = m_OutsideConnectionType,
			m_ResourcesType = m_ResourcesType,
			m_TradeCostType = m_TradeCostType,
			m_InstalledUpgradeType = m_InstalledUpgradeType,
			m_StorageCompanyData = m_StorageCompanyData,
			m_StorageLimitData = m_StorageLimitData,
			m_ServiceDistricts = m_ServiceDistricts,
			m_SetupData = setupData
		}, m_GarbageTransferQuery, inputDeps);
	}
```


## Nested types

- `Game.Simulation.GarbagePathfindSetup+SetupGarbageCollectorsJob`  
- `Game.Simulation.GarbagePathfindSetup+SetupGarbageTransferJob`  
- `Game.Simulation.GarbagePathfindSetup+GarbageCollectorRequestsJob`  

