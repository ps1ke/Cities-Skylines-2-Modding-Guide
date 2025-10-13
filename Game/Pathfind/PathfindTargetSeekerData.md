# Game.Pathfind.PathfindTargetSeekerData

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct PathfindTargetSeekerData
{
    public Game.Net.AirwayHelpers+AirwayData m_AirwayData;
    public Unity.Entities.ComponentLookup<Game.Common.Owner> m_Owner;
    public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_Transform;
    public Unity.Entities.ComponentLookup<Game.Objects.Attached> m_Attached;
    public Unity.Entities.ComponentLookup<Game.Objects.SpawnLocation> m_SpawnLocation;
    public Unity.Entities.ComponentLookup<Game.Objects.Stopped> m_Stopped;
    public Unity.Entities.ComponentLookup<Game.Creatures.HumanCurrentLane> m_HumanCurrentLane;
    public Unity.Entities.ComponentLookup<Game.Vehicles.CarCurrentLane> m_CarCurrentLane;
    public Unity.Entities.ComponentLookup<Game.Vehicles.TrainCurrentLane> m_TrainCurrentLane;
    public Unity.Entities.ComponentLookup<Game.Vehicles.WatercraftCurrentLane> m_WatercraftCurrentLane;
    public Unity.Entities.ComponentLookup<Game.Vehicles.AircraftCurrentLane> m_AircraftCurrentLane;
    public Unity.Entities.ComponentLookup<Game.Vehicles.ParkedCar> m_ParkedCar;
    public Unity.Entities.ComponentLookup<Game.Vehicles.ParkedTrain> m_ParkedTrain;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Train> m_Train;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Airplane> m_Airplane;
    public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Building;
    public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenter;
    public Unity.Entities.ComponentLookup<Game.Citizens.CurrentBuilding> m_CurrentBuilding;
    public Unity.Entities.ComponentLookup<Game.Citizens.CurrentTransport> m_CurrentTransport;
    public Unity.Entities.ComponentLookup<Game.Net.Curve> m_Curve;
    public Unity.Entities.ComponentLookup<Game.Net.PedestrianLane> m_PedestrianLane;
    public Unity.Entities.ComponentLookup<Game.Net.ParkingLane> m_ParkingLane;
    public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLane;
    public Unity.Entities.ComponentLookup<Game.Net.MasterLane> m_MasterLane;
    public Unity.Entities.ComponentLookup<Game.Net.SlaveLane> m_SlaveLane;
    public Unity.Entities.ComponentLookup<Game.Net.ConnectionLane> m_ConnectionLane;
    public Unity.Entities.ComponentLookup<Game.Net.NodeLane> m_NodeLane;
    public Unity.Entities.ComponentLookup<Game.Net.LaneConnection> m_LaneConnection;
    public Unity.Entities.ComponentLookup<Game.Routes.RouteLane> m_RouteLane;
    public Unity.Entities.ComponentLookup<Game.Routes.AccessLane> m_AccessLane;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRef;
    public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_BuildingData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PathfindCarData> m_CarPathfindData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnLocationData> m_SpawnLocationData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> m_NetLaneData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.CarLaneData> m_CarLaneData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ParkingLaneData> m_ParkingLaneData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.TrackLaneData> m_TrackLaneData;
    public Unity.Entities.BufferLookup<Game.Net.SubLane> m_SubLane;
    public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNode;
    public Unity.Entities.BufferLookup<Game.Areas.Triangle> m_AreaTriangle;
    public Unity.Entities.BufferLookup<Game.Buildings.SpawnLocationElement> m_SpawnLocations;
    public Unity.Entities.BufferLookup<Game.Vehicles.LayoutElement> m_VehicleLayout;
    public Unity.Entities.BufferLookup<Game.Vehicles.CarNavigationLane> m_CarNavigationLanes;
    public Unity.Entities.BufferLookup<Game.Vehicles.WatercraftNavigationLane> m_WatercraftNavigationLanes;
    public Unity.Entities.BufferLookup<Game.Vehicles.AircraftNavigationLane> m_AircraftNavigationLanes;

    public PathfindTargetSeekerData(Unity.Entities.SystemBase system);

    public System.Void Update(Unity.Entities.SystemBase system, Game.Net.AirwayHelpers+AirwayData airwayData);
}
```


## Fields

- `public Game.Net.AirwayHelpers+AirwayData m_AirwayData`  

```csharp
public Game.Net.AirwayHelpers+AirwayData m_AirwayData;
```

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_Owner`  

