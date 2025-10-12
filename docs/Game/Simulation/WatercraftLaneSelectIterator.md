# Game.Simulation.WatercraftLaneSelectIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Lane> m_LaneData`  
- `public Unity.Entities.ComponentLookup<Game.Net.SlaveLane> m_SlaveLaneData`  
- `public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Watercraft> m_WatercraftData`  
- `public Unity.Entities.BufferLookup<Game.Net.SubLane> m_Lanes`  
- `public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects`  
- `public Unity.Entities.Entity m_Entity`  
- `public Unity.Entities.Entity m_Blocker`  
- `public System.Int32 m_Priority`  
- `private Unity.Collections.NativeArray<System.Single> m_Buffer`  
- `private System.Int32 m_BufferPos`  
- `private System.Single m_LaneSwitchCost`  
- `private System.Single m_LaneSwitchBaseCost`  
- `private Unity.Entities.Entity m_PrevLane`  

## Methods

- `public CalculateLaneCosts(Game.Vehicles.WatercraftNavigationLane navLaneData, System.Int32 index) : System.Void`  
- `public CalculateLaneCosts(Game.Vehicles.WatercraftNavigationLane navLaneData, Game.Vehicles.WatercraftNavigationLane nextNavLaneData, System.Int32 index) : System.Void`  
- `private CalculateLaneObjectCost(System.Single laneObjectCost, System.Int32 index, Unity.Entities.Entity lane, Game.Vehicles.WatercraftLaneFlags laneFlags) : System.Single`  
- `private CalculateLaneObjectCost(System.Single laneObjectCost, Unity.Entities.Entity lane, System.Single minCurvePosition, Game.Vehicles.WatercraftLaneFlags laneFlags) : System.Single`  
- `private CalculateLaneObjectCost(Game.Net.LaneObject laneObject, System.Single laneObjectCost, Game.Vehicles.WatercraftLaneFlags laneFlags) : System.Single`  
- `private DrawLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curvePos, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher, System.Single cost) : System.Void`  
- `public DrawLaneCosts(Game.Vehicles.WatercraftCurrentLane currentLaneData, Game.Vehicles.WatercraftNavigationLane nextNavLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher) : System.Void`  
- `public DrawLaneCosts(Game.Vehicles.WatercraftNavigationLane navLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Colossal.GizmoBatcher gizmoBatcher) : System.Void`  
- `private GetLanePriorityCost(System.Int32 lanePriority) : System.Single`  
- `private GetLaneSwitchCost(System.Int32 numLanes) : System.Single`  
- `public SetBuffer(Game.Simulation.WatercraftLaneSelectBuffer& buffer) : System.Void`  
- `public UpdateOptimalLane(Game.Vehicles.WatercraftCurrentLane& currentLaneData, Game.Vehicles.WatercraftNavigationLane nextNavLaneData) : System.Void`  
- `public UpdateOptimalLane(Game.Vehicles.WatercraftNavigationLane& navLaneData) : System.Void`  

