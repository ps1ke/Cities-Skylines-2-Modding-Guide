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
public RoadPathfindSetup(PathfindSetupSystem system)
	{
		m_MaintenanceProviderQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			Any = new ComponentType[2]
			{
				ComponentType.ReadOnly<Game.Buildings.MaintenanceDepot>(),
				ComponentType.ReadOnly<Game.Vehicles.MaintenanceVehicle>()
			},
			None = new ComponentType[4]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Game.Buildings.ServiceUpgrade>(),
				ComponentType.ReadOnly<Temp>()
			}
		});
		m_RandomTrafficQuery = system.GetSetupQuery(ComponentType.ReadOnly<Game.Buildings.TrafficSpawner>(), ComponentType.ReadOnly<PrefabRef>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Destroyed>(), ComponentType.Exclude<Temp>());
		m_OutsideConnectionQuery = system.GetSetupQuery(new EntityQueryDesc
		{
			All = new ComponentType[1] { ComponentType.ReadOnly<Game.Objects.OutsideConnection>() },
			None = new ComponentType[5]
			{
				ComponentType.ReadOnly<Deleted>(),
				ComponentType.ReadOnly<Destroyed>(),
				ComponentType.ReadOnly<Temp>(),
				ComponentType.ReadOnly<Game.Objects.ElectricityOutsideConnection>(),
				ComponentType.ReadOnly<Game.Objects.WaterPipeOutsideConnection>()
			}
		});
		m_MaintenanceRequestQuery = system.GetSetupQuery(ComponentType.ReadOnly<MaintenanceRequest>(), ComponentType.Exclude<Dispatched>(), ComponentType.Exclude<PathInformation>());
		m_EntityType = system.GetEntityTypeHandle();
		m_PathOwnerType = system.GetComponentTypeHandle<PathOwner>(isReadOnly: true);
		m_OwnerType = system.GetComponentTypeHandle<Owner>(isReadOnly: true);
		m_OutsideConnectionType = system.GetComponentTypeHandle<Game.Objects.OutsideConnection>(isReadOnly: true);
		m_ServiceRequestType = system.GetComponentTypeHandle<ServiceRequest>(isReadOnly: true);
		m_MaintenanceRequestType = system.GetComponentTypeHandle<MaintenanceRequest>(isReadOnly: true);
		m_MaintenanceDepotType = system.GetComponentTypeHandle<Game.Buildings.MaintenanceDepot>(isReadOnly: true);
		m_MaintenanceVehicleType = system.GetComponentTypeHandle<Game.Vehicles.MaintenanceVehicle>(isReadOnly: true);
		m_PrefabRefType = system.GetComponentTypeHandle<PrefabRef>(isReadOnly: true);
		m_PathElementType = system.GetBufferTypeHandle<PathElement>(isReadOnly: true);
		m_ServiceDispatchType = system.GetBufferTypeHandle<ServiceDispatch>(isReadOnly: true);
		m_PathInformationData = system.GetComponentLookup<PathInformation>(isReadOnly: true);
		m_RandomTrafficRequestData = system.GetComponentLookup<RandomTrafficRequest>(isReadOnly: true);
		m_MaintenanceRequestData = system.GetComponentLookup<MaintenanceRequest>(isReadOnly: true);
		m_SurfaceData = system.GetComponentLookup<Game.Objects.Surface>(isReadOnly: true);
		m_ParkData = system.GetComponentLookup<Game.Buildings.Park>(isReadOnly: true);
		m_EdgeData = system.GetComponentLookup<Game.Net.Edge>(isReadOnly: true);
		m_NetConditionData = system.GetComponentLookup<NetCondition>(isReadOnly: true);
		m_CompositionData = system.GetComponentLookup<Composition>(isReadOnly: true);
		m_CurrentDistrictData = system.GetComponentLookup<CurrentDistrict>(isReadOnly: true);
		m_BorderDistrictData = system.GetComponentLookup<BorderDistrict>(isReadOnly: true);
		m_DistrictData = system.GetComponentLookup<District>(isReadOnly: true);
		m_VehicleData = system.GetComponentLookup<Vehicle>(isReadOnly: true);
		m_PrefabMaintenanceDepotData = system.GetComponentLookup<MaintenanceDepotData>(isReadOnly: true);
		m_PrefabMaintenanceVehicleData = system.GetComponentLookup<MaintenanceVehicleData>(isReadOnly: true);
		m_PrefabTrafficSpawnerData = system.GetComponentLookup<TrafficSpawnerData>(isReadOnly: true);
		m_NetCompositionData = system.GetComponentLookup<NetCompositionData>(isReadOnly: true);
		m_PathElements = system.GetBufferLookup<PathElement>(isReadOnly: true);
		m_ServiceDistricts = system.GetBufferLookup<ServiceDistrict>(isReadOnly: true);
		m_AreaSearchSystem = system.World.GetOrCreateSystemManaged<Game.Areas.SearchSystem>();
		m_NetSearchSystem = system.World.GetOrCreateSystemManaged<Game.Net.SearchSystem>();
	}
