# Game.Simulation.CreatureTargetIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Code

```csharp
public sealed struct CreatureTargetIterator
{
    public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData;
    public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
    public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData;
    public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlaps;
    public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects;
    public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry;
    public Unity.Entities.Entity m_Blocker;
    public Game.Vehicles.BlockerType m_BlockerType;
    public Unity.Entities.Entity m_QueueEntity;
    public Colossal.Mathematics.Sphere3 m_QueueArea;
    private System.Single m_TargetDelta;

    private System.Void CheckOverlapLane(Unity.Entities.Entity currentLane, Unity.Entities.Entity overlapLane, System.Single limitDelta, System.Single targetDelta, Unity.Mathematics.float2 overlapRange);
    public System.Boolean IterateLane(Unity.Entities.Entity currentLane, System.Single& curveDelta, System.Single targetDelta);
}
```


## Fields

- `public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData;
```

- `public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData`  

```csharp
public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData;
```

- `public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlaps`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlaps;
```

- `public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects`  

```csharp
public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects;
```

- `public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry`  

```csharp
public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry;
```

- `public Unity.Entities.Entity m_Blocker`  

```csharp
public Unity.Entities.Entity m_Blocker;
```

- `public Game.Vehicles.BlockerType m_BlockerType`  

```csharp
public Game.Vehicles.BlockerType m_BlockerType;
```

- `public Unity.Entities.Entity m_QueueEntity`  

```csharp
public Unity.Entities.Entity m_QueueEntity;
```

- `public Colossal.Mathematics.Sphere3 m_QueueArea`  

```csharp
public Colossal.Mathematics.Sphere3 m_QueueArea;
```

- `private System.Single m_TargetDelta`  

```csharp
private System.Single m_TargetDelta;
```


## Methods

- `private CheckOverlapLane(Unity.Entities.Entity currentLane, Unity.Entities.Entity overlapLane, System.Single limitDelta, System.Single targetDelta, Unity.Mathematics.float2 overlapRange) : System.Void`  

```csharp
private System.Void CheckOverlapLane(Unity.Entities.Entity currentLane, Unity.Entities.Entity overlapLane, System.Single limitDelta, System.Single targetDelta, Unity.Mathematics.float2 overlapRange);
```

- `public IterateLane(Unity.Entities.Entity currentLane, System.Single& curveDelta, System.Single targetDelta) : System.Boolean`  

```csharp
public System.Boolean IterateLane(Unity.Entities.Entity currentLane, System.Single& curveDelta, System.Single targetDelta);
```