```csharp
public Unity.Entities.ComponentLookup<Game.Common.Owner> m_Owner;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_Transform`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_Transform;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Attached> m_Attached`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Attached> m_Attached;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.SpawnLocation> m_SpawnLocation`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.SpawnLocation> m_SpawnLocation;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Stopped> m_Stopped`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Stopped> m_Stopped;
```

- `public Unity.Entities.ComponentLookup<Game.Creatures.HumanCurrentLane> m_HumanCurrentLane`  

```csharp
public Unity.Entities.ComponentLookup<Game.Creatures.HumanCurrentLane> m_HumanCurrentLane;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.CarCurrentLane> m_CarCurrentLane`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.CarCurrentLane> m_CarCurrentLane;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.TrainCurrentLane> m_TrainCurrentLane`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.TrainCurrentLane> m_TrainCurrentLane;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.WatercraftCurrentLane> m_WatercraftCurrentLane`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.WatercraftCurrentLane> m_WatercraftCurrentLane;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.AircraftCurrentLane> m_AircraftCurrentLane`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.AircraftCurrentLane> m_AircraftCurrentLane;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.ParkedCar> m_ParkedCar`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.ParkedCar> m_ParkedCar;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.ParkedTrain> m_ParkedTrain`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.ParkedTrain> m_ParkedTrain;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Train> m_Train`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Train> m_Train;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Airplane> m_Airplane`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Airplane> m_Airplane;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Building`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Building;
```

- `public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenter`  

```csharp
public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenter;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.CurrentBuilding> m_CurrentBuilding`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.CurrentBuilding> m_CurrentBuilding;
```

- `public Unity.Entities.ComponentLookup<Game.Citizens.CurrentTransport> m_CurrentTransport`  

```csharp
public Unity.Entities.ComponentLookup<Game.Citizens.CurrentTransport> m_CurrentTransport;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_Curve`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Curve> m_Curve;
```

- `public Unity.Entities.ComponentLookup<Game.Net.PedestrianLane> m_PedestrianLane`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.PedestrianLane> m_PedestrianLane;
```

- `public Unity.Entities.ComponentLookup<Game.Net.ParkingLane> m_ParkingLane`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.ParkingLane> m_ParkingLane;
```

- `public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLane`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLane;
```

- `public Unity.Entities.ComponentLookup<Game.Net.MasterLane> m_MasterLane`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.MasterLane> m_MasterLane;
```

- `public Unity.Entities.ComponentLookup<Game.Net.SlaveLane> m_SlaveLane`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.SlaveLane> m_SlaveLane;
```

- `public Unity.Entities.ComponentLookup<Game.Net.ConnectionLane> m_ConnectionLane`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.ConnectionLane> m_ConnectionLane;
```

- `public Unity.Entities.ComponentLookup<Game.Net.NodeLane> m_NodeLane`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.NodeLane> m_NodeLane;
```

- `public Unity.Entities.ComponentLookup<Game.Net.LaneConnection> m_LaneConnection`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.LaneConnection> m_LaneConnection;
```

- `public Unity.Entities.ComponentLookup<Game.Routes.RouteLane> m_RouteLane`  

```csharp
public Unity.Entities.ComponentLookup<Game.Routes.RouteLane> m_RouteLane;
```

- `public Unity.Entities.ComponentLookup<Game.Routes.AccessLane> m_AccessLane`  

```csharp
public Unity.Entities.ComponentLookup<Game.Routes.AccessLane> m_AccessLane;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRef`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRef;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_BuildingData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_BuildingData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PathfindCarData> m_CarPathfindData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PathfindCarData> m_CarPathfindData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnLocationData> m_SpawnLocationData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnLocationData> m_SpawnLocationData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> m_NetLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> m_NetLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.CarLaneData> m_CarLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.CarLaneData> m_CarLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ParkingLaneData> m_ParkingLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ParkingLaneData> m_ParkingLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.TrackLaneData> m_TrackLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.TrackLaneData> m_TrackLaneData;
```

