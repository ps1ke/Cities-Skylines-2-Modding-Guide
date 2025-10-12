# Game.Simulation.CreatureTargetIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  

## Fields

- `public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  
- `public Unity.Entities.ComponentLookup<Game.Net.LaneReservation> m_LaneReservationData`  
- `public Unity.Entities.BufferLookup<Game.Net.LaneOverlap> m_LaneOverlaps`  
- `public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects`  
- `public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry`  
- `public Unity.Entities.Entity m_Blocker`  
- `public Game.Vehicles.BlockerType m_BlockerType`  
- `public Unity.Entities.Entity m_QueueEntity`  
- `public Colossal.Mathematics.Sphere3 m_QueueArea`  
- `private System.Single m_TargetDelta`  

## Methods

- `private CheckOverlapLane(Unity.Entities.Entity currentLane, Unity.Entities.Entity overlapLane, System.Single limitDelta, System.Single targetDelta, Unity.Mathematics.float2 overlapRange) : System.Void`  
- `public IterateLane(Unity.Entities.Entity currentLane, System.Single& curveDelta, System.Single targetDelta) : System.Boolean`  