```


## Methods

- `public SetupMaintenanceProviders(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupMaintenanceProviders(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_PrefabRefType.Update(system);
		m_MaintenanceDepotType.Update(system);
		m_MaintenanceVehicleType.Update(system);
		m_PathOwnerType.Update(system);
		m_OwnerType.Update(system);
		m_PathElementType.Update(system);
		m_ServiceDispatchType.Update(system);
		m_PathInformationData.Update(system);
		m_PrefabMaintenanceDepotData.Update(system);
		m_PrefabMaintenanceVehicleData.Update(system);
		m_PathElements.Update(system);
		m_ServiceDistricts.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupMaintenanceProvidersJob
		{
			m_EntityType = m_EntityType,
			m_PrefabRefType = m_PrefabRefType,
			m_MaintenanceDepotType = m_MaintenanceDepotType,
			m_MaintenanceVehicleType = m_MaintenanceVehicleType,
			m_PathOwnerType = m_PathOwnerType,
			m_OwnerType = m_OwnerType,
			m_PathElementType = m_PathElementType,
			m_ServiceDispatchType = m_ServiceDispatchType,
			m_PathInformationData = m_PathInformationData,
			m_PrefabMaintenanceDepotData = m_PrefabMaintenanceDepotData,
			m_PrefabMaintenanceVehicleData = m_PrefabMaintenanceVehicleData,
			m_PathElements = m_PathElements,
			m_ServiceDistricts = m_ServiceDistricts,
			m_SetupData = setupData
		}, m_MaintenanceProviderQuery, inputDeps);
	}
```

- `public SetupMaintenanceRequest(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupMaintenanceRequest(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_ServiceRequestType.Update(system);
		m_MaintenanceRequestType.Update(system);
		m_MaintenanceRequestData.Update(system);
		m_SurfaceData.Update(system);
		m_ParkData.Update(system);
		m_EdgeData.Update(system);
		m_NetConditionData.Update(system);
		m_CompositionData.Update(system);
		m_CurrentDistrictData.Update(system);
		m_BorderDistrictData.Update(system);
		m_DistrictData.Update(system);
		m_VehicleData.Update(system);
		m_NetCompositionData.Update(system);
		m_ServiceDistricts.Update(system);
		JobHandle dependencies;
		JobHandle dependencies2;
		JobHandle jobHandle = JobChunkExtensions.ScheduleParallel(new MaintenanceRequestsJob
		{
			m_EntityType = m_EntityType,
			m_ServiceRequestType = m_ServiceRequestType,
			m_MaintenanceRequestType = m_MaintenanceRequestType,
			m_MaintenanceRequestData = m_MaintenanceRequestData,
			m_SurfaceData = m_SurfaceData,
			m_ParkData = m_ParkData,
			m_EdgeData = m_EdgeData,
			m_NetConditionData = m_NetConditionData,
			m_CompositionData = m_CompositionData,
			m_CurrentDistrictData = m_CurrentDistrictData,
			m_BorderDistrictData = m_BorderDistrictData,
			m_DistrictData = m_DistrictData,
			m_VehicleData = m_VehicleData,
			m_NetCompositionData = m_NetCompositionData,
			m_ServiceDistricts = m_ServiceDistricts,
			m_AreaTree = m_AreaSearchSystem.GetSearchTree(readOnly: true, out dependencies),
			m_NetTree = m_NetSearchSystem.GetNetSearchTree(readOnly: true, out dependencies2),
			m_SetupData = setupData
		}, m_MaintenanceRequestQuery, JobHandle.CombineDependencies(inputDeps, dependencies, dependencies2));
		m_AreaSearchSystem.AddSearchTreeReader(jobHandle);
		m_NetSearchSystem.AddNetSearchTreeReader(jobHandle);
		return jobHandle;
	}
```

- `public SetupOutsideConnections(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupOutsideConnections(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_OutsideConnectionType.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupOutsideConnectionsJob
		{
			m_EntityType = m_EntityType,
			m_OutsideConnectionType = m_OutsideConnectionType,
			m_SetupData = setupData
		}, m_OutsideConnectionQuery, inputDeps);
	}
```

- `public SetupRandomTraffic(Game.Simulation.PathfindSetupSystem system, Game.Simulation.PathfindSetupSystem+SetupData setupData, Unity.Jobs.JobHandle inputDeps) : Unity.Jobs.JobHandle`  

```csharp
public JobHandle SetupRandomTraffic(PathfindSetupSystem system, PathfindSetupSystem.SetupData setupData, JobHandle inputDeps)
	{
		m_EntityType.Update(system);
		m_PrefabRefType.Update(system);
		m_RandomTrafficRequestData.Update(system);
		m_PrefabTrafficSpawnerData.Update(system);
		return JobChunkExtensions.ScheduleParallel(new SetupRandomTrafficJob
		{
			m_EntityType = m_EntityType,
			m_PrefabRefType = m_PrefabRefType,
			m_RandomTrafficRequestData = m_RandomTrafficRequestData,
			m_PrefabTrafficSpawnerData = m_PrefabTrafficSpawnerData,
			m_SetupData = setupData
		}, m_RandomTrafficQuery, inputDeps);
	}
```


## Nested types

- `Game.Simulation.RoadPathfindSetup+SetupMaintenanceProvidersJob`  
- `Game.Simulation.RoadPathfindSetup+SetupRandomTrafficJob`  
- `Game.Simulation.RoadPathfindSetup+SetupOutsideConnectionsJob`  
- `Game.Simulation.RoadPathfindSetup+MaintenanceRequestsJob`  

