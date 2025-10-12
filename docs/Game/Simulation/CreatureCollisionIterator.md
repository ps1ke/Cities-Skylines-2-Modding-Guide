# Game.Simulation.CreatureCollisionIterator

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** struct sealed public  

**Base:** `System.ValueType`  
**Implements:** `Colossal.Collections.INativeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`, `Colossal.Collections.IUnsafeQuadTreeIterator<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ>`  

## Fields

- `public Unity.Entities.ComponentLookup<Game.Common.Owner> m_OwnerData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Transform> m_TransformData`  
- `public Unity.Entities.ComponentLookup<Game.Objects.Moving> m_MovingData`  
- `public Unity.Entities.ComponentLookup<Game.Creatures.Creature> m_CreatureData`  
- `public Unity.Entities.ComponentLookup<Game.Creatures.GroupMember> m_GroupMemberData`  
- `public Unity.Entities.ComponentLookup<Game.Routes.Waypoint> m_WaypointData`  
- `public Unity.Entities.ComponentLookup<Game.Routes.TaxiStand> m_TaxiStandData`  
- `public Unity.Entities.ComponentLookup<Game.Net.Curve> m_CurveData`  
- `public Unity.Entities.ComponentLookup<Game.Net.AreaLane> m_AreaLaneData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> m_PrefabRefData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.ObjectGeometryData> m_PrefabObjectGeometryData`  
- `public Unity.Entities.ComponentLookup<Game.Prefabs.NetLaneData> m_PrefabLaneData`  
- `public Unity.Entities.BufferLookup<Game.Net.LaneObject> m_LaneObjects`  
- `public Unity.Entities.BufferLookup<Game.Areas.Node> m_AreaNodes`  
- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_StaticObjectSearchTree`  
- `public Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> m_MovingObjectSearchTree`  
- `public Unity.Entities.Entity m_Entity`  
- `public Unity.Entities.Entity m_Leader`  
- `public Unity.Entities.Entity m_CurrentLane`  
- `public Unity.Entities.Entity m_CurrentVehicle`  
- `public System.Single m_CurvePosition`  
- `public System.Single m_TimeStep`  
- `public Game.Prefabs.ObjectGeometryData m_PrefabObjectGeometry`  
- `public Colossal.Mathematics.Bounds1 m_SpeedRange`  
- `public Unity.Mathematics.float3 m_CurrentPosition`  
- `public Unity.Mathematics.float3 m_CurrentDirection`  
- `public Unity.Mathematics.float3 m_CurrentVelocity`  
- `public System.Single m_TargetDistance`  
- `public Game.Pathfind.PathOwner m_PathOwner`  
- `public Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> m_PathElements`  
- `public System.Single m_MinSpeed`  
- `public Unity.Mathematics.float3 m_TargetPosition`  
- `public System.Single m_MaxSpeed`  
- `public System.Single m_LanePosition`  
- `public Unity.Entities.Entity m_Blocker`  
- `public Game.Vehicles.BlockerType m_BlockerType`  
- `public Unity.Entities.Entity m_QueueEntity`  
- `public Colossal.Mathematics.Sphere3 m_QueueArea`  
- `public Unity.Entities.DynamicBuffer<Game.Creatures.Queue> m_Queues`  
- `private Colossal.Mathematics.Line3+Segment m_TargetLine`  
- `private System.Single m_PushFactor`  
- `private Colossal.Mathematics.Bounds3 m_Bounds`  
- `private System.Single m_Size`  

## Methods

- `private CalculateTargetLine(Unity.Entities.Entity targetLane, Unity.Mathematics.float3 targetPosition, System.Boolean isBackward) : System.Void`  
- `private CalculateTargetLine(Unity.Entities.Entity targetLane, System.Single targetOffset) : System.Void`  
- `private CheckCollision(Unity.Entities.Entity other) : System.Void`  
- `private CheckQueue(Unity.Entities.Entity other, Unity.Entities.Entity& queueEntity, Colossal.Mathematics.Sphere3& queueArea) : System.Boolean`  
- `private GetTargetPosition(System.Int32 elementIndex, Unity.Entities.Entity targetElement, System.Single curvePos) : Unity.Mathematics.float3`  
- `public Intersect(Game.Common.QuadTreeBoundsXZ bounds) : System.Boolean`  
- `public Iterate(Game.Common.QuadTreeBoundsXZ bounds, Unity.Entities.Entity item) : System.Void`  
- `public IterateBlocker(Game.Prefabs.HumanData prefabHumanData, Unity.Entities.Entity other) : System.Void`  
- `public IterateBlocker(Game.Prefabs.AnimalData prefabAnimalData, Unity.Entities.Entity other) : System.Void`  
- `public IterateFirstLane(Unity.Entities.Entity currentLane, Unity.Mathematics.float2 currentOffset, System.Boolean isBackward) : System.Boolean`  
- `public IterateFirstLane(Unity.Entities.Entity currentLane, Unity.Entities.Entity targetLane, Unity.Mathematics.float2 currentOffset, Unity.Mathematics.float2 targetOffset, System.Boolean isBackward) : System.Boolean`  
- `public IterateNextLane(Unity.Entities.Entity nextLane, Unity.Mathematics.float2 nextOffset) : System.Boolean`  
- `private ShouldQueue(Unity.Entities.Entity entity, Colossal.Mathematics.Sphere3 area, Colossal.Mathematics.Sphere3& queueArea) : System.Boolean`  

