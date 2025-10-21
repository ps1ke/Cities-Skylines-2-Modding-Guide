# Game.Creatures.CreatureUtils

**Assembly:** `Game`  
**Namespace:** `Game.Creatures`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class CreatureUtils
{
    public static const System.Single MAX_HUMAN_WALK_SPEED;
    public static const System.Single AVG_HUMAN_WALK_SPEED;
    public static const System.Single MIN_MOVE_SPEED;
    public static const System.Single RESIDENT_PATHFIND_RANDOM_COST;
    public static const System.Int32 MAX_TRANSPORT_WAIT_TICKS;
    public static const System.Int32 MAX_ENTER_VEHICLE_TICKS;
    public static const System.Single QUEUE_TICKS_TO_SECONDS;

    public static System.Boolean ActionLocationReached(Game.Creatures.HumanCurrentLane currentLane);
    private static Unity.Mathematics.float3 CalculateAreaTarget(Unity.Mathematics.float3 prev2, Unity.Mathematics.float3 prev, Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 comparePosition, System.Single minDistance, System.Single lanePosition, System.Single navigationSize, System.Boolean& farEnough);
    public static System.Boolean CalculateTransformPosition(Unity.Entities.Entity creature, Unity.Entities.Entity creaturePrefab, Unity.Entities.DynamicBuffer<Game.Rendering.MeshGroup> meshGroups, Unity.Mathematics.Random& random, Game.Objects.Transform& result, Game.Prefabs.ActivityType& activity, Game.Creatures.CurrentVehicle currentVehicle, Unity.Entities.Entity entity, System.Boolean leftHandTraffic, Game.Prefabs.ActivityMask activityMask, Game.Prefabs.ActivityCondition conditions, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> movingObjectSearchTree, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Entities.ComponentLookup`1[[Game.Routes.Position, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& positions, Unity.Entities.ComponentLookup`1[[Game.Vehicles.PublicTransport, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& publicTransports, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Train, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trains, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Controller, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& controllers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabBuildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.CarData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabCarDatas, Unity.Entities.BufferLookup`1[[Game.Prefabs.ActivityLocationElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabActivityLocations, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMeshGroup, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshGroupBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.CharacterElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& characterElementBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationClip, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationClipBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationMotionBuffers);
    private static Unity.Mathematics.float3 CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 lastTarget, Game.Pathfind.PathElement nextElement, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Routes.TaxiStand> taxiStands, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves);
    private static Unity.Mathematics.float3 CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 target, System.Single navigationSize, System.Boolean isSingle);
    private static Unity.Mathematics.float3 CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle);
    public static System.Void CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Creatures.HumanCurrentLane currentLane, Game.Creatures.Human human, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer);
    public static System.Void CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Creatures.AnimalCurrentLane currentLane, Game.Creatures.Animal animal, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer);
    public static System.Boolean DivertDestination(Game.Pathfind.SetupQueueTarget& destination, Game.Pathfind.PathOwner& pathOwner, Game.Creatures.Divert divert);
    public static System.Boolean EndReached(Game.Creatures.HumanCurrentLane currentLane);
    public static System.Void FixEnterPath(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes, Unity.Entities.BufferLookup`1[[Game.Areas.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaNodes, Unity.Entities.BufferLookup`1[[Game.Areas.Triangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaTriangles);
    private static System.Void FixEnterPath_AreaLane(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes, Unity.Entities.BufferLookup`1[[Game.Areas.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaNodes, Unity.Entities.BufferLookup`1[[Game.Areas.Triangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaTriangles);
    private static System.Void FixEnterPath_EdgeLane(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes);
    public static System.Void FixPathStart(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes, Unity.Entities.BufferLookup`1[[Game.Areas.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaNodes, Unity.Entities.BufferLookup`1[[Game.Areas.Triangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaTriangles);
    private static System.Void FixPathStart_AreaLane(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes, Unity.Entities.BufferLookup`1[[Game.Areas.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaNodes, Unity.Entities.BufferLookup`1[[Game.Areas.Triangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaTriangles);
    private static System.Void FixPathStart_EdgeLane(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes);
    public static System.Void GetAreaActivity(Unity.Mathematics.Random& random, Game.Prefabs.ActivityType& activity, Unity.Entities.Entity laneEntity, Game.Prefabs.ActivityMask activityMask, Unity.Entities.ComponentLookup<Game.Common.Owner> owners, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnLocationData> prefabSpawnLocationDatas);
    public static System.Single GetBrakingDistance(Game.Prefabs.HumanData prefabHumanData, System.Single speed, System.Single timeStep);
    public static System.Single GetBrakingDistance(Game.Prefabs.AnimalData prefabAnimalData, System.Single speed, System.Single timeStep);
    public static Game.Prefabs.ActivityCondition GetConditions(Game.Creatures.Human human);
    public static System.Single GetLaneOffset(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Game.Prefabs.NetLaneData prefabLaneData, System.Single lanePosition);
    public static Unity.Mathematics.float3 GetLanePosition(Colossal.Mathematics.Bezier4x3 curve, System.Single curvePosition, System.Single laneOffset);
    public static System.Single GetMaxBrakingSpeed(Game.Prefabs.HumanData prefabHumanData, System.Single distance, System.Single timeStep);
    public static System.Single GetMaxBrakingSpeed(Game.Prefabs.HumanData prefabHumanData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep);
    public static System.Single GetMaxBrakingSpeed(Game.Prefabs.AnimalData prefabAnimalData, System.Single distance, System.Single timeStep);
    public static System.Single GetMaxBrakingSpeed(Game.Prefabs.AnimalData prefabAnimalData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep);
    public static System.Single GetNavigationSize(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData);
    public static Colossal.Mathematics.Sphere3 GetQueueArea(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Unity.Mathematics.float3 position);
    public static Colossal.Mathematics.Sphere3 GetQueueArea(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Unity.Mathematics.float3 position1, Unity.Mathematics.float3 position2);
    public static Game.Objects.Transform GetVehicleDoorPosition(Unity.Mathematics.Random& random, Game.Prefabs.ActivityType activityType, Game.Prefabs.ActivityCondition conditions, Game.Objects.Transform vehicleTransform, Unity.Mathematics.float3 targetPosition, System.Boolean isDriver, System.Boolean lefthandTraffic, Unity.Entities.Entity creaturePrefab, Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Rendering.MeshGroup> meshGroups, Unity.Entities.ComponentLookup`1[[Game.Vehicles.PublicTransport, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& publicTransports, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Train, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trains, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Controller, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& controllers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.CarData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabCarDatas, Unity.Entities.BufferLookup`1[[Game.Prefabs.ActivityLocationElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabActivityLocations, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMeshGroup, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshGroupBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.CharacterElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& characterElementBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationClip, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationClipBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationMotionBuffers, Game.Prefabs.ActivityMask& activityMask, Game.Rendering.AnimatedPropID& propID);
    public static System.Boolean IsStuck(Game.Pathfind.PathOwner pathOwner);
    public static System.Boolean IsStuck(Game.Creatures.AnimalCurrentLane currentLane);
    public static System.Boolean ParkingSpaceReached(Game.Creatures.HumanCurrentLane currentLane);
    public static System.Boolean PathEndReached(Game.Creatures.HumanCurrentLane currentLane);
    public static System.Boolean PathEndReached(Game.Creatures.AnimalCurrentLane currentLane);
    public static System.Boolean PathfindFailed(Game.Pathfind.PathOwner pathOwner);
    public static System.Boolean RequireNewPath(Game.Pathfind.PathOwner pathOwner);
    public static System.Boolean ResetUncheckedLane(Game.Creatures.HumanCurrentLane& currentLane);
    public static System.Boolean ResetUpdatedPath(Game.Pathfind.PathOwner& pathOwner);
    public static System.Boolean SetAreaTarget(Unity.Mathematics.float3 prev2, Unity.Mathematics.float3 prev, Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Entities.Entity areaEntity, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Mathematics.float3 comparePosition, Game.Pathfind.PathElement nextElement, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isBackward, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Routes.TaxiStand> taxiStands, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves, Unity.Entities.ComponentLookup<Game.Common.Owner> owners);
    public static System.Void SetQueue(Unity.Entities.Entity& queueEntity, Colossal.Mathematics.Sphere3& queueArea, Unity.Entities.Entity setEntity, Colossal.Mathematics.Sphere3 setArea);
    public static System.Void SetRandomAreaTarget(Unity.Mathematics.Random& random, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.ConnectionLane> connectionLaneData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, Unity.Entities.BufferLookup<Game.Areas.Node> areaNodes, Unity.Entities.BufferLookup<Game.Areas.Triangle> areaTriangles);
    public static System.Boolean SetTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 comparePosition, Game.Pathfind.PathElement nextElement, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Routes.TaxiStand> taxiStands, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves);
    public static System.Void SetupPathfind(Game.Creatures.HumanCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> queue, Game.Pathfind.SetupQueueItem item);
    public static System.Boolean TransportStopReached(Game.Creatures.HumanCurrentLane currentLane);
}
```


## Fields

- `public static const System.Single MAX_HUMAN_WALK_SPEED`  

```csharp
public static const System.Single MAX_HUMAN_WALK_SPEED;
```

- `public static const System.Single AVG_HUMAN_WALK_SPEED`  

```csharp
public static const System.Single AVG_HUMAN_WALK_SPEED;
```

- `public static const System.Single MIN_MOVE_SPEED`  

```csharp
public static const System.Single MIN_MOVE_SPEED;
```

- `public static const System.Single RESIDENT_PATHFIND_RANDOM_COST`  

```csharp
public static const System.Single RESIDENT_PATHFIND_RANDOM_COST;
```

- `public static const System.Int32 MAX_TRANSPORT_WAIT_TICKS`  

```csharp
public static const System.Int32 MAX_TRANSPORT_WAIT_TICKS;
```

- `public static const System.Int32 MAX_ENTER_VEHICLE_TICKS`  

```csharp
public static const System.Int32 MAX_ENTER_VEHICLE_TICKS;
```

- `public static const System.Single QUEUE_TICKS_TO_SECONDS`  

```csharp
public static const System.Single QUEUE_TICKS_TO_SECONDS;
```


## Methods

- `public static ActionLocationReached(Game.Creatures.HumanCurrentLane currentLane) : System.Boolean`  

```csharp
public static System.Boolean ActionLocationReached(Game.Creatures.HumanCurrentLane currentLane);
```

- `private static CalculateAreaTarget(Unity.Mathematics.float3 prev2, Unity.Mathematics.float3 prev, Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 comparePosition, System.Single minDistance, System.Single lanePosition, System.Single navigationSize, System.Boolean& farEnough) : Unity.Mathematics.float3`  

```csharp
private static Unity.Mathematics.float3 CalculateAreaTarget(Unity.Mathematics.float3 prev2, Unity.Mathematics.float3 prev, Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 comparePosition, System.Single minDistance, System.Single lanePosition, System.Single navigationSize, System.Boolean& farEnough);
```

- `public static CalculateTransformPosition(Unity.Entities.Entity creature, Unity.Entities.Entity creaturePrefab, Unity.Entities.DynamicBuffer<Game.Rendering.MeshGroup> meshGroups, Unity.Mathematics.Random& random, Game.Objects.Transform& result, Game.Prefabs.ActivityType& activity, Game.Creatures.CurrentVehicle currentVehicle, Unity.Entities.Entity entity, System.Boolean leftHandTraffic, Game.Prefabs.ActivityMask activityMask, Game.Prefabs.ActivityCondition conditions, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> movingObjectSearchTree, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Entities.ComponentLookup`1[[Game.Routes.Position, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& positions, Unity.Entities.ComponentLookup`1[[Game.Vehicles.PublicTransport, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& publicTransports, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Train, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trains, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Controller, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& controllers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabBuildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.CarData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabCarDatas, Unity.Entities.BufferLookup`1[[Game.Prefabs.ActivityLocationElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabActivityLocations, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMeshGroup, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshGroupBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.CharacterElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& characterElementBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationClip, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationClipBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationMotionBuffers) : System.Boolean`  

```csharp
public static System.Boolean CalculateTransformPosition(Unity.Entities.Entity creature, Unity.Entities.Entity creaturePrefab, Unity.Entities.DynamicBuffer<Game.Rendering.MeshGroup> meshGroups, Unity.Mathematics.Random& random, Game.Objects.Transform& result, Game.Prefabs.ActivityType& activity, Game.Creatures.CurrentVehicle currentVehicle, Unity.Entities.Entity entity, System.Boolean leftHandTraffic, Game.Prefabs.ActivityMask activityMask, Game.Prefabs.ActivityCondition conditions, Colossal.Collections.NativeQuadTree<Unity.Entities.Entity, Game.Common.QuadTreeBoundsXZ> movingObjectSearchTree, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transforms, Unity.Entities.ComponentLookup`1[[Game.Routes.Position, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& positions, Unity.Entities.ComponentLookup`1[[Game.Vehicles.PublicTransport, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& publicTransports, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Train, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trains, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Controller, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& controllers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.BuildingData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabBuildingDatas, Unity.Entities.ComponentLookup`1[[Game.Prefabs.CarData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabCarDatas, Unity.Entities.BufferLookup`1[[Game.Prefabs.ActivityLocationElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabActivityLocations, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMeshGroup, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshGroupBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.CharacterElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& characterElementBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationClip, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationClipBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationMotionBuffers);
```

- `private static CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 lastTarget, Game.Pathfind.PathElement nextElement, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Routes.TaxiStand> taxiStands, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves) : Unity.Mathematics.float3`  

```csharp
private static Unity.Mathematics.float3 CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 lastTarget, Game.Pathfind.PathElement nextElement, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Routes.TaxiStand> taxiStands, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves);
```

- `private static CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 target, System.Single navigationSize, System.Boolean isSingle) : Unity.Mathematics.float3`  

```csharp
private static Unity.Mathematics.float3 CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 target, System.Single navigationSize, System.Boolean isSingle);
```

- `private static CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle) : Unity.Mathematics.float3`  

```csharp
private static Unity.Mathematics.float3 CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle);
```

- `public static CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Creatures.HumanCurrentLane currentLane, Game.Creatures.Human human, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer) : System.Void`  

```csharp
public static System.Void CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Creatures.HumanCurrentLane currentLane, Game.Creatures.Human human, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer);
```

- `public static CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Creatures.AnimalCurrentLane currentLane, Game.Creatures.Animal animal, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer) : System.Void`  

```csharp
public static System.Void CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Creatures.AnimalCurrentLane currentLane, Game.Creatures.Animal animal, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer);
```

- `public static DivertDestination(Game.Pathfind.SetupQueueTarget& destination, Game.Pathfind.PathOwner& pathOwner, Game.Creatures.Divert divert) : System.Boolean`  

```csharp
public static System.Boolean DivertDestination(Game.Pathfind.SetupQueueTarget& destination, Game.Pathfind.PathOwner& pathOwner, Game.Creatures.Divert divert);
```

- `public static EndReached(Game.Creatures.HumanCurrentLane currentLane) : System.Boolean`  

```csharp
public static System.Boolean EndReached(Game.Creatures.HumanCurrentLane currentLane);
```

- `public static FixEnterPath(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes, Unity.Entities.BufferLookup`1[[Game.Areas.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaNodes, Unity.Entities.BufferLookup`1[[Game.Areas.Triangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaTriangles) : System.Void`  

```csharp
public static System.Void FixEnterPath(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes, Unity.Entities.BufferLookup`1[[Game.Areas.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaNodes, Unity.Entities.BufferLookup`1[[Game.Areas.Triangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaTriangles);
```

- `private static FixEnterPath_AreaLane(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes, Unity.Entities.BufferLookup`1[[Game.Areas.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaNodes, Unity.Entities.BufferLookup`1[[Game.Areas.Triangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaTriangles) : System.Void`  

```csharp
private static System.Void FixEnterPath_AreaLane(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes, Unity.Entities.BufferLookup`1[[Game.Areas.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaNodes, Unity.Entities.BufferLookup`1[[Game.Areas.Triangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaTriangles);
```

- `private static FixEnterPath_EdgeLane(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes) : System.Void`  

```csharp
private static System.Void FixEnterPath_EdgeLane(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes);
```

- `public static FixPathStart(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes, Unity.Entities.BufferLookup`1[[Game.Areas.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaNodes, Unity.Entities.BufferLookup`1[[Game.Areas.Triangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaTriangles) : System.Void`  

```csharp
public static System.Void FixPathStart(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes, Unity.Entities.BufferLookup`1[[Game.Areas.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaNodes, Unity.Entities.BufferLookup`1[[Game.Areas.Triangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaTriangles);
```

- `private static FixPathStart_AreaLane(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes, Unity.Entities.BufferLookup`1[[Game.Areas.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaNodes, Unity.Entities.BufferLookup`1[[Game.Areas.Triangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaTriangles) : System.Void`  

```csharp
private static System.Void FixPathStart_AreaLane(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes, Unity.Entities.BufferLookup`1[[Game.Areas.Node, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaNodes, Unity.Entities.BufferLookup`1[[Game.Areas.Triangle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& areaTriangles);
```

- `private static FixPathStart_EdgeLane(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes) : System.Void`  

```csharp
private static System.Void FixPathStart_EdgeLane(Unity.Mathematics.Random& random, Unity.Mathematics.float3 position, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes);
```

- `public static GetAreaActivity(Unity.Mathematics.Random& random, Game.Prefabs.ActivityType& activity, Unity.Entities.Entity laneEntity, Game.Prefabs.ActivityMask activityMask, Unity.Entities.ComponentLookup<Game.Common.Owner> owners, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnLocationData> prefabSpawnLocationDatas) : System.Void`  

```csharp
public static System.Void GetAreaActivity(Unity.Mathematics.Random& random, Game.Prefabs.ActivityType& activity, Unity.Entities.Entity laneEntity, Game.Prefabs.ActivityMask activityMask, Unity.Entities.ComponentLookup<Game.Common.Owner> owners, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.SpawnLocationData> prefabSpawnLocationDatas);
```

- `public static GetBrakingDistance(Game.Prefabs.HumanData prefabHumanData, System.Single speed, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetBrakingDistance(Game.Prefabs.HumanData prefabHumanData, System.Single speed, System.Single timeStep);
```

- `public static GetBrakingDistance(Game.Prefabs.AnimalData prefabAnimalData, System.Single speed, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetBrakingDistance(Game.Prefabs.AnimalData prefabAnimalData, System.Single speed, System.Single timeStep);
```

- `public static GetConditions(Game.Creatures.Human human) : Game.Prefabs.ActivityCondition`  

```csharp
public static Game.Prefabs.ActivityCondition GetConditions(Game.Creatures.Human human);
```

- `public static GetLaneOffset(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Game.Prefabs.NetLaneData prefabLaneData, System.Single lanePosition) : System.Single`  

```csharp
public static System.Single GetLaneOffset(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Game.Prefabs.NetLaneData prefabLaneData, System.Single lanePosition);
```

- `public static GetLanePosition(Colossal.Mathematics.Bezier4x3 curve, System.Single curvePosition, System.Single laneOffset) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetLanePosition(Colossal.Mathematics.Bezier4x3 curve, System.Single curvePosition, System.Single laneOffset);
```

- `public static GetMaxBrakingSpeed(Game.Prefabs.HumanData prefabHumanData, System.Single distance, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetMaxBrakingSpeed(Game.Prefabs.HumanData prefabHumanData, System.Single distance, System.Single timeStep);
```

- `public static GetMaxBrakingSpeed(Game.Prefabs.HumanData prefabHumanData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetMaxBrakingSpeed(Game.Prefabs.HumanData prefabHumanData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep);
```

- `public static GetMaxBrakingSpeed(Game.Prefabs.AnimalData prefabAnimalData, System.Single distance, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetMaxBrakingSpeed(Game.Prefabs.AnimalData prefabAnimalData, System.Single distance, System.Single timeStep);
```

- `public static GetMaxBrakingSpeed(Game.Prefabs.AnimalData prefabAnimalData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetMaxBrakingSpeed(Game.Prefabs.AnimalData prefabAnimalData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep);
```

- `public static GetNavigationSize(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData) : System.Single`  

```csharp
public static System.Single GetNavigationSize(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData);
```

- `public static GetQueueArea(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Unity.Mathematics.float3 position) : Colossal.Mathematics.Sphere3`  

```csharp
public static Colossal.Mathematics.Sphere3 GetQueueArea(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Unity.Mathematics.float3 position);
```

- `public static GetQueueArea(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Unity.Mathematics.float3 position1, Unity.Mathematics.float3 position2) : Colossal.Mathematics.Sphere3`  

```csharp
public static Colossal.Mathematics.Sphere3 GetQueueArea(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Unity.Mathematics.float3 position1, Unity.Mathematics.float3 position2);
```

- `public static GetVehicleDoorPosition(Unity.Mathematics.Random& random, Game.Prefabs.ActivityType activityType, Game.Prefabs.ActivityCondition conditions, Game.Objects.Transform vehicleTransform, Unity.Mathematics.float3 targetPosition, System.Boolean isDriver, System.Boolean lefthandTraffic, Unity.Entities.Entity creaturePrefab, Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Rendering.MeshGroup> meshGroups, Unity.Entities.ComponentLookup`1[[Game.Vehicles.PublicTransport, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& publicTransports, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Train, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trains, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Controller, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& controllers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.CarData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabCarDatas, Unity.Entities.BufferLookup`1[[Game.Prefabs.ActivityLocationElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabActivityLocations, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMeshGroup, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshGroupBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.CharacterElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& characterElementBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationClip, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationClipBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationMotionBuffers, Game.Prefabs.ActivityMask& activityMask, Game.Rendering.AnimatedPropID& propID) : Game.Objects.Transform`  

```csharp
public static Game.Objects.Transform GetVehicleDoorPosition(Unity.Mathematics.Random& random, Game.Prefabs.ActivityType activityType, Game.Prefabs.ActivityCondition conditions, Game.Objects.Transform vehicleTransform, Unity.Mathematics.float3 targetPosition, System.Boolean isDriver, System.Boolean lefthandTraffic, Unity.Entities.Entity creaturePrefab, Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Rendering.MeshGroup> meshGroups, Unity.Entities.ComponentLookup`1[[Game.Vehicles.PublicTransport, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& publicTransports, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Train, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trains, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Controller, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& controllers, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefs, Unity.Entities.ComponentLookup`1[[Game.Prefabs.CarData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabCarDatas, Unity.Entities.BufferLookup`1[[Game.Prefabs.ActivityLocationElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabActivityLocations, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMeshGroup, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshGroupBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.CharacterElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& characterElementBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.SubMesh, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subMeshBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationClip, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationClipBuffers, Unity.Entities.BufferLookup`1[[Game.Prefabs.AnimationMotion, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& animationMotionBuffers, Game.Prefabs.ActivityMask& activityMask, Game.Rendering.AnimatedPropID& propID);
```

- `public static IsStuck(Game.Pathfind.PathOwner pathOwner) : System.Boolean`  

```csharp
public static System.Boolean IsStuck(Game.Pathfind.PathOwner pathOwner);
```

- `public static IsStuck(Game.Creatures.AnimalCurrentLane currentLane) : System.Boolean`  

```csharp
public static System.Boolean IsStuck(Game.Creatures.AnimalCurrentLane currentLane);
```

- `public static ParkingSpaceReached(Game.Creatures.HumanCurrentLane currentLane) : System.Boolean`  

```csharp
public static System.Boolean ParkingSpaceReached(Game.Creatures.HumanCurrentLane currentLane);
```

- `public static PathEndReached(Game.Creatures.HumanCurrentLane currentLane) : System.Boolean`  

```csharp
public static System.Boolean PathEndReached(Game.Creatures.HumanCurrentLane currentLane);
```

- `public static PathEndReached(Game.Creatures.AnimalCurrentLane currentLane) : System.Boolean`  

```csharp
public static System.Boolean PathEndReached(Game.Creatures.AnimalCurrentLane currentLane);
```

- `public static PathfindFailed(Game.Pathfind.PathOwner pathOwner) : System.Boolean`  

```csharp
public static System.Boolean PathfindFailed(Game.Pathfind.PathOwner pathOwner);
```

- `public static RequireNewPath(Game.Pathfind.PathOwner pathOwner) : System.Boolean`  

```csharp
public static System.Boolean RequireNewPath(Game.Pathfind.PathOwner pathOwner);
```

- `public static ResetUncheckedLane(Game.Creatures.HumanCurrentLane& currentLane) : System.Boolean`  

```csharp
public static System.Boolean ResetUncheckedLane(Game.Creatures.HumanCurrentLane& currentLane);
```

- `public static ResetUpdatedPath(Game.Pathfind.PathOwner& pathOwner) : System.Boolean`  

```csharp
public static System.Boolean ResetUpdatedPath(Game.Pathfind.PathOwner& pathOwner);
```

- `public static SetAreaTarget(Unity.Mathematics.float3 prev2, Unity.Mathematics.float3 prev, Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Entities.Entity areaEntity, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Mathematics.float3 comparePosition, Game.Pathfind.PathElement nextElement, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isBackward, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Routes.TaxiStand> taxiStands, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves, Unity.Entities.ComponentLookup<Game.Common.Owner> owners) : System.Boolean`  

```csharp
public static System.Boolean SetAreaTarget(Unity.Mathematics.float3 prev2, Unity.Mathematics.float3 prev, Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Entities.Entity areaEntity, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Mathematics.float3 comparePosition, Game.Pathfind.PathElement nextElement, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isBackward, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Routes.TaxiStand> taxiStands, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves, Unity.Entities.ComponentLookup<Game.Common.Owner> owners);
```

- `public static SetQueue(Unity.Entities.Entity& queueEntity, Colossal.Mathematics.Sphere3& queueArea, Unity.Entities.Entity setEntity, Colossal.Mathematics.Sphere3 setArea) : System.Void`  

```csharp
public static System.Void SetQueue(Unity.Entities.Entity& queueEntity, Colossal.Mathematics.Sphere3& queueArea, Unity.Entities.Entity setEntity, Colossal.Mathematics.Sphere3 setArea);
```

- `public static SetRandomAreaTarget(Unity.Mathematics.Random& random, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.ConnectionLane> connectionLaneData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, Unity.Entities.BufferLookup<Game.Areas.Node> areaNodes, Unity.Entities.BufferLookup<Game.Areas.Triangle> areaTriangles) : System.Void`  

```csharp
public static System.Void SetRandomAreaTarget(Unity.Mathematics.Random& random, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.ConnectionLane> connectionLaneData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, Unity.Entities.BufferLookup<Game.Areas.Node> areaNodes, Unity.Entities.BufferLookup<Game.Areas.Triangle> areaTriangles);
```

- `public static SetTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 comparePosition, Game.Pathfind.PathElement nextElement, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Routes.TaxiStand> taxiStands, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves) : System.Boolean`  

```csharp
public static System.Boolean SetTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 comparePosition, Game.Pathfind.PathElement nextElement, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Routes.TaxiStand> taxiStands, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves);
```

- `public static SetupPathfind(Game.Creatures.HumanCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> queue, Game.Pathfind.SetupQueueItem item) : System.Void`  

```csharp
public static System.Void SetupPathfind(Game.Creatures.HumanCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> queue, Game.Pathfind.SetupQueueItem item);
```

- `public static TransportStopReached(Game.Creatures.HumanCurrentLane currentLane) : System.Boolean`  

```csharp
public static System.Boolean TransportStopReached(Game.Creatures.HumanCurrentLane currentLane);
```


## Nested types

- `Game.Creatures.CreatureUtils+ActivityLocationIterator`  

