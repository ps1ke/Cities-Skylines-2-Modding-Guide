# Game.Pathfind.PathfindTargetSeekerData

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Game.Net.AirwayHelpers+AirwayData m_AirwayData`  
- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_Owner`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_Transform`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Attached> m_Attached`  
- `public Unity.Entities.ComponentLookup<Game.Objects.SpawnLocation> m_SpawnLocation`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Stopped> m_Stopped`  
- `public Unity.Entities.ComponentLookup<Game.Creatures.HumanCurrentLane> m_HumanCurrentLane`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.CarCurrentLane> m_CarCurrentLane`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.TrainCurrentLane> m_TrainCurrentLane`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.WatercraftCurrentLane> m_WatercraftCurrentLane`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.AircraftCurrentLane> m_AircraftCurrentLane`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.ParkedCar> m_ParkedCar`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.ParkedTrain> m_ParkedTrain`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Train> m_Train`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Airplane> m_Airplane`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.Building> m_Building`  
- `public Unity.Entities.ComponentLookup<Game.Buildings.PropertyRenter> m_PropertyRenter`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.CurrentBuilding> m_CurrentBuilding`  
- `public Unity.Entities.ComponentLookup<Game.Citizens.CurrentTransport> m_CurrentTransport`  
- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_Curve`  
- `public Unity.Entities.ComponentLookup<Game.Net.PedestrianLane> m_PedestrianLane`  
- `public Unity.Entities.ComponentLookup<Game.Net.ParkingLane> m_ParkingLane`  
- `public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLane`  
- `public Unity.Entities.ComponentLookup<Game.Net.MasterLane> m_MasterLane`  
- `public Unity.Entities.ComponentLookup<Game.Net.SlaveLane> m_SlaveLane`  
- `public Unity.Entities.ComponentLookup<Game.Net.ConnectionLane> m_ConnectionLane`  
- `public Unity.Entities.ComponentLookup<Game.Net.NodeLane> m_NodeLane`  
- `public Unity.Entities.ComponentLookup<Game.Net.LaneConnection> m_LaneConnection`  
- `public Unity.Entities.ComponentLookup<Game.Routes.RouteLane> m_RouteLane`  
- `public Unity.Entities.ComponentLookup<Game.Routes.AccessLane> m_AccessLane`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRef`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> m_BuildingData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PathfindCarData> m_CarPathfindData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.SpawnLocationData> m_SpawnLocationData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> m_NetLaneData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.CarLaneData> m_CarLaneData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ParkingLaneData> m_ParkingLaneData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.TrackLaneData> m_TrackLaneData`  
- `public Unity.Entities.BufferLookup<Game.Net.SubLane> m_SubLane`  
- `public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNode`  
- `public Unity.Entities.BufferLookup<Game.Areas.Triangle> m_AreaTriangle`  
- `public Unity.Entities.BufferLookup<Game.Buildings.SpawnLocationElement> m_SpawnLocations`  
- `public Unity.Entities.BufferLookup<Game.Vehicles.LayoutElement> m_VehicleLayout`  
- `public Unity.Entities.BufferLookup<Game.Vehicles.CarNavigationLane> m_CarNavigationLanes`  
- `public Unity.Entities.BufferLookup<Game.Vehicles.WatercraftNavigationLane> m_WatercraftNavigationLanes`  
- `public Unity.Entities.BufferLookup<Game.Vehicles.AircraftNavigationLane> m_AircraftNavigationLanes`  

## Constructors

- `public PathfindTargetSeekerData(Unity.Entities.SystemBase system)`  

## Methods

- `public Update(Unity.Entities.SystemBase system, Game.Net.AirwayHelpers+AirwayData airwayData) : System.Void`  

