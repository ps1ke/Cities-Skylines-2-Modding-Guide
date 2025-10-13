# Game.Simulation.AircraftLaneSpeedIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct AircraftLaneSpeedIterator
{
    public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData;
    public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData;
    public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_AircraftData;
    public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData;
    public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
    public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
    public Unity.Entities.ComponentLookup<Game.Prefabs.AircraftData> m_PrefabAircraftData;
    public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlapData;
    public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjectData;
    public Unity.Entities.Entity m_Entity;
    public Unity.Entities.Entity m_Ignore;
    public System.Int32 m_Priority;
    public System.Single m_TimeStep;
    public System.Single m_SafeTimeStep;
    public Game.Prefabs.AircraftData m_PrefabAircraft;
    public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry;
    public Colossal.Mathematics.Bounds1 m_SpeedRange;
    public System.Single m_MaxSpeed;
    public System.Single m_CanChangeLane;
    public Unity.Mathematics.float3 m_CurrentPosition;
    public System.Single m_Distance;
    public Unity.Entities.Entity m_Blocker;
    public Game.Vehicles.BlockerType m_BlockerType;
    private Unity.Entities.Entity m_Lane;
    private Game.Net.Curve m_Curve;
    private Unity.Mathematics.float2 m_CurveOffset;
    private Unity.Mathematics.float3 m_PrevPosition;
    private System.Single m_PrevDistance;

    private System.Void CheckCurrentLane(System.Single distance, Unity.Mathematics.float2 minOffset);
    private System.Void CheckOverlappingLanes(System.Single origDistance, System.Single origMinOffset);
    private System.Single GetObjectSpeed(Unity.Entities.Entity obj, System.Single curveOffset);
    public System.Boolean IterateFirstLane(Unity.Entities.Entity lane, Unity.Mathematics.float3 curveOffset);
    public System.Boolean IterateNextLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curveOffset, System.Single minOffset);
    public System.Void IterateTarget(Unity.Mathematics.float3 targetPosition);
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

- `public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_AircraftData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Vehicles.Aircraft> m_AircraftData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.CarLane> m_CarLaneData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData;
```

- `public Unity.Entities.ComponentLookup<Game.Prefabs.AircraftData> m_PrefabAircraftData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Prefabs.AircraftData> m_PrefabAircraftData;
```

- `public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlapData`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlapData;
```

- `public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjectData`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjectData;
```

- `public Unity.Entities.Entity m_Entity`  

```csharp
public Unity.Entities.Entity m_Entity;
```

- `public Unity.Entities.Entity m_Ignore`  

```csharp
public Unity.Entities.Entity m_Ignore;
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

- `public Game.Prefabs.AircraftData m_PrefabAircraft`  

```csharp
public Game.Prefabs.AircraftData m_PrefabAircraft;
```

- `public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry`  

```csharp
public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry;
```

- `public Colossal.Mathematics.Bounds1 m_SpeedRange`  

```csharp
public Colossal.Mathematics.Bounds1 m_SpeedRange;
```

- `public System.Single m_MaxSpeed`  

```csharp
public System.Single m_MaxSpeed;
```

- `public System.Single m_CanChangeLane`  

```csharp
public System.Single m_CanChangeLane;
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

- `private CheckCurrentLane(System.Single distance, Unity.Mathematics.float2 minOffset) : System.Void`  

```csharp
private System.Void CheckCurrentLane(System.Single distance, Unity.Mathematics.float2 minOffset);
```

- `private CheckOverlappingLanes(System.Single origDistance, System.Single origMinOffset) : System.Void`  

```csharp
private System.Void CheckOverlappingLanes(System.Single origDistance, System.Single origMinOffset);
```

- `private GetObjectSpeed(Unity.Entities.Entity obj, System.Single curveOffset) : System.Single`  

```csharp
private System.Single GetObjectSpeed(Unity.Entities.Entity obj, System.Single curveOffset);
```

- `public IterateFirstLane(Unity.Entities.Entity lane, Unity.Mathematics.float3 curveOffset) : System.Boolean`  

```csharp
public System.Boolean IterateFirstLane(Unity.Entities.Entity lane, Unity.Mathematics.float3 curveOffset);
```

- `public IterateNextLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curveOffset, System.Single minOffset) : System.Boolean`  

```csharp
public System.Boolean IterateNextLane(Unity.Entities.Entity lane, Unity.Mathematics.float2 curveOffset, System.Single minOffset);
```

- `public IterateTarget(Unity.Mathematics.float3 targetPosition) : System.Void`  

```csharp
public System.Void IterateTarget(Unity.Mathematics.float3 targetPosition);
```

- `private UpdateMaxSpeed(Unity.Entities.Entity obj, Game.Vehicles.BlockerType blockerType, System.Single objectSpeed, System.Single laneOffset, System.Single distanceFactor, System.Single distanceOffset) : System.Void`  

```csharp
private System.Void UpdateMaxSpeed(Unity.Entities.Entity obj, Game.Vehicles.BlockerType blockerType, System.Single objectSpeed, System.Single laneOffset, System.Single distanceFactor, System.Single distanceOffset);
```