- `public Unity.Entities.BufferLookup<Game.Net.SubLane> m_SubLane`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.SubLane> m_SubLane;
```

- `public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNode`  

```csharp
public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNode;
```

- `public Unity.Entities.BufferLookup<Game.Areas.Triangle> m_AreaTriangle`  

```csharp
public Unity.Entities.BufferLookup<Game.Areas.Triangle> m_AreaTriangle;
```

- `public Unity.Entities.BufferLookup<Game.Buildings.SpawnLocationElement> m_SpawnLocations`  

```csharp
public Unity.Entities.BufferLookup<Game.Buildings.SpawnLocationElement> m_SpawnLocations;
```

- `public Unity.Entities.BufferLookup<Game.Vehicles.LayoutElement> m_VehicleLayout`  

```csharp
public Unity.Entities.BufferLookup<Game.Vehicles.LayoutElement> m_VehicleLayout;
```

- `public Unity.Entities.BufferLookup<Game.Vehicles.CarNavigationLane> m_CarNavigationLanes`  

```csharp
public Unity.Entities.BufferLookup<Game.Vehicles.CarNavigationLane> m_CarNavigationLanes;
```

- `public Unity.Entities.BufferLookup<Game.Vehicles.WatercraftNavigationLane> m_WatercraftNavigationLanes`  

```csharp
public Unity.Entities.BufferLookup<Game.Vehicles.WatercraftNavigationLane> m_WatercraftNavigationLanes;
```

- `public Unity.Entities.BufferLookup<Game.Vehicles.AircraftNavigationLane> m_AircraftNavigationLanes`  

```csharp
public Unity.Entities.BufferLookup<Game.Vehicles.AircraftNavigationLane> m_AircraftNavigationLanes;
```


## Constructors

- `public PathfindTargetSeekerData(Unity.Entities.SystemBase system)`  

```csharp
public PathfindTargetSeekerData(SystemBase system)
	{
		m_AirwayData = default(AirwayHelpers.AirwayData);
		m_Owner = system.GetComponentLookup<Owner>(isReadOnly: true);
		m_Transform = system.GetComponentLookup<Transform>(isReadOnly: true);
		m_Attached = system.GetComponentLookup<Attached>(isReadOnly: true);
		m_SpawnLocation = system.GetComponentLookup<Game.Objects.SpawnLocation>(isReadOnly: true);
		m_Stopped = system.GetComponentLookup<Stopped>(isReadOnly: true);
		m_HumanCurrentLane = system.GetComponentLookup<HumanCurrentLane>(isReadOnly: true);
		m_CarCurrentLane = system.GetComponentLookup<CarCurrentLane>(isReadOnly: true);
		m_TrainCurrentLane = system.GetComponentLookup<TrainCurrentLane>(isReadOnly: true);
		m_WatercraftCurrentLane = system.GetComponentLookup<WatercraftCurrentLane>(isReadOnly: true);
		m_AircraftCurrentLane = system.GetComponentLookup<AircraftCurrentLane>(isReadOnly: true);
		m_ParkedCar = system.GetComponentLookup<ParkedCar>(isReadOnly: true);
		m_ParkedTrain = system.GetComponentLookup<ParkedTrain>(isReadOnly: true);
		m_Train = system.GetComponentLookup<Train>(isReadOnly: true);
		m_Airplane = system.GetComponentLookup<Airplane>(isReadOnly: true);
		m_Building = system.GetComponentLookup<Building>(isReadOnly: true);
		m_PropertyRenter = system.GetComponentLookup<PropertyRenter>(isReadOnly: true);
		m_CurrentBuilding = system.GetComponentLookup<CurrentBuilding>(isReadOnly: true);
		m_CurrentTransport = system.GetComponentLookup<CurrentTransport>(isReadOnly: true);
		m_Curve = system.GetComponentLookup<Curve>(isReadOnly: true);
		m_PedestrianLane = system.GetComponentLookup<Game.Net.PedestrianLane>(isReadOnly: true);
		m_ParkingLane = system.GetComponentLookup<Game.Net.ParkingLane>(isReadOnly: true);
		m_CarLane = system.GetComponentLookup<Game.Net.CarLane>(isReadOnly: true);
		m_MasterLane = system.GetComponentLookup<MasterLane>(isReadOnly: true);
		m_SlaveLane = system.GetComponentLookup<SlaveLane>(isReadOnly: true);
		m_ConnectionLane = system.GetComponentLookup<Game.Net.ConnectionLane>(isReadOnly: true);
		m_NodeLane = system.GetComponentLookup<NodeLane>(isReadOnly: true);
		m_LaneConnection = system.GetComponentLookup<LaneConnection>(isReadOnly: true);
		m_RouteLane = system.GetComponentLookup<RouteLane>(isReadOnly: true);
		m_AccessLane = system.GetComponentLookup<AccessLane>(isReadOnly: true);
		m_PrefabRef = system.GetComponentLookup<PrefabRef>(isReadOnly: true);
		m_BuildingData = system.GetComponentLookup<BuildingData>(isReadOnly: true);
		m_CarPathfindData = system.GetComponentLookup<PathfindCarData>(isReadOnly: true);
		m_SpawnLocationData = system.GetComponentLookup<SpawnLocationData>(isReadOnly: true);
		m_NetLaneData = system.GetComponentLookup<NetLaneData>(isReadOnly: true);
		m_CarLaneData = system.GetComponentLookup<CarLaneData>(isReadOnly: true);
		m_ParkingLaneData = system.GetComponentLookup<ParkingLaneData>(isReadOnly: true);
		m_TrackLaneData = system.GetComponentLookup<TrackLaneData>(isReadOnly: true);
		m_SubLane = system.GetBufferLookup<Game.Net.SubLane>(isReadOnly: true);
		m_AreaNode = system.GetBufferLookup<Game.Areas.Node>(isReadOnly: true);
		m_AreaTriangle = system.GetBufferLookup<Triangle>(isReadOnly: true);
		m_SpawnLocations = system.GetBufferLookup<SpawnLocationElement>(isReadOnly: true);
		m_VehicleLayout = system.GetBufferLookup<LayoutElement>(isReadOnly: true);
		m_CarNavigationLanes = system.GetBufferLookup<CarNavigationLane>(isReadOnly: true);
		m_WatercraftNavigationLanes = system.GetBufferLookup<WatercraftNavigationLane>(isReadOnly: true);
		m_AircraftNavigationLanes = system.GetBufferLookup<AircraftNavigationLane>(isReadOnly: true);
	}
