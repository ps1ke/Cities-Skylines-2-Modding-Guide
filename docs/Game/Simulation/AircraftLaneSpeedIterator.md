# Game.Simulation.AircraftLaneSpeedIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_AircraftData`  
- `public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  
- `public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.AircraftData> m_PrefabAircraftData`  
- `public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlapData`  
- `public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjectData`  
- `public Unity.Entities.Entity m_Entity`  
- `public Unity.Entities.Entity m_Ignore`  
- `public System.Int32 m_Priority`  
- `public System.Single m_TimeStep`  
- `public System.Single m_SafeTimeStep`  
- `public Game.Prefabs.AircraftData m_PrefabAircraft`  
- `public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry`  
- `public Colossal.Mathematics.Bounds1 m_SpeedRange`  
- `public System.Single m_MaxSpeed`  
- `public System.Single m_CanChangeLane`  
- `public Unity.Mathematics.float3 m_CurrentPosition`  
- `public System.Single m_Distance`  
- `public Unity.Entities.Entity m_Blocker`  
- `public Game.Vehicles.BlockerType m_BlockerType`  
- `private Unity.Entities.Entity m_Lane`  
- `private Game.Net.Curve m_Curve`  
- `private Unity.Mathematics.float2 m_CurveOffset`  
- `private Unity.Mathematics.float3 m_PrevPosition`  
- `private System.Single m_PrevDistance`  

## Methods

- `private CheckCurrentLane(System.Single distance, Unity.Mathematics.float2 minOffset) : System.Void`  
- `private CheckOverlappingLanes(System.Single origDistance, System.Single origMinOffset) : System.Void`  
- `private GetObjectSpeed(Unity.Entities.Entity obj, System.Single curveOffset) : System.Single`  
- `public IterateFirstLane(Unity.Entities.Entity lane, Unity.Mathematics.float3 curveOffset) : System.Boolean`  
- `public IterateNextLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curveOffset, System.Single minOffset) : System.Boolean`  
- `public IterateTarget(Unity.Mathematics.float3 targetPosition) : System.Void`  
- `private UpdateMaxSpeed(Unity.Entities.Entity obj, Game.Vehicles.BlockerType blockerType, System.Single objectSpeed, System.Single laneOffset, System.Single distanceFactor, System.Single distanceOffset) : System.Void`  

