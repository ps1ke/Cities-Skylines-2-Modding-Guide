# Game.Simulation.TrainLaneSpeedIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct TrainLaneSpeedIterator
{
    public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
    public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Car> m_CarData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Train> m_TrainData;
    public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
    public Unity.Entities.ComponentLookup<Game.Net.TrackLane> m_TrackLaneData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData;
    public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData;
    public Unity.Entities.ComponentLookup<Game.Net.LaneSignal> m_LaneSignalData;
    public Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.CarData> m_PrefabCarData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.TrainData> m_PrefabTrainData;
    public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlapData;
    public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjectData;
    public Unity.Entities.Entity m_Controller;
    public System.Int32 m_Priority;
    public System.Single m_TimeStep;
    public System.Single m_SafeTimeStep;
    public System.Single m_CurrentSpeed;
    public Game.Prefabs.TrainData m_PrefabTrain;
    public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry;
    public Colossal.Mathematics.Bounds1 m_SpeedRange;
    public Unity.Mathematics.float3 m_RearPosition;
    public System.Boolean m_PushBlockers;
    public System.Single m_MaxSpeed;
    public Unity.Mathematics.float3 m_CurrentPosition;
    public System.Single m_Distance;
    public Unity.Entities.Entity m_Blocker;
    public Game.Vehicles.BlockerType m_BlockerType;
    private Unity.Entities.Entity m_Lane;
    private Game.Net.Curve m_Curve;
    private Unity.Mathematics.float2 m_CurveOffset;
    private Unity.Mathematics.float3 m_PrevPosition;
    private System.Single m_PrevDistance;

    private System.Void CheckCurrentLane(System.Single distance, Unity.Mathematics.float2 minOffset, System.Boolean exclusive);
    private System.Void CheckOverlappingLanes(System.Single origDistance, System.Single origMinOffset, System.Int32 yieldOverride, System.Boolean exclusive);
    private System.Void CheckPedestrian(Colossal.Mathematics.Line3+Segment overlapLine, Unity.Entities.Entity obj, System.Single targetOffset, System.Single distanceOffset, System.Boolean giveSpace);
    private System.Single GetObjectSpeed(Unity.Entities.Entity obj, System.Single curveOffset);
    public System.Boolean IterateFirstLane(Unity.Entities.Entity lane, Unity.Mathematics.float4 curveOffset, System.Boolean exclusive, System.Boolean ignoreObstacles, System.Boolean skipCurrent, System.Boolean& needSignal);
    public System.Boolean IterateNextLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curveOffset, System.Single minOffset, System.Boolean exclusive, System.Boolean ignoreObstacles, System.Boolean& needSignal);
    public System.Void IteratePrevLane(Unity.Entities.Entity lane, System.Boolean& needSignal);
    public System.Boolean IterateTarget(Unity.Entities.Entity lane, System.Boolean ignoreObstacles);
    public System.Boolean IterateTarget();
    private System.Void UpdateMaxSpeed(Unity.Entities.Entity obj, Game.Vehicles.BlockerType blockerType, System.Single objectSpeed, System.Single laneOffset, System.Single distanceFactor, System.Single distanceOffset);
}
```


## Fields

- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
```

- `public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Car> m_CarData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Car> m_CarData;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Train> m_TrainData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Train> m_TrainData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.TrackLane> m_TrackLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.TrackLane> m_TrackLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.LaneSignal> m_LaneSignalData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.LaneSignal> m_LaneSignalData;
```

- `public Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.CarData> m_PrefabCarData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.CarData> m_PrefabCarData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.TrainData> m_PrefabTrainData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.TrainData> m_PrefabTrainData;
```

- `public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlapData`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlapData;
```

- `public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjectData`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjectData;
```

- `public Unity.Entities.Entity m_Controller`  

```csharp
public Unity.Entities.Entity m_Controller;
```

- `public System.Int32 m_Priority`  

```csharp
public System.Int32 m_Priority;
```

- `public System.Single m_TimeStep`  

```csharp
public System.Single m_TimeStep;
```

- `public System.Single m_SafeTimeStep`  

```csharp
public System.Single m_SafeTimeStep;
```

- `public System.Single m_CurrentSpeed`  

```csharp
public System.Single m_CurrentSpeed;
```

- `public Game.Prefabs.TrainData m_PrefabTrain`  

```csharp
public Game.Prefabs.TrainData m_PrefabTrain;
```

- `public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry`  

```csharp
public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry;
```

- `public Colossal.Mathematics.Bounds1 m_SpeedRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_SpeedRange;
```

- `public Unity.Mathematics.float3 m_RearPosition`  

```csharp
public Unity.Mathematics.float3 m_RearPosition;
```

