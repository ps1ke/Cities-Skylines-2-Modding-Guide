# Game.Simulation.VehicleCollisionIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

## Fields

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData`  
- `public Unity.Entities.ComponentLookup<Game.Vehicles.Controller> m_ControllerData`  
- `public Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  
- `public Unity.Entities.ComponentLookup<Game.Net.AreaLane> m_AreaLaneData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> m_PrefabLaneData`  
- `public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes`  
- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_StaticObjectSearchTree`  
- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_MovingObjectSearchTree`  
- `public Game.Simulation.TerrainHeightData m_TerrainHeightData`  
- `public Unity.Entities.Entity m_Entity`  
- `public Unity.Entities.Entity m_CurrentLane`  
- `public System.Single m_CurvePosition`  
- `public System.Single m_TimeStep`  
- `public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry`  
- `public Colossal.Mathematics.Bounds1 m_SpeedRange`  
- `public Unity.Mathematics.float3 m_CurrentPosition`  
- `public Unity.Mathematics.float3 m_CurrentVelocity`  
- `public System.Single m_MinDistance`  
- `public Unity.Mathematics.float3 m_TargetPosition`  
- `public System.Single m_MaxSpeed`  
- `public System.Single m_LanePosition`  
- `public Unity.Entities.Entity m_Blocker`  
- `public Game.Vehicles.BlockerType m_BlockerType`  
- `private Colossal.Mathematics.Line3+Segment m_TargetLine`  
- `private Colossal.Mathematics.Bounds1 m_TargetLimits`  
- `private System.Single m_PushFactor`  
- `private Colossal.Mathematics.Bounds3 m_Bounds`  
- `private System.Single m_Size`  

## Methods

- `private CalculateTargetLine(Unity.Entities.Entity targetLane, Unity.Mathematics.float3 targetPosition) : System.Void`  
- `private CheckCollision(Unity.Entities.Entity other) : System.Void`  
- `public Intersect(Game.Common.QuadTreeBoundsXZ bounds) : System.Boolean`  
- `public Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity item) : System.Void`  
- `public IterateFirstLane(Unity.Entities.Entity currentLane) : System.Boolean`  

