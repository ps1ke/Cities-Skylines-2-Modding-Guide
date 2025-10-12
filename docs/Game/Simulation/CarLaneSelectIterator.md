# Game.Simulation.CarLaneSelectIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Lane> m_LaneData`  
- `public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData`  
- `public Unity.Entities.ComponentLookup<Game.Net.SlaveLane> m_SlaveLaneData`  
- `public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Car> m_CarData`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData`  
- `public Unity.Entities.BufferLookup<Game.Net.SubLane> m_Lanes`  
- `public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects`  
- `public Unity.Entities.Entity m_Entity`  
- `public Unity.Entities.Entity m_Blocker`  
- `public System.Int32 m_Priority`  
- `public Game.Net.CarLaneFlags m_ForbidLaneFlags`  
- `public Game.Net.CarLaneFlags m_PreferLaneFlags`  
- `private Unity.Collections.NativeArray<System.Single> m_Buffer`  
- `private System.Int32 m_BufferPos`  
- `private System.Single m_LaneSwitchCost`  
- `private System.Single m_LaneSwitchBaseCost`  
- `private Unity.Entities.Entity m_PrevLane`  

## Methods

- `public CalculateLaneCosts(Game.Vehicles.CarNavigationLane navLaneData, System.Int32 index) : System.Void`  
- `public CalculateLaneCosts(Game.Vehicles.CarNavigationLane navLaneData, Game.Vehicles.CarNavigationLane nextNavLaneData, System.Int32 index) : System.Void`  
- `private CalculateLaneObjectCost(System.Single laneObjectCost, System.Int32 index, Unity.Entities.Entity lane, Game.Vehicles.CarLaneFlags laneFlags) : System.Single`  
- `private CalculateLaneObjectCost(System.Single laneObjectCost, Unity.Entities.Entity lane, System.Single minCurvePosition, Game.Vehicles.CarLaneFlags laneFlags) : System.Single`  
- `private CalculateLaneObjectCost(Game.Net.LaneObject laneObject, System.Single laneObjectCost, Game.Vehicles.CarLaneFlags laneFlags) : System.Single`  
- `private DrawLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curvePos, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher, System.Single cost) : System.Void`  
- `public DrawLaneCosts(Game.Vehicles.CarCurrentLane currentLaneData, Game.Vehicles.CarNavigationLane nextNavLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher) : System.Void`  
- `public DrawLaneCosts(Game.Vehicles.CarNavigationLane navLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher) : System.Void`  
- `private GetLaneDriveCost(Game.Net.CarLaneFlags flags) : System.Single`  
- `private GetLanePriorityCost(System.Int32 lanePriority) : System.Single`  
- `private GetLaneSwitchCost(System.Int32 numLanes) : System.Single`  
- `private GetTurnFlags(Unity.Entities.Entity currentLane, System.Int32 currentIndex, System.Int32 changeIndex) : Game.Vehicles.CarLaneFlags`  
- `public SetBuffer(Game.Simulation.CarLaneSelectBuffer& buffer) : System.Void`  
- `public UpdateOptimalLane(Game.Vehicles.CarCurrentLane& currentLane, Game.Vehicles.CarNavigationLane nextNavLaneData) : System.Void`  
- `public UpdateOptimalLane(Game.Vehicles.CarNavigationLane& navLaneData) : System.Void`  

