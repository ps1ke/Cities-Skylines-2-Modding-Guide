# Game.Simulation.CarLaneSpeedIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Car> m_CarData`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Train> m_TrainData`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData`  
- `public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData`  
- `public Unity.Entities.ComponentLookup<Game.Net.LaneCondition> m_LaneConditionData`  
- `public Unity.Entities.ComponentLookup<Game.Net.LaneSignal> m_LaneSignalData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  
- `public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData`  
- `public Unity.Entities.ComponentLookup<Game.Net.ParkingLane> m_ParkingLaneData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Unspawned> m_UnspawnedData`  
- `public Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.CarData> m_PrefabCarData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.TrainData> m_PrefabTrainData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ParkingLaneData> m_PrefabParkingLaneData`  
- `public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlapData`  
- `public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjectData`  
- `public Unity.Entities.Entity m_Entity`  
- `public Unity.Entities.Entity m_Ignore`  
- `public Unity.Collections.NativeList<Unity.Entities.Entity> m_TempBuffer`  
- `public System.Int32 m_Priority`  
- `public System.Single m_TimeStep`  
- `public System.Single m_SafeTimeStep`  
- `public System.Single m_DistanceOffset`  
- `public System.Single m_SpeedLimitFactor`  
- `public System.Single m_CurrentSpeed`  
- `public Game.Prefabs.CarData m_PrefabCar`  
- `public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry`  
- `public Colossal.Mathematics.Bounds1 m_SpeedRange`  
- `public System.Boolean m_PushBlockers`  
- `public System.Single m_MaxSpeed`  
- `public System.Single m_CanChangeLane`  
- `public Unity.Mathematics.float3 m_CurrentPosition`  
- `public System.Single m_Oncoming`  
- `public Unity.Entities.Entity m_Blocker`  
- `public Game.Vehicles.BlockerType m_BlockerType`  
- `private Unity.Entities.Entity m_Lane`  
- `private Unity.Entities.Entity m_NextLane`  
- `private Game.Net.Curve m_Curve`  
- `private Unity.Mathematics.float2 m_CurveOffset`  
- `private Unity.Mathematics.float2 m_NextOffset`  
- `private Unity.Mathematics.float3 m_PrevPosition`  
- `private System.Single m_PrevDistance`  
- `private System.Single m_Distance`  

## Methods

- `private CheckCurrentLane(System.Single distance, Unity.Mathematics.float2 minOffset, System.Boolean inverse) : System.Void`  
- `private CheckCurrentLane(System.Single distance, Unity.Mathematics.float2 minOffset, System.Boolean inverse, System.Single& canUseLane) : System.Void`  
- `private CheckOverlappingLanes(System.Single origDistance, System.Single origMinOffset, System.Int32 yieldOverride, System.Single speedLimit, System.Boolean isRoundabout, System.Boolean inverse, System.Boolean requestSpace) : System.Void`  
- `private CheckOverlapSpace(Unity.Entities.Entity currentLane, Unity.Mathematics.float2 curCurvePos, Unity.Entities.Entity nextLane, Unity.Mathematics.float2 nextCurvePos, Unity.Mathematics.float2 overlapPos, Unity.Entities.Entity& blocker) : System.Boolean`  
- `private CheckParkingLane(System.Single distance) : System.Void`  
- `private CheckPedestrian(Colossal.Mathematics.Line3+Segment overlapLine, Unity.Entities.Entity obj, System.Single targetOffset, System.Single distanceOffset, System.Boolean giveSpace, System.Boolean inverse) : System.Void`  
- `private CheckSpace(Unity.Entities.Entity currentLane, Unity.Mathematics.float2 curveOffset, Unity.Collections.NativeArray<Game.Vehicles.CarNavigationLane> nextLanes, Unity.Entities.Entity& blocker) : System.Boolean`  
- `private GetObjectSpeed(Unity.Entities.Entity obj, System.Single curveOffset) : System.Single`  
- `public IterateFirstLane(Unity.Entities.Entity lane, Unity.Mathematics.float3 curveOffset, Unity.Entities.Entity nextLane, Unity.Mathematics.float2 nextOffset, System.Single laneOffset, System.Boolean requestSpace, Game.Net.CarLaneFlags& laneFlags) : System.Boolean`  
- `public IterateFirstLane(Unity.Entities.Entity lane1, Unity.Entities.Entity lane2, Unity.Mathematics.float3 curveOffset, Unity.Entities.Entity nextLane, Unity.Mathematics.float2 nextOffset, System.Single laneDelta, System.Single laneOffset1, System.Single laneOffset2, System.Boolean requestSpace, Game.Net.CarLaneFlags& laneFlags) : System.Boolean`  
- `public IterateNextLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curveOffset, System.Single minOffset, Unity.Collections.NativeArray<Game.Vehicles.CarNavigationLane> nextLanes, System.Boolean requestSpace, Game.Net.CarLaneFlags& laneFlags, System.Boolean& needSignal) : System.Boolean`  
- `public IterateTarget(Unity.Mathematics.float3 targetPosition) : System.Void`  
- `public IterateTarget(Unity.Mathematics.float3 targetPosition, System.Single maxLaneSpeed) : System.Void`  
- `private UpdateMaxSpeed(Unity.Entities.Entity obj, Game.Vehicles.BlockerType blockerType, System.Single objectSpeed, System.Single laneOffset, System.Single distanceFactor, System.Single distanceOffset, System.Boolean ignore, System.Boolean inverse1, System.Boolean inverse2, Unity.Mathematics.float3 currentPos) : System.Void`  