```


## Methods

- `public Update(Unity.Entities.SystemBase system, Game.Net.AirwayHelpers+AirwayData airwayData) : System.Void`  

```csharp
public void Update(SystemBase system, AirwayHelpers.AirwayData airwayData)
	{
		m_AirwayData = airwayData;
		m_Owner.Update(system);
		m_Transform.Update(system);
		m_Attached.Update(system);
		m_SpawnLocation.Update(system);
		m_Stopped.Update(system);
		m_HumanCurrentLane.Update(system);
		m_CarCurrentLane.Update(system);
		m_TrainCurrentLane.Update(system);
		m_WatercraftCurrentLane.Update(system);
		m_AircraftCurrentLane.Update(system);
		m_ParkedCar.Update(system);
		m_ParkedTrain.Update(system);
		m_Train.Update(system);
		m_Airplane.Update(system);
		m_Building.Update(system);
		m_PropertyRenter.Update(system);
		m_CurrentBuilding.Update(system);
		m_CurrentTransport.Update(system);
		m_Curve.Update(system);
		m_PedestrianLane.Update(system);
		m_ParkingLane.Update(system);
		m_CarLane.Update(system);
		m_MasterLane.Update(system);
		m_SlaveLane.Update(system);
		m_ConnectionLane.Update(system);
		m_NodeLane.Update(system);
		m_LaneConnection.Update(system);
		m_RouteLane.Update(system);
		m_AccessLane.Update(system);
		m_PrefabRef.Update(system);
		m_BuildingData.Update(system);
		m_CarPathfindData.Update(system);
		m_SpawnLocationData.Update(system);
		m_NetLaneData.Update(system);
		m_CarLaneData.Update(system);
		m_ParkingLaneData.Update(system);
		m_TrackLaneData.Update(system);
		m_SubLane.Update(system);
		m_AreaNode.Update(system);
		m_AreaTriangle.Update(system);
		m_SpawnLocations.Update(system);
		m_VehicleLayout.Update(system);
		m_CarNavigationLanes.Update(system);
		m_WatercraftNavigationLanes.Update(system);
		m_AircraftNavigationLanes.Update(system);
	}
```


