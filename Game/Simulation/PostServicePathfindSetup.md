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
public PostServicePathfindSetup(PathfindSetupSystem system)
	{
		m_PostVanQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Buildings.PostFacility>(),
				ComponentType.ReadOnly<Game.Vehicles.PostVan>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Game.Buildings.ServiceUpgrade>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_MailTransferQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			All = new ComponentType[3]
			{
				ComponentType.ReadOnly<Game.Buildings.PostFacility>(),
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
		m_MailBoxQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<PrefabRef>() },
			Any = new ComponentType[1] { ComponentType.ReadOnly<Game.Routes.MailBox>() },
			None = new ComponentType[3]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_PostVanRequestQuery = system.GetSetupQuery(ComponentType.ReadOnly<PostVanRequest>(), ComponentType.Exclude<Dispatched>(), ComponentType.Exclude<PathInformation>());
		m_EntityType = system.GetEntityTypeHandle();
		m_PathOwnerType = system.GetComponentTypeHandle<PathOwner>(isReadOnly: true);
		m_OwnerType = system.GetComponentTypeHandle<Owner>(isReadOnly: true);
		m_OutsideConnectionType = system.GetComponentTypeHandle<Game.Objects.OutsideConnection>(isReadOnly: true);
		m_ServiceRequestType = system.GetComponentTypeHandle<ServiceRequest>(isReadOnly: true);
		m_PostVanRequestType = system.GetComponentTypeHandle<PostVanRequest>(isReadOnly: true);
		m_PostFacilityType = system.GetComponentTypeHandle<Game.Buildings.PostFacility>(isReadOnly: true);
		m_PostVanType = system.GetComponentTypeHandle<Game.Vehicles.PostVan>(isReadOnly: true);
		m_MailBoxType = system.GetComponentTypeHandle<Game.Routes.MailBox>(isReadOnly: true);
		m_TransportStopType = system.GetComponentTypeHandle<Game.Routes.TransportStop>(isReadOnly: true);
		m_PrefabRefType = system.GetComponentTypeHandle<PrefabRef>(isReadOnly: true);
		m_PathElementType = system.GetBufferTypeHandle<PathElement>(isReadOnly: true);
		m_ServiceDispatchType = system.GetBufferTypeHandle<ServiceDispatch>(isReadOnly: true);
		m_ResourcesType = system.GetBufferTypeHandle<Resources>(isReadOnly: true);
		m_TradeCostType = system.GetBufferTypeHandle<TradeCost>(isReadOnly: true);
		m_InstalledUpgradeType = system.GetBufferTypeHandle<InstalledUpgrade>(isReadOnly: true);
		m_PathInformationData = system.GetComponentLookup<PathInformation>(isReadOnly: true);
		m_PostVanRequestData = system.GetComponentLookup<PostVanRequest>(isReadOnly: true);
		m_PostFacilityData = system.GetComponentLookup<Game.Buildings.PostFacility>(isReadOnly: true);
		m_PostVanData = system.GetComponentLookup<Game.Vehicles.PostVan>(isReadOnly: true);
		m_CurrentDistrictData = system.GetComponentLookup<CurrentDistrict>(isReadOnly: true);
		m_StorageLimitData = system.GetComponentLookup<StorageLimitData>(isReadOnly: true);
		m_StorageCompanyData = system.GetComponentLookup<StorageCompanyData>(isReadOnly: true);
		m_MailBoxData = system.GetComponentLookup<MailBoxData>(isReadOnly: true);
		m_PathElements = system.GetBufferLookup<PathElement>(isReadOnly: true);
		m_ServiceDistricts = system.GetBufferLookup<ServiceDistrict>(isReadOnly: true);
	}