- `public System.Boolean m_PushBlockers`  

```csharp
public System.Boolean m_PushBlockers;
```

- `public System.Single m_MaxSpeed`  

```csharp
public System.Single m_MaxSpeed;
```

- `public Unity.Mathematics.float3 m_CurrentPosition`  

```csharp
public Unity.Mathematics.float3 m_CurrentPosition;
```

- `public System.Single m_Distance`  

```csharp
public System.Single m_Distance;
```

- `public Unity.Entities.Entity m_Blocker`  

```csharp
public Unity.Entities.Entity m_Blocker;
```

- `public Game.Vehicles.BlockerType m_BlockerType`  

```csharp
public Game.Vehicles.BlockerType m_BlockerType;
```

- `private Unity.Entities.Entity m_Lane`  

```csharp
private Unity.Entities.Entity m_Lane;
```

- `private Game.Net.Curve m_Curve`  

```csharp
private Game.Net.Curve m_Curve;
```

- `private Unity.Mathematics.float2 m_CurveOffset`  

```csharp
private Unity.Mathematics.float2 m_CurveOffset;
```

- `private Unity.Mathematics.float3 m_PrevPosition`  

```csharp
private Unity.Mathematics.float3 m_PrevPosition;
```

- `private System.Single m_PrevDistance`  

```csharp
private System.Single m_PrevDistance;
```


## Methods

- `private CheckCurrentLane(System.Single distance, Unity.Mathematics.float2 minOffset, System.Boolean exclusive) : System.Void`  

```csharp
private System.Void CheckCurrentLane(System.Single distance, Unity.Mathematics.float2 minOffset, System.Boolean exclusive);
```

- `private CheckOverlappingLanes(System.Single origDistance, System.Single origMinOffset, System.Int32 yieldOverride, System.Boolean exclusive) : System.Void`  

```csharp
private System.Void CheckOverlappingLanes(System.Single origDistance, System.Single origMinOffset, System.Int32 yieldOverride, System.Boolean exclusive);
```

- `private CheckPedestrian(Colossal.Mathematics.Line3+Segment overlapLine, Unity.Entities.Entity obj, System.Single targetOffset, System.Single distanceOffset, System.Boolean giveSpace) : System.Void`  

```csharp
private System.Void CheckPedestrian(Colossal.Mathematics.Line3+Segment overlapLine, Unity.Entities.Entity obj, System.Single targetOffset, System.Single distanceOffset, System.Boolean giveSpace);
```

- `private GetObjectSpeed(Unity.Entities.Entity obj, System.Single curveOffset) : System.Single`  

```csharp
private System.Single GetObjectSpeed(Unity.Entities.Entity obj, System.Single curveOffset);
```

- `public IterateFirstLane(Unity.Entities.Entity lane, Unity.Mathematics.float4 curveOffset, System.Boolean exclusive, System.Boolean ignoreObstacles, System.Boolean skipCurrent, System.Boolean& needSignal) : System.Boolean`  

```csharp
public System.Boolean IterateFirstLane(Unity.Entities.Entity lane, Unity.Mathematics.float4 curveOffset, System.Boolean exclusive, System.Boolean ignoreObstacles, System.Boolean skipCurrent, System.Boolean& needSignal);
```

- `public IterateNextLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curveOffset, System.Single minOffset, System.Boolean exclusive, System.Boolean ignoreObstacles, System.Boolean& needSignal) : System.Boolean`  

```csharp
public System.Boolean IterateNextLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curveOffset, System.Single minOffset, System.Boolean exclusive, System.Boolean ignoreObstacles, System.Boolean& needSignal);
```

- `public IteratePrevLane(Unity.Entities.Entity lane, System.Boolean& needSignal) : System.Void`  

```csharp
public System.Void IteratePrevLane(Unity.Entities.Entity lane, System.Boolean& needSignal);
```

- `public IterateTarget(Unity.Entities.Entity lane, System.Boolean ignoreObstacles) : System.Boolean`  

```csharp
public System.Boolean IterateTarget(Unity.Entities.Entity lane, System.Boolean ignoreObstacles);
```

- `public IterateTarget() : System.Boolean`  

```csharp
public System.Boolean IterateTarget();
```

- `private UpdateMaxSpeed(Unity.Entities.Entity obj, Game.Vehicles.BlockerType blockerType, System.Single objectSpeed, System.Single laneOffset, System.Single distanceFactor, System.Single distanceOffset) : System.Void`  

```csharp
private System.Void UpdateMaxSpeed(Unity.Entities.Entity obj, Game.Vehicles.BlockerType blockerType, System.Single objectSpeed, System.Single laneOffset, System.Single distanceFactor, System.Single distanceOffset);
```