```


## Methods

- `public SetupMailBoxes(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupMailBoxes(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_PrefabRefType.Update(system);
		m_MailBoxType.Update(system);
		m_TransportStopType.Update(system);
		m_MailBoxData.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupMailBoxesJob
		{
			m_EntityType = m_EntityType,
			m_PrefabRefType = m_PrefabRefType,
			m_MailBoxType = m_MailBoxType,
			m_TransportStopType = m_TransportStopType,
			m_MailBoxData = m_MailBoxData,
			m_SetupData = setupData
		}, m_MailBoxQuery, inputDeps);
	}
```

- `public SetupMailTransfer(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupMailTransfer(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_PostFacilityType.Update(system);
		m_PrefabRefType.Update(system);
		m_OutsideConnectionType.Update(system);
		m_ResourcesType.Update(system);
		m_TradeCostType.Update(system);
		m_InstalledUpgradeType.Update(system);
		m_StorageCompanyData.Update(system);
		m_StorageLimitData.Update(system);
		m_ServiceDistricts.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupMailTransferJob
		{
			m_EntityType = m_EntityType,
			m_PostFacilityType = m_PostFacilityType,
			m_PrefabRefType = m_PrefabRefType,
			m_OutsideConnectionType = m_OutsideConnectionType,
			m_ResourcesType = m_ResourcesType,
			m_TradeCostType = m_TradeCostType,
			m_InstalledUpgradeType = m_InstalledUpgradeType,
			m_StorageCompanyData = m_StorageCompanyData,
			m_StorageLimitData = m_StorageLimitData,
			m_ServiceDistricts = m_ServiceDistricts,
			m_SetupData = setupData
		}, m_MailTransferQuery, inputDeps);
	}
```

- `public SetupPostVanRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupPostVanRequest(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_ServiceRequestType.Update(system);
		m_PostVanRequestType.Update(system);
		m_PostVanRequestData.Update(system);
		m_CurrentDistrictData.Update(system);
		m_PostFacilityData.Update(system);
		m_PostVanData.Update(system);
		m_ServiceDistricts.Update(system);
		return JobChunkExtensions.ScheduleParallel(new PostVanRequestsJob
		{
			m_EntityType = m_EntityType,
			m_ServiceRequestType = m_ServiceRequestType,
			m_PostVanRequestType = m_PostVanRequestType,
			m_PostVanRequestData = m_PostVanRequestData,
			m_CurrentDistrictData = m_CurrentDistrictData,
			m_PostFacilityData = m_PostFacilityData,
			m_PostVanData = m_PostVanData,
			m_ServiceDistricts = m_ServiceDistricts,
			m_SetupData = setupData
		}, m_PostVanRequestQuery, inputDeps);
	}
```

- `public SetupPostVans(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupPostVans(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_PostFacilityType.Update(system);
		m_PostVanType.Update(system);
		m_PathOwnerType.Update(system);
		m_OwnerType.Update(system);
		m_PathElementType.Update(system);
		m_ServiceDispatchType.Update(system);
		m_PathInformationData.Update(system);
		m_PathElements.Update(system);
		m_ServiceDistricts.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupPostVansJob
		{
			m_EntityType = m_EntityType,
			m_PostFacilityType = m_PostFacilityType,
			m_PostVanType = m_PostVanType,
			m_PathOwnerType = m_PathOwnerType,
			m_OwnerType = m_OwnerType,
			m_PathElementType = m_PathElementType,
			m_ServiceDispatchType = m_ServiceDispatchType,
			m_PathInformationData = m_PathInformationData,
			m_PathElements = m_PathElements,
			m_ServiceDistricts = m_ServiceDistricts,
			m_SetupData = setupData
		}, m_PostVanQuery, inputDeps);
	}
```


## Nested types

- `Game.Simulation.PostServicePathfindSetup+SetupPostVansJob`  
- `Game.Simulation.PostServicePathfindSetup+SetupMailTransferJob`  
- `Game.Simulation.PostServicePathfindSetup+SetupMailBoxesJob`  
- `Game.Simulation.PostServicePathfindSetup+PostVanRequestsJob`  

