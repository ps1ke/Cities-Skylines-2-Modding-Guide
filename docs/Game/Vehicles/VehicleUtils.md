# Game.Vehicles.VehicleUtils

**Assembly:** `Game`  
**Namespace:** `Game.Vehicles`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class VehicleUtils
{
    public static const System.Single MAX_VEHICLE_SPEED;
    public static const System.Single MAX_CAR_SPEED;
    public static const System.Single MAX_TRAIN_SPEED;
    public static const System.Single MAX_WATERCRAFT_SPEED;
    public static const System.Single MAX_HELICOPTER_SPEED;
    public static const System.Single MAX_AIRPLANE_SPEED;
    public static const System.Single MAX_CAR_LENGTH;
    public static const System.Single PARALLEL_PARKING_OFFSET;
    public static const System.Single CAR_CRAWL_SPEED;
    public static const System.Single CAR_AREA_SPEED;
    public static const System.Single MIN_HIGHWAY_SPEED;
    public static const System.Single MAX_WATERCRAFT_LENGTH;
    public static const System.Single WATERCRAFT_AREA_SPEED;
    public static const System.Single MAX_FIRE_ENGINE_EXTINGUISH_DISTANCE;
    public static const System.Single MAX_POLICE_ACCIDENT_TARGET_DISTANCE;
    public static const System.Single MAX_MAINTENANCE_TARGET_DISTANCE;
    public static const System.UInt32 MAINTENANCE_DESTROYED_CLEAR_AMOUNT;
    public static const System.Single MAX_TRAIN_LENGTH;
    public static const System.Single TRAIN_CRAWL_SPEED;
    public static const System.Single MAX_TRAIN_CARRIAGE_LENGTH;
    public static const System.Single MAX_TRAM_CARRIAGE_LENGTH;
    public static const System.Single MAX_SUBWAY_LENGTH;
    public static const System.Single MAX_SUBWAY_CARRIAGE_LENGTH;
    public static const System.Int32 CAR_NAVIGATION_LANE_CAPACITY;
    public static const System.Int32 CAR_PARALLEL_LANE_CAPACITY;
    public static const System.Int32 WATERCRAFT_NAVIGATION_LANE_CAPACITY;
    public static const System.Int32 WATERCRAFT_PARALLEL_LANE_CAPACITY;
    public static const System.Int32 AIRCRAFT_NAVIGATION_LANE_CAPACITY;
    public static const System.Single MIN_HELICOPTER_NAVIGATION_DISTANCE;
    public static const System.Single MIN_AIRPLANE_NAVIGATION_DISTANCE;
    public static const System.Single AIRPLANE_FLY_HEIGHT;
    public static const System.Single HELICOPTER_FLY_HEIGHT;
    public static const System.Single ROCKET_FLY_HEIGHT;
    public static const System.UInt32 BOTTLENECK_LIMIT;
    public static const System.UInt32 STUCK_MAX_COUNT;
    public static const System.Int32 STUCK_MAX_SPEED;
    public static const System.Single TEMP_WAIT_TIME;
    public static const System.Single DELIVERY_PATHFIND_RANDOM_COST;
    public static const System.Single SERVICE_PATHFIND_RANDOM_COST;
    public static const System.Int32 PRIORITY_OFFSET;
    public static const System.Int32 NORMAL_CAR_PRIORITY;
    public static const System.Int32 TRACK_RESERVE_PRIORITY;
    public static const System.Int32 REQUEST_SPACE_PRIORITY;
    public static const System.Int32 EMERGENCY_YIELD_PRIORITY;
    public static const System.Int32 NORMAL_TRAIN_PRIORITY;
    public static const System.Int32 EMERGENCY_FLEE_PRIORITY;
    public static const System.Int32 EMERGENCY_CAR_PRIORITY;
    public static const System.Int32 PRIMARY_TRAIN_PRIORITY;
    public static const System.Int32 SMALL_WATERCRAFT_PRIORITY;
    public static const System.Int32 MEDIUM_WATERCRAFT_PRIORITY;
    public static const System.Int32 LARGE_WATERCRAFT_PRIORITY;
    public static const System.Int32 NORMAL_AIRCRAFT_PRIORITY;

    private static Unity.Mathematics.float3 CalculateAreaTarget(Unity.Mathematics.float3 prev2, Unity.Mathematics.float3 prev, Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 comparePosition, System.Single minDistance, System.Single lanePosition, System.Single navigationSize, System.Boolean& farEnough);
    public static System.Single CalculateLength(Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.TrainData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabTrainData);
    public static Game.Objects.Transform CalculateParkingSpaceTarget(Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData parkingLaneData, Game.Prefabs.ObjectGeometryData prefabGeometryData, Game.Net.Curve curve, Game.Objects.Transform ownerTransform, System.Single curvePos);
    public static System.Void CalculateParkingSpaceTarget(Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData parkingLaneData, Game.Prefabs.ObjectGeometryData prefabGeometryData, Game.Net.Curve curve, Game.Objects.Transform ownerTransform, System.Single curvePos, Unity.Mathematics.float3& position, Unity.Mathematics.float3& forward, Unity.Mathematics.float3& up);
    public static System.Void CalculateShipNavigationPivots(Game.Objects.Transform transform, Game.Prefabs.ObjectGeometryData prefabGeometryData, Unity.Mathematics.float3& pivot1, Unity.Mathematics.float3& pivot2);
    public static Colossal.Mathematics.Bounds1 CalculateSpeedRange(Game.Prefabs.CarData prefabCarData, System.Single currentSpeed, System.Single timeStep);
    public static Colossal.Mathematics.Bounds1 CalculateSpeedRange(Game.Prefabs.TrainData prefabTrainData, System.Single currentSpeed, System.Single timeStep);
    public static Colossal.Mathematics.Bounds1 CalculateSpeedRange(Game.Prefabs.WatercraftData prefabWatercraftData, System.Single currentSpeed, System.Single timeStep);
    public static Colossal.Mathematics.Bounds1 CalculateSpeedRange(Game.Prefabs.AircraftData prefabAircraftData, System.Single currentSpeed, System.Single timeStep);
    public static Colossal.Mathematics.Bounds1 CalculateSpeedRange(Game.Prefabs.HelicopterData prefabHelicopterData, System.Single currentSpeed, System.Single timeStep);
    public static Colossal.Mathematics.Bounds1 CalculateSpeedRange(Game.Prefabs.AirplaneData prefabAirplaneData, System.Single currentSpeed, System.Single timeStep);
    public static System.Void CalculateTrainNavigationPivots(Game.Objects.Transform transform, Game.Prefabs.TrainData prefabTrainData, Unity.Mathematics.float3& pivot1, Unity.Mathematics.float3& pivot2);
    public static Game.Objects.Transform CalculateTransform(Game.Net.Curve curve, System.Single curvePos);
    public static System.Boolean CalculateTransformPosition(Unity.Mathematics.float3& position, Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Routes.Position> positions, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> prefabBuildingDatas);
    private static Unity.Mathematics.float3 CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 lastTarget, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves);
    private static Unity.Mathematics.float3 CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 lastTarget, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves);
    private static Unity.Mathematics.float3 CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 target, System.Single navigationSize, System.Boolean isSingle);
    private static Unity.Mathematics.float3 CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle);
    public static System.Boolean CanUseLane(Game.Pathfind.PathMethod methods, Game.Net.RoadTypes roadTypes, Game.Prefabs.CarLaneData carLaneData);
    public static System.Void CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Vehicles.CarCurrentLane currentLane, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer);
    public static System.Void CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Vehicles.TrainCurrentLane currentLane, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer);
    public static System.Void CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Vehicles.AircraftCurrentLane currentLane, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer);
    public static System.Void CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Vehicles.WatercraftCurrentLane currentLane, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer);
    private static System.Void ClampPosition(Unity.Mathematics.float3& position, Unity.Mathematics.float3 original, System.Single maxDistance);
    public static System.Void ClearEndOfPath(Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes);
    public static System.Void ClearEndOfPath(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes);
    public static System.Void ClearEndOfPath(Game.Vehicles.AircraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.AircraftNavigationLane> navigationLanes);
    public static System.Void ClearEndOfPath(Game.Vehicles.TrainCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.TrainNavigationLane> navigationLanes);
    public static System.Void ClearNavigationForPathfind(Game.Objects.Moving moving, Game.Prefabs.CarData prefabCarData, Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Entities.ComponentLookup`1[[Game.Net.CarLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& carLaneLookup, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveLookup);
    public static System.Void DeleteVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout);
    public static System.Void DeleteVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout);
    public static System.Boolean FindFreeParkingSpace(Unity.Mathematics.Random& random, Unity.Entities.Entity lane, System.Single minT, System.Single parkingLength, System.Single parkingOffset, System.Single& curvePos, Unity.Entities.ComponentLookup`1[[Game.Vehicles.ParkedCar, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Objects.Unspawned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unspawnedData, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ParkingLaneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabParkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabObjectGeometryData, Unity.Entities.BufferLookup`1[[Game.Net.LaneObject, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneObjectData, Unity.Entities.BufferLookup`1[[Game.Net.LaneOverlap, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneOverlapData, System.Boolean ignoreDriveways, System.Boolean ignoreDisabled);
    public static System.Int32 GetAllBuyingResourcesTrucks(Unity.Entities.Entity destination, Game.Economy.Resource resource, Unity.Entities.ComponentLookup`1[[Game.Vehicles.DeliveryTruck, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trucks, Unity.Entities.BufferLookup`1[[Game.Vehicles.GuestVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& guestVehiclesBufs, Unity.Entities.BufferLookup`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layoutsBufs);
    public static System.Single GetBrakingDistance(Game.Prefabs.CarData prefabCarData, System.Single speed, System.Single timeStep);
    public static System.Single GetBrakingDistance(Game.Prefabs.TrainData prefabTrainData, System.Single speed, System.Single timeStep);
    public static System.Single GetBrakingDistance(Game.Prefabs.WatercraftData prefabWatercraftData, System.Single speed, System.Single timeStep);
    public static System.Single GetBrakingDistance(Game.Prefabs.AircraftData prefabAircraftData, System.Single speed, System.Single timeStep);
    public static System.Single GetBrakingDistance(Game.Prefabs.HelicopterData prefabHelicopterData, System.Single speed, System.Single timeStep);
    public static System.Single GetBrakingDistance(Game.Prefabs.AirplaneData prefabAirplaneData, System.Single speed, System.Single timeStep);
    public static System.Int32 GetBuyingTrucksLoad(Unity.Entities.Entity vehicle, Game.Economy.Resource resource, Unity.Entities.ComponentLookup`1[[Game.Vehicles.DeliveryTruck, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trucks, Unity.Entities.BufferLookup`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layouts);
    public static Colossal.Mathematics.Bounds3 GetConnectionParkingBounds(Game.Net.ConnectionLane connectionLane, Colossal.Mathematics.Bezier4x3 curve);
    public static Unity.Mathematics.float3 GetConnectionParkingPosition(Game.Net.ConnectionLane connectionLane, Colossal.Mathematics.Bezier4x3 curve, System.Single curvePosition);
    public static System.Void GetDrivingStyle(System.UInt32 simulationFrame, Game.Common.PseudoRandomSeed randomSeed, System.Single& safetyTime);
    public static Game.Net.CarLaneFlags GetForbiddenLaneFlags(Game.Vehicles.Car carData);
    public static Game.Pathfind.RuleFlags GetIgnoredPathfindRules(Game.Prefabs.CarData carData);
    public static Game.Pathfind.RuleFlags GetIgnoredPathfindRulesTaxiDefaults();
    public static System.Single GetLaneOffset(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Game.Prefabs.NetLaneData prefabLaneData, System.Single lanePosition);
    public static Unity.Mathematics.float3 GetLanePosition(Colossal.Mathematics.Bezier4x3 curve, System.Single curvePosition, System.Single laneOffset);
    public static System.Single GetMaxBrakingSpeed(Game.Prefabs.CarData prefabCarData, System.Single distance, System.Single timeStep);
    public static System.Single GetMaxBrakingSpeed(Game.Prefabs.CarData prefabCarData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep);
    public static System.Single GetMaxBrakingSpeed(Game.Prefabs.TrainData prefabTrainData, System.Single distance, System.Single timeStep);
    public static System.Single GetMaxBrakingSpeed(Game.Prefabs.TrainData prefabTrainData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep);
    public static System.Single GetMaxBrakingSpeed(Game.Prefabs.WatercraftData prefabWatercraftData, System.Single distance, System.Single timeStep);
    public static System.Single GetMaxBrakingSpeed(Game.Prefabs.WatercraftData prefabWatercraftData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep);
    public static System.Single GetMaxBrakingSpeed(Game.Prefabs.AircraftData prefabAircraftData, System.Single distance, System.Single timeStep);
    public static System.Single GetMaxBrakingSpeed(Game.Prefabs.HelicopterData prefabHelicopterData, System.Single distance, System.Single timeStep);
    public static System.Single GetMaxBrakingSpeed(Game.Prefabs.AirplaneData prefabAirplaneData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep);
    public static System.Single GetMaxBrakingSpeed(Game.Prefabs.AircraftData prefabAircraftData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep);
    public static System.Single GetMaxDriveSpeed(Game.Prefabs.CarData prefabCarData, Game.Net.CarLane carLaneData);
    public static System.Single GetMaxDriveSpeed(Game.Prefabs.CarData prefabCarData, System.Single speedLimit, System.Single curviness);
    public static System.Single GetMaxDriveSpeed(Game.Prefabs.TrainData prefabTrainData, Game.Net.TrackLane trackLaneData);
    public static System.Single GetMaxDriveSpeed(Game.Prefabs.TrainData prefabTrainData, System.Single speedLimit, System.Single curviness);
    public static System.Single GetMaxDriveSpeed(Game.Prefabs.WatercraftData prefabWatercraftData, Game.Net.CarLane carLaneData);
    public static System.Single GetMaxDriveSpeed(Game.Prefabs.WatercraftData prefabWatercraftData, System.Single speedLimit, System.Single curviness);
    public static System.Single GetMaxDriveSpeed(Game.Prefabs.AircraftData prefabAircraftData, Game.Net.CarLane carLaneData);
    public static System.Single GetMaxDriveSpeed(Game.Prefabs.AircraftData prefabAircraftData, System.Single speedLimit, System.Single curviness);
    public static System.Single GetNavigationSize(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData);
    public static Unity.Mathematics.float2 GetParkingOffsets(Unity.Entities.Entity car, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectGeometryData);
    public static Unity.Mathematics.float2 GetParkingSize(Game.Prefabs.ParkingLaneData parkingLaneData);
    public static Unity.Mathematics.float2 GetParkingSize(Unity.Entities.Entity car, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectGeometryData);
    public static Unity.Mathematics.float2 GetParkingSize(Unity.Entities.Entity car, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectGeometryData, System.Single& offset);
    public static Unity.Mathematics.float2 GetParkingSize(Game.Prefabs.ObjectGeometryData objectGeometry, System.Single& offset);
    public static Unity.Entities.Entity GetParkingSource(Unity.Entities.Entity entity, Game.Vehicles.CarCurrentLane currentLane, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData);
    public static System.Boolean GetPathElement(System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathElement& pathElement);
    public static System.Boolean GetPathElement(System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathElement& pathElement);
    public static Game.Pathfind.PathMethod GetPathMethods(Game.Prefabs.CarLaneData carLaneData);
    public static Game.Pathfind.PathMethod GetPathMethods(Game.Prefabs.CarData carData);
    public static Game.Pathfind.PathMethod GetPathMethods(Game.Prefabs.WatercraftData watercraftData);
    public static Game.Pathfind.PathMethod GetPathMethods(Game.Prefabs.AircraftData aircraftData);
    public static Game.Net.CarLaneFlags GetPreferredLaneFlags(Game.Vehicles.Car carData);
    public static System.Int32 GetPriority(Game.Vehicles.Car carData);
    public static System.Int32 GetPriority(Game.Prefabs.TrainData trainData);
    public static System.Int32 GetPriority(Game.Prefabs.WatercraftData prefabWatercraftData);
    public static System.Int32 GetPriority(Game.Prefabs.AircraftData prefabAircraftData);
    public static System.Single GetSignalDistance(Game.Prefabs.TrainData prefabTrainData, System.Single speed);
    public static System.Single GetSpeedLimitFactor(Game.Vehicles.Car carData);
    public static System.Boolean IsCarLane(Unity.Entities.Entity lane, Unity.Entities.ComponentLookup`1[[Game.Net.CarLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& carLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Objects.SpawnLocation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnLocationData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnLocationData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabSpawnLocationData);
    public static System.Boolean IsParkingLane(Unity.Entities.Entity lane, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData);
    public static System.Boolean IsReversedPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.ComponentLookup<Game.Vehicles.TrainCurrentLane> currentLaneData, Unity.Entities.ComponentLookup<Game.Vehicles.Train> trainData, Unity.Entities.ComponentLookup<Game.Objects.Transform> transformData);
    public static System.Boolean IsStuck(Game.Pathfind.PathOwner pathOwner);
    public static System.Void ModifyDriveSpeed(System.Single& driveSpeed, Game.Net.LaneCondition condition);
    private static System.Boolean MoveBufferPosition(Unity.Mathematics.float3 comparePosition, Game.Vehicles.TrainBogiePosition& targetPosition, System.Single minDistance, Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float2& curveDelta);
    public static System.Boolean ParkingSpaceReached(Game.Vehicles.CarCurrentLane currentLane, Game.Pathfind.PathOwner pathOwner);
    public static System.Boolean ParkingSpaceReached(Game.Vehicles.AircraftCurrentLane currentLane, Game.Pathfind.PathOwner pathOwner);
    public static System.Boolean PathEndReached(Game.Vehicles.CarCurrentLane currentLane);
    public static System.Boolean PathEndReached(Game.Vehicles.TrainCurrentLane currentLane);
    public static System.Boolean PathEndReached(Game.Vehicles.WatercraftCurrentLane currentLane);
    public static System.Boolean PathEndReached(Game.Vehicles.AircraftCurrentLane currentLane);
    public static System.Boolean PathfindFailed(Game.Pathfind.PathOwner pathOwner);
    public static System.Boolean QueueReached(Game.Vehicles.CarCurrentLane currentLane);
    public static System.Boolean RequireNewPath(Game.Pathfind.PathOwner pathOwner);
    public static System.Void ResetParkingLaneStatus(Unity.Entities.Entity entity, Game.Vehicles.CarCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.EntityStorageInfoLookup& entityLookup, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.CarLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& carLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Objects.SpawnLocation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnLocationData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnLocationData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabSpawnLocationData);
    public static System.Boolean ResetUpdatedPath(Game.Pathfind.PathOwner& pathOwner);
    public static System.Boolean ReturnEndReached(Game.Vehicles.TrainCurrentLane currentLane);
    public static System.Void ReverseCarriage(Unity.Entities.Entity vehicle, Unity.Entities.Entity lastLane, System.Single lastCurvePos, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Train, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trainData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainCurrentLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentLaneData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainNavigation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& navigationData, Game.Vehicles.TrainBogieCache& rearCache);
    public static System.Void ReverseTrain(Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Train, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trainData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainCurrentLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentLaneData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainNavigation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& navigationData);
    public static System.Boolean SetAreaTarget(Unity.Mathematics.float3 prev2, Unity.Mathematics.float3 prev, Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Entities.Entity areaEntity, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Mathematics.float3 comparePosition, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isBackward, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves, Unity.Entities.ComponentLookup<Game.Common.Owner> owners);
    public static System.Boolean SetAreaTarget(Unity.Mathematics.float3 prev2, Unity.Mathematics.float3 prev, Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Entities.Entity areaEntity, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Mathematics.float3 comparePosition, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isBackward, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves, Unity.Entities.ComponentLookup<Game.Common.Owner> owners);
    public static System.Int32 SetParkingCurvePos(Unity.Entities.Entity entity, Unity.Mathematics.Random& random, Game.Vehicles.CarCurrentLane currentLane, Game.Pathfind.PathOwner pathOwner, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Vehicles.ParkedCar, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarData, Unity.Entities.ComponentLookup`1[[Game.Objects.Unspawned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unspawnedData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabObjectGeometryData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ParkingLaneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabParkingLaneData, Unity.Entities.BufferLookup`1[[Game.Net.LaneObject, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneObjectData, Unity.Entities.BufferLookup`1[[Game.Net.LaneOverlap, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneOverlapData, System.Boolean ignoreDriveways);
    public static System.Void SetParkingCurvePos(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, System.Int32 index, Unity.Entities.Entity currentLane, System.Single curvePos, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData);
    public static System.Void SetParkingCurvePos(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, Game.Vehicles.CarCurrentLane& currentLaneData, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navLanes, System.Int32 navIndex, System.Single curvePos, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData);
    public static System.Void SetTarget(Game.Pathfind.PathOwner& pathOwner, Game.Common.Target& targetData, Unity.Entities.Entity newTarget);
    public static System.Boolean SetTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 comparePosition, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves);
    public static System.Boolean SetTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 comparePosition, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves);
    public static System.Boolean SetTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 comparePosition, Unity.Mathematics.float3 lastTarget, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single navigationSize, System.Boolean isSingle);
    public static System.Void SetupPathfind(Game.Vehicles.CarCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> queue, Game.Pathfind.SetupQueueItem item);
    public static System.Void SetupPathfind(Game.Vehicles.TrainCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> queue, Game.Pathfind.SetupQueueItem item);
    public static System.Void SetupPathfind(Game.Vehicles.WatercraftCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> queue, Game.Pathfind.SetupQueueItem item);
    public static System.Void SetupPathfind(Game.Vehicles.AircraftCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> queue, Game.Pathfind.SetupQueueItem item);
    public static System.Void UpdateCarriageLocations(Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout, Unity.Collections.NativeList<Game.Pathfind.PathElement> laneBuffer, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Train, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trainData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.ParkedTrain, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedTrainData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainCurrentLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentLaneData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainNavigation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& navigationData, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transformData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.TrainData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabTrainData);
    public static Unity.Entities.Entity ValidateParkingSpace(Unity.Entities.Entity entity, Unity.Mathematics.Random& random, Game.Vehicles.CarCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Vehicles.ParkedCar, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Blocker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& blockerData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Objects.Unspawned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unspawnedData, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.GarageLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& garageLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ParkingLaneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabParkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabObjectGeometryData, Unity.Entities.BufferLookup`1[[Game.Net.LaneObject, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneObjectData, Unity.Entities.BufferLookup`1[[Game.Net.LaneOverlap, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneOverlapData, System.Boolean ignoreDriveways, System.Boolean ignoreDisabled, System.Boolean boardingOnly);
    public static System.Boolean WaypointReached(Game.Vehicles.CarCurrentLane currentLane);
}
```


## Fields

- `public static const System.Single MAX_VEHICLE_SPEED`  

```csharp
public static const System.Single MAX_VEHICLE_SPEED;
```

- `public static const System.Single MAX_CAR_SPEED`  

```csharp
public static const System.Single MAX_CAR_SPEED;
```

- `public static const System.Single MAX_TRAIN_SPEED`  

```csharp
public static const System.Single MAX_TRAIN_SPEED;
```

- `public static const System.Single MAX_WATERCRAFT_SPEED`  

```csharp
public static const System.Single MAX_WATERCRAFT_SPEED;
```

- `public static const System.Single MAX_HELICOPTER_SPEED`  

```csharp
public static const System.Single MAX_HELICOPTER_SPEED;
```

- `public static const System.Single MAX_AIRPLANE_SPEED`  

```csharp
public static const System.Single MAX_AIRPLANE_SPEED;
```

- `public static const System.Single MAX_CAR_LENGTH`  

```csharp
public static const System.Single MAX_CAR_LENGTH;
```

- `public static const System.Single PARALLEL_PARKING_OFFSET`  

```csharp
public static const System.Single PARALLEL_PARKING_OFFSET;
```

- `public static const System.Single CAR_CRAWL_SPEED`  

```csharp
public static const System.Single CAR_CRAWL_SPEED;
```

- `public static const System.Single CAR_AREA_SPEED`  

```csharp
public static const System.Single CAR_AREA_SPEED;
```

- `public static const System.Single MIN_HIGHWAY_SPEED`  

```csharp
public static const System.Single MIN_HIGHWAY_SPEED;
```

- `public static const System.Single MAX_WATERCRAFT_LENGTH`  

```csharp
public static const System.Single MAX_WATERCRAFT_LENGTH;
```

- `public static const System.Single WATERCRAFT_AREA_SPEED`  

```csharp
public static const System.Single WATERCRAFT_AREA_SPEED;
```

- `public static const System.Single MAX_FIRE_ENGINE_EXTINGUISH_DISTANCE`  

```csharp
public static const System.Single MAX_FIRE_ENGINE_EXTINGUISH_DISTANCE;
```

- `public static const System.Single MAX_POLICE_ACCIDENT_TARGET_DISTANCE`  

```csharp
public static const System.Single MAX_POLICE_ACCIDENT_TARGET_DISTANCE;
```

- `public static const System.Single MAX_MAINTENANCE_TARGET_DISTANCE`  

```csharp
public static const System.Single MAX_MAINTENANCE_TARGET_DISTANCE;
```

- `public static const System.UInt32 MAINTENANCE_DESTROYED_CLEAR_AMOUNT`  

```csharp
public static const System.UInt32 MAINTENANCE_DESTROYED_CLEAR_AMOUNT;
```

- `public static const System.Single MAX_TRAIN_LENGTH`  

```csharp
public static const System.Single MAX_TRAIN_LENGTH;
```

- `public static const System.Single TRAIN_CRAWL_SPEED`  

```csharp
public static const System.Single TRAIN_CRAWL_SPEED;
```

- `public static const System.Single MAX_TRAIN_CARRIAGE_LENGTH`  

```csharp
public static const System.Single MAX_TRAIN_CARRIAGE_LENGTH;
```

- `public static const System.Single MAX_TRAM_CARRIAGE_LENGTH`  

```csharp
public static const System.Single MAX_TRAM_CARRIAGE_LENGTH;
```

- `public static const System.Single MAX_SUBWAY_LENGTH`  

```csharp
public static const System.Single MAX_SUBWAY_LENGTH;
```

- `public static const System.Single MAX_SUBWAY_CARRIAGE_LENGTH`  

```csharp
public static const System.Single MAX_SUBWAY_CARRIAGE_LENGTH;
```

- `public static const System.Int32 CAR_NAVIGATION_LANE_CAPACITY`  

```csharp
public static const System.Int32 CAR_NAVIGATION_LANE_CAPACITY;
```

- `public static const System.Int32 CAR_PARALLEL_LANE_CAPACITY`  

```csharp
public static const System.Int32 CAR_PARALLEL_LANE_CAPACITY;
```

- `public static const System.Int32 WATERCRAFT_NAVIGATION_LANE_CAPACITY`  

```csharp
public static const System.Int32 WATERCRAFT_NAVIGATION_LANE_CAPACITY;
```

- `public static const System.Int32 WATERCRAFT_PARALLEL_LANE_CAPACITY`  

```csharp
public static const System.Int32 WATERCRAFT_PARALLEL_LANE_CAPACITY;
```

- `public static const System.Int32 AIRCRAFT_NAVIGATION_LANE_CAPACITY`  

```csharp
public static const System.Int32 AIRCRAFT_NAVIGATION_LANE_CAPACITY;
```

- `public static const System.Single MIN_HELICOPTER_NAVIGATION_DISTANCE`  

```csharp
public static const System.Single MIN_HELICOPTER_NAVIGATION_DISTANCE;
```

- `public static const System.Single MIN_AIRPLANE_NAVIGATION_DISTANCE`  

```csharp
public static const System.Single MIN_AIRPLANE_NAVIGATION_DISTANCE;
```

- `public static const System.Single AIRPLANE_FLY_HEIGHT`  

```csharp
public static const System.Single AIRPLANE_FLY_HEIGHT;
```

- `public static const System.Single HELICOPTER_FLY_HEIGHT`  

```csharp
public static const System.Single HELICOPTER_FLY_HEIGHT;
```

- `public static const System.Single ROCKET_FLY_HEIGHT`  

```csharp
public static const System.Single ROCKET_FLY_HEIGHT;
```

- `public static const System.UInt32 BOTTLENECK_LIMIT`  

```csharp
public static const System.UInt32 BOTTLENECK_LIMIT;
```

- `public static const System.UInt32 STUCK_MAX_COUNT`  

```csharp
public static const System.UInt32 STUCK_MAX_COUNT;
```

- `public static const System.Int32 STUCK_MAX_SPEED`  

```csharp
public static const System.Int32 STUCK_MAX_SPEED;
```

- `public static const System.Single TEMP_WAIT_TIME`  

```csharp
public static const System.Single TEMP_WAIT_TIME;
```

- `public static const System.Single DELIVERY_PATHFIND_RANDOM_COST`  

```csharp
public static const System.Single DELIVERY_PATHFIND_RANDOM_COST;
```

- `public static const System.Single SERVICE_PATHFIND_RANDOM_COST`  

```csharp
public static const System.Single SERVICE_PATHFIND_RANDOM_COST;
```

- `public static const System.Int32 PRIORITY_OFFSET`  

```csharp
public static const System.Int32 PRIORITY_OFFSET;
```

- `public static const System.Int32 NORMAL_CAR_PRIORITY`  

```csharp
public static const System.Int32 NORMAL_CAR_PRIORITY;
```

- `public static const System.Int32 TRACK_RESERVE_PRIORITY`  

```csharp
public static const System.Int32 TRACK_RESERVE_PRIORITY;
```

- `public static const System.Int32 REQUEST_SPACE_PRIORITY`  

```csharp
public static const System.Int32 REQUEST_SPACE_PRIORITY;
```

- `public static const System.Int32 EMERGENCY_YIELD_PRIORITY`  

```csharp
public static const System.Int32 EMERGENCY_YIELD_PRIORITY;
```

- `public static const System.Int32 NORMAL_TRAIN_PRIORITY`  

```csharp
public static const System.Int32 NORMAL_TRAIN_PRIORITY;
```

- `public static const System.Int32 EMERGENCY_FLEE_PRIORITY`  

```csharp
public static const System.Int32 EMERGENCY_FLEE_PRIORITY;
```

- `public static const System.Int32 EMERGENCY_CAR_PRIORITY`  

```csharp
public static const System.Int32 EMERGENCY_CAR_PRIORITY;
```

- `public static const System.Int32 PRIMARY_TRAIN_PRIORITY`  

```csharp
public static const System.Int32 PRIMARY_TRAIN_PRIORITY;
```

- `public static const System.Int32 SMALL_WATERCRAFT_PRIORITY`  

```csharp
public static const System.Int32 SMALL_WATERCRAFT_PRIORITY;
```

- `public static const System.Int32 MEDIUM_WATERCRAFT_PRIORITY`  

```csharp
public static const System.Int32 MEDIUM_WATERCRAFT_PRIORITY;
```

- `public static const System.Int32 LARGE_WATERCRAFT_PRIORITY`  

```csharp
public static const System.Int32 LARGE_WATERCRAFT_PRIORITY;
```

- `public static const System.Int32 NORMAL_AIRCRAFT_PRIORITY`  

```csharp
public static const System.Int32 NORMAL_AIRCRAFT_PRIORITY;
```


## Methods

- `private static CalculateAreaTarget(Unity.Mathematics.float3 prev2, Unity.Mathematics.float3 prev, Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 comparePosition, System.Single minDistance, System.Single lanePosition, System.Single navigationSize, System.Boolean& farEnough) : Unity.Mathematics.float3`  

```csharp
private static Unity.Mathematics.float3 CalculateAreaTarget(Unity.Mathematics.float3 prev2, Unity.Mathematics.float3 prev, Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 comparePosition, System.Single minDistance, System.Single lanePosition, System.Single navigationSize, System.Boolean& farEnough);
```

- `public static CalculateLength(Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.TrainData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabTrainData) : System.Single`  

```csharp
public static System.Single CalculateLength(Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.TrainData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabTrainData);
```

- `public static CalculateParkingSpaceTarget(Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData parkingLaneData, Game.Prefabs.ObjectGeometryData prefabGeometryData, Game.Net.Curve curve, Game.Objects.Transform ownerTransform, System.Single curvePos) : Game.Objects.Transform`  

```csharp
public static Game.Objects.Transform CalculateParkingSpaceTarget(Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData parkingLaneData, Game.Prefabs.ObjectGeometryData prefabGeometryData, Game.Net.Curve curve, Game.Objects.Transform ownerTransform, System.Single curvePos);
```

- `public static CalculateParkingSpaceTarget(Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData parkingLaneData, Game.Prefabs.ObjectGeometryData prefabGeometryData, Game.Net.Curve curve, Game.Objects.Transform ownerTransform, System.Single curvePos, Unity.Mathematics.float3& position, Unity.Mathematics.float3& forward, Unity.Mathematics.float3& up) : System.Void`  

```csharp
public static System.Void CalculateParkingSpaceTarget(Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData parkingLaneData, Game.Prefabs.ObjectGeometryData prefabGeometryData, Game.Net.Curve curve, Game.Objects.Transform ownerTransform, System.Single curvePos, Unity.Mathematics.float3& position, Unity.Mathematics.float3& forward, Unity.Mathematics.float3& up);
```

- `public static CalculateShipNavigationPivots(Game.Objects.Transform transform, Game.Prefabs.ObjectGeometryData prefabGeometryData, Unity.Mathematics.float3& pivot1, Unity.Mathematics.float3& pivot2) : System.Void`  

```csharp
public static System.Void CalculateShipNavigationPivots(Game.Objects.Transform transform, Game.Prefabs.ObjectGeometryData prefabGeometryData, Unity.Mathematics.float3& pivot1, Unity.Mathematics.float3& pivot2);
```

- `public static CalculateSpeedRange(Game.Prefabs.CarData prefabCarData, System.Single currentSpeed, System.Single timeStep) : Colossal.Mathematics.Bounds1`  

```csharp
public static Colossal.Mathematics.Bounds1 CalculateSpeedRange(Game.Prefabs.CarData prefabCarData, System.Single currentSpeed, System.Single timeStep);
```

- `public static CalculateSpeedRange(Game.Prefabs.TrainData prefabTrainData, System.Single currentSpeed, System.Single timeStep) : Colossal.Mathematics.Bounds1`  

```csharp
public static Colossal.Mathematics.Bounds1 CalculateSpeedRange(Game.Prefabs.TrainData prefabTrainData, System.Single currentSpeed, System.Single timeStep);
```

- `public static CalculateSpeedRange(Game.Prefabs.WatercraftData prefabWatercraftData, System.Single currentSpeed, System.Single timeStep) : Colossal.Mathematics.Bounds1`  

```csharp
public static Colossal.Mathematics.Bounds1 CalculateSpeedRange(Game.Prefabs.WatercraftData prefabWatercraftData, System.Single currentSpeed, System.Single timeStep);
```

- `public static CalculateSpeedRange(Game.Prefabs.AircraftData prefabAircraftData, System.Single currentSpeed, System.Single timeStep) : Colossal.Mathematics.Bounds1`  

```csharp
public static Colossal.Mathematics.Bounds1 CalculateSpeedRange(Game.Prefabs.AircraftData prefabAircraftData, System.Single currentSpeed, System.Single timeStep);
```

- `public static CalculateSpeedRange(Game.Prefabs.HelicopterData prefabHelicopterData, System.Single currentSpeed, System.Single timeStep) : Colossal.Mathematics.Bounds1`  

```csharp
public static Colossal.Mathematics.Bounds1 CalculateSpeedRange(Game.Prefabs.HelicopterData prefabHelicopterData, System.Single currentSpeed, System.Single timeStep);
```

- `public static CalculateSpeedRange(Game.Prefabs.AirplaneData prefabAirplaneData, System.Single currentSpeed, System.Single timeStep) : Colossal.Mathematics.Bounds1`  

```csharp
public static Colossal.Mathematics.Bounds1 CalculateSpeedRange(Game.Prefabs.AirplaneData prefabAirplaneData, System.Single currentSpeed, System.Single timeStep);
```

- `public static CalculateTrainNavigationPivots(Game.Objects.Transform transform, Game.Prefabs.TrainData prefabTrainData, Unity.Mathematics.float3& pivot1, Unity.Mathematics.float3& pivot2) : System.Void`  

```csharp
public static System.Void CalculateTrainNavigationPivots(Game.Objects.Transform transform, Game.Prefabs.TrainData prefabTrainData, Unity.Mathematics.float3& pivot1, Unity.Mathematics.float3& pivot2);
```

- `public static CalculateTransform(Game.Net.Curve curve, System.Single curvePos) : Game.Objects.Transform`  

```csharp
public static Game.Objects.Transform CalculateTransform(Game.Net.Curve curve, System.Single curvePos);
```

- `public static CalculateTransformPosition(Unity.Mathematics.float3& position, Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Routes.Position> positions, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> prefabBuildingDatas) : System.Boolean`  

```csharp
public static System.Boolean CalculateTransformPosition(Unity.Mathematics.float3& position, Unity.Entities.Entity entity, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Routes.Position> positions, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefs, Unity.Entities.ComponentLookup<Game.Prefabs.BuildingData> prefabBuildingDatas);
```

- `private static CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 lastTarget, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves) : Unity.Mathematics.float3`  

```csharp
private static Unity.Mathematics.float3 CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 lastTarget, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves);
```

- `private static CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 lastTarget, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves) : Unity.Mathematics.float3`  

```csharp
private static Unity.Mathematics.float3 CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 lastTarget, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves);
```

- `private static CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 target, System.Single navigationSize, System.Boolean isSingle) : Unity.Mathematics.float3`  

```csharp
private static Unity.Mathematics.float3 CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 target, System.Single navigationSize, System.Boolean isSingle);
```

- `private static CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle) : Unity.Mathematics.float3`  

```csharp
private static Unity.Mathematics.float3 CalculateTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle);
```

- `public static CanUseLane(Game.Pathfind.PathMethod methods, Game.Net.RoadTypes roadTypes, Game.Prefabs.CarLaneData carLaneData) : System.Boolean`  

```csharp
public static System.Boolean CanUseLane(Game.Pathfind.PathMethod methods, Game.Net.RoadTypes roadTypes, Game.Prefabs.CarLaneData carLaneData);
```

- `public static CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Vehicles.CarCurrentLane currentLane, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer) : System.Void`  

```csharp
public static System.Void CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Vehicles.CarCurrentLane currentLane, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer);
```

- `public static CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Vehicles.TrainCurrentLane currentLane, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer) : System.Void`  

```csharp
public static System.Void CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Vehicles.TrainCurrentLane currentLane, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer);
```

- `public static CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Vehicles.AircraftCurrentLane currentLane, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer) : System.Void`  

```csharp
public static System.Void CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Vehicles.AircraftCurrentLane currentLane, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer);
```

- `public static CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Vehicles.WatercraftCurrentLane currentLane, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer) : System.Void`  

```csharp
public static System.Void CheckUnspawned(System.Int32 jobIndex, Unity.Entities.Entity entity, Game.Vehicles.WatercraftCurrentLane currentLane, System.Boolean isUnspawned, Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer);
```

- `private static ClampPosition(Unity.Mathematics.float3& position, Unity.Mathematics.float3 original, System.Single maxDistance) : System.Void`  

```csharp
private static System.Void ClampPosition(Unity.Mathematics.float3& position, Unity.Mathematics.float3 original, System.Single maxDistance);
```

- `public static ClearEndOfPath(Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes) : System.Void`  

```csharp
public static System.Void ClearEndOfPath(Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes);
```

- `public static ClearEndOfPath(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes) : System.Void`  

```csharp
public static System.Void ClearEndOfPath(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes);
```

- `public static ClearEndOfPath(Game.Vehicles.AircraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.AircraftNavigationLane> navigationLanes) : System.Void`  

```csharp
public static System.Void ClearEndOfPath(Game.Vehicles.AircraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.AircraftNavigationLane> navigationLanes);
```

- `public static ClearEndOfPath(Game.Vehicles.TrainCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.TrainNavigationLane> navigationLanes) : System.Void`  

```csharp
public static System.Void ClearEndOfPath(Game.Vehicles.TrainCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.TrainNavigationLane> navigationLanes);
```

- `public static ClearNavigationForPathfind(Game.Objects.Moving moving, Game.Prefabs.CarData prefabCarData, Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Entities.ComponentLookup`1[[Game.Net.CarLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& carLaneLookup, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveLookup) : System.Void`  

```csharp
public static System.Void ClearNavigationForPathfind(Game.Objects.Moving moving, Game.Prefabs.CarData prefabCarData, Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Entities.ComponentLookup`1[[Game.Net.CarLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& carLaneLookup, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveLookup);
```

- `public static DeleteVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout) : System.Void`  

```csharp
public static System.Void DeleteVehicle(Unity.Entities.EntityCommandBuffer commandBuffer, Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout);
```

- `public static DeleteVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout) : System.Void`  

```csharp
public static System.Void DeleteVehicle(Unity.Entities.EntityCommandBuffer+ParallelWriter commandBuffer, System.Int32 jobIndex, Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout);
```

- `public static FindFreeParkingSpace(Unity.Mathematics.Random& random, Unity.Entities.Entity lane, System.Single minT, System.Single parkingLength, System.Single parkingOffset, System.Single& curvePos, Unity.Entities.ComponentLookup`1[[Game.Vehicles.ParkedCar, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Objects.Unspawned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unspawnedData, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ParkingLaneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabParkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabObjectGeometryData, Unity.Entities.BufferLookup`1[[Game.Net.LaneObject, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneObjectData, Unity.Entities.BufferLookup`1[[Game.Net.LaneOverlap, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneOverlapData, System.Boolean ignoreDriveways, System.Boolean ignoreDisabled) : System.Boolean`  

```csharp
public static System.Boolean FindFreeParkingSpace(Unity.Mathematics.Random& random, Unity.Entities.Entity lane, System.Single minT, System.Single parkingLength, System.Single parkingOffset, System.Single& curvePos, Unity.Entities.ComponentLookup`1[[Game.Vehicles.ParkedCar, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Objects.Unspawned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unspawnedData, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ParkingLaneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabParkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabObjectGeometryData, Unity.Entities.BufferLookup`1[[Game.Net.LaneObject, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneObjectData, Unity.Entities.BufferLookup`1[[Game.Net.LaneOverlap, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneOverlapData, System.Boolean ignoreDriveways, System.Boolean ignoreDisabled);
```

- `public static GetAllBuyingResourcesTrucks(Unity.Entities.Entity destination, Game.Economy.Resource resource, Unity.Entities.ComponentLookup`1[[Game.Vehicles.DeliveryTruck, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trucks, Unity.Entities.BufferLookup`1[[Game.Vehicles.GuestVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& guestVehiclesBufs, Unity.Entities.BufferLookup`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layoutsBufs) : System.Int32`  

```csharp
public static System.Int32 GetAllBuyingResourcesTrucks(Unity.Entities.Entity destination, Game.Economy.Resource resource, Unity.Entities.ComponentLookup`1[[Game.Vehicles.DeliveryTruck, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trucks, Unity.Entities.BufferLookup`1[[Game.Vehicles.GuestVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& guestVehiclesBufs, Unity.Entities.BufferLookup`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layoutsBufs);
```

- `public static GetBrakingDistance(Game.Prefabs.CarData prefabCarData, System.Single speed, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetBrakingDistance(Game.Prefabs.CarData prefabCarData, System.Single speed, System.Single timeStep);
```

- `public static GetBrakingDistance(Game.Prefabs.TrainData prefabTrainData, System.Single speed, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetBrakingDistance(Game.Prefabs.TrainData prefabTrainData, System.Single speed, System.Single timeStep);
```

- `public static GetBrakingDistance(Game.Prefabs.WatercraftData prefabWatercraftData, System.Single speed, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetBrakingDistance(Game.Prefabs.WatercraftData prefabWatercraftData, System.Single speed, System.Single timeStep);
```

- `public static GetBrakingDistance(Game.Prefabs.AircraftData prefabAircraftData, System.Single speed, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetBrakingDistance(Game.Prefabs.AircraftData prefabAircraftData, System.Single speed, System.Single timeStep);
```

- `public static GetBrakingDistance(Game.Prefabs.HelicopterData prefabHelicopterData, System.Single speed, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetBrakingDistance(Game.Prefabs.HelicopterData prefabHelicopterData, System.Single speed, System.Single timeStep);
```

- `public static GetBrakingDistance(Game.Prefabs.AirplaneData prefabAirplaneData, System.Single speed, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetBrakingDistance(Game.Prefabs.AirplaneData prefabAirplaneData, System.Single speed, System.Single timeStep);
```

- `public static GetBuyingTrucksLoad(Unity.Entities.Entity vehicle, Game.Economy.Resource resource, Unity.Entities.ComponentLookup`1[[Game.Vehicles.DeliveryTruck, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trucks, Unity.Entities.BufferLookup`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layouts) : System.Int32`  

```csharp
public static System.Int32 GetBuyingTrucksLoad(Unity.Entities.Entity vehicle, Game.Economy.Resource resource, Unity.Entities.ComponentLookup`1[[Game.Vehicles.DeliveryTruck, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trucks, Unity.Entities.BufferLookup`1[[Game.Vehicles.LayoutElement, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& layouts);
```

- `public static GetConnectionParkingBounds(Game.Net.ConnectionLane connectionLane, Colossal.Mathematics.Bezier4x3 curve) : Colossal.Mathematics.Bounds3`  

```csharp
public static Colossal.Mathematics.Bounds3 GetConnectionParkingBounds(Game.Net.ConnectionLane connectionLane, Colossal.Mathematics.Bezier4x3 curve);
```

- `public static GetConnectionParkingPosition(Game.Net.ConnectionLane connectionLane, Colossal.Mathematics.Bezier4x3 curve, System.Single curvePosition) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetConnectionParkingPosition(Game.Net.ConnectionLane connectionLane, Colossal.Mathematics.Bezier4x3 curve, System.Single curvePosition);
```

- `public static GetDrivingStyle(System.UInt32 simulationFrame, Game.Common.PseudoRandomSeed randomSeed, System.Single& safetyTime) : System.Void`  

```csharp
public static System.Void GetDrivingStyle(System.UInt32 simulationFrame, Game.Common.PseudoRandomSeed randomSeed, System.Single& safetyTime);
```

- `public static GetForbiddenLaneFlags(Game.Vehicles.Car carData) : Game.Net.CarLaneFlags`  

```csharp
public static Game.Net.CarLaneFlags GetForbiddenLaneFlags(Game.Vehicles.Car carData);
```

- `public static GetIgnoredPathfindRules(Game.Prefabs.CarData carData) : Game.Pathfind.RuleFlags`  

```csharp
public static Game.Pathfind.RuleFlags GetIgnoredPathfindRules(Game.Prefabs.CarData carData);
```

- `public static GetIgnoredPathfindRulesTaxiDefaults() : Game.Pathfind.RuleFlags`  

```csharp
public static Game.Pathfind.RuleFlags GetIgnoredPathfindRulesTaxiDefaults();
```

- `public static GetLaneOffset(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Game.Prefabs.NetLaneData prefabLaneData, System.Single lanePosition) : System.Single`  

```csharp
public static System.Single GetLaneOffset(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData, Game.Prefabs.NetLaneData prefabLaneData, System.Single lanePosition);
```

- `public static GetLanePosition(Colossal.Mathematics.Bezier4x3 curve, System.Single curvePosition, System.Single laneOffset) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetLanePosition(Colossal.Mathematics.Bezier4x3 curve, System.Single curvePosition, System.Single laneOffset);
```

- `public static GetMaxBrakingSpeed(Game.Prefabs.CarData prefabCarData, System.Single distance, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetMaxBrakingSpeed(Game.Prefabs.CarData prefabCarData, System.Single distance, System.Single timeStep);
```

- `public static GetMaxBrakingSpeed(Game.Prefabs.CarData prefabCarData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetMaxBrakingSpeed(Game.Prefabs.CarData prefabCarData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep);
```

- `public static GetMaxBrakingSpeed(Game.Prefabs.TrainData prefabTrainData, System.Single distance, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetMaxBrakingSpeed(Game.Prefabs.TrainData prefabTrainData, System.Single distance, System.Single timeStep);
```

- `public static GetMaxBrakingSpeed(Game.Prefabs.TrainData prefabTrainData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetMaxBrakingSpeed(Game.Prefabs.TrainData prefabTrainData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep);
```

- `public static GetMaxBrakingSpeed(Game.Prefabs.WatercraftData prefabWatercraftData, System.Single distance, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetMaxBrakingSpeed(Game.Prefabs.WatercraftData prefabWatercraftData, System.Single distance, System.Single timeStep);
```

- `public static GetMaxBrakingSpeed(Game.Prefabs.WatercraftData prefabWatercraftData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetMaxBrakingSpeed(Game.Prefabs.WatercraftData prefabWatercraftData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep);
```

- `public static GetMaxBrakingSpeed(Game.Prefabs.AircraftData prefabAircraftData, System.Single distance, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetMaxBrakingSpeed(Game.Prefabs.AircraftData prefabAircraftData, System.Single distance, System.Single timeStep);
```

- `public static GetMaxBrakingSpeed(Game.Prefabs.HelicopterData prefabHelicopterData, System.Single distance, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetMaxBrakingSpeed(Game.Prefabs.HelicopterData prefabHelicopterData, System.Single distance, System.Single timeStep);
```

- `public static GetMaxBrakingSpeed(Game.Prefabs.AirplaneData prefabAirplaneData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetMaxBrakingSpeed(Game.Prefabs.AirplaneData prefabAirplaneData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep);
```

- `public static GetMaxBrakingSpeed(Game.Prefabs.AircraftData prefabAircraftData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep) : System.Single`  

```csharp
public static System.Single GetMaxBrakingSpeed(Game.Prefabs.AircraftData prefabAircraftData, System.Single distance, System.Single maxResultSpeed, System.Single timeStep);
```

- `public static GetMaxDriveSpeed(Game.Prefabs.CarData prefabCarData, Game.Net.CarLane carLaneData) : System.Single`  

```csharp
public static System.Single GetMaxDriveSpeed(Game.Prefabs.CarData prefabCarData, Game.Net.CarLane carLaneData);
```

- `public static GetMaxDriveSpeed(Game.Prefabs.CarData prefabCarData, System.Single speedLimit, System.Single curviness) : System.Single`  

```csharp
public static System.Single GetMaxDriveSpeed(Game.Prefabs.CarData prefabCarData, System.Single speedLimit, System.Single curviness);
```

- `public static GetMaxDriveSpeed(Game.Prefabs.TrainData prefabTrainData, Game.Net.TrackLane trackLaneData) : System.Single`  

```csharp
public static System.Single GetMaxDriveSpeed(Game.Prefabs.TrainData prefabTrainData, Game.Net.TrackLane trackLaneData);
```

- `public static GetMaxDriveSpeed(Game.Prefabs.TrainData prefabTrainData, System.Single speedLimit, System.Single curviness) : System.Single`  

```csharp
public static System.Single GetMaxDriveSpeed(Game.Prefabs.TrainData prefabTrainData, System.Single speedLimit, System.Single curviness);
```

- `public static GetMaxDriveSpeed(Game.Prefabs.WatercraftData prefabWatercraftData, Game.Net.CarLane carLaneData) : System.Single`  

```csharp
public static System.Single GetMaxDriveSpeed(Game.Prefabs.WatercraftData prefabWatercraftData, Game.Net.CarLane carLaneData);
```

- `public static GetMaxDriveSpeed(Game.Prefabs.WatercraftData prefabWatercraftData, System.Single speedLimit, System.Single curviness) : System.Single`  

```csharp
public static System.Single GetMaxDriveSpeed(Game.Prefabs.WatercraftData prefabWatercraftData, System.Single speedLimit, System.Single curviness);
```

- `public static GetMaxDriveSpeed(Game.Prefabs.AircraftData prefabAircraftData, Game.Net.CarLane carLaneData) : System.Single`  

```csharp
public static System.Single GetMaxDriveSpeed(Game.Prefabs.AircraftData prefabAircraftData, Game.Net.CarLane carLaneData);
```

- `public static GetMaxDriveSpeed(Game.Prefabs.AircraftData prefabAircraftData, System.Single speedLimit, System.Single curviness) : System.Single`  

```csharp
public static System.Single GetMaxDriveSpeed(Game.Prefabs.AircraftData prefabAircraftData, System.Single speedLimit, System.Single curviness);
```

- `public static GetNavigationSize(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData) : System.Single`  

```csharp
public static System.Single GetNavigationSize(Game.Prefabs.ObjectGeometryData prefabObjectGeometryData);
```

- `public static GetParkingOffsets(Unity.Entities.Entity car, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectGeometryData) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 GetParkingOffsets(Unity.Entities.Entity car, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectGeometryData);
```

- `public static GetParkingSize(Game.Prefabs.ParkingLaneData parkingLaneData) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 GetParkingSize(Game.Prefabs.ParkingLaneData parkingLaneData);
```

- `public static GetParkingSize(Unity.Entities.Entity car, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectGeometryData) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 GetParkingSize(Unity.Entities.Entity car, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectGeometryData);
```

- `public static GetParkingSize(Unity.Entities.Entity car, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectGeometryData, System.Single& offset) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 GetParkingSize(Unity.Entities.Entity car, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& objectGeometryData, System.Single& offset);
```

- `public static GetParkingSize(Game.Prefabs.ObjectGeometryData objectGeometry, System.Single& offset) : Unity.Mathematics.float2`  

```csharp
public static Unity.Mathematics.float2 GetParkingSize(Game.Prefabs.ObjectGeometryData objectGeometry, System.Single& offset);
```

- `public static GetParkingSource(Unity.Entities.Entity entity, Game.Vehicles.CarCurrentLane currentLane, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity GetParkingSource(Unity.Entities.Entity entity, Game.Vehicles.CarCurrentLane currentLane, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData);
```

- `public static GetPathElement(System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathElement& pathElement) : System.Boolean`  

```csharp
public static System.Boolean GetPathElement(System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathElement& pathElement);
```

- `public static GetPathElement(System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathElement& pathElement) : System.Boolean`  

```csharp
public static System.Boolean GetPathElement(System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathElement& pathElement);
```

- `public static GetPathMethods(Game.Prefabs.CarLaneData carLaneData) : Game.Pathfind.PathMethod`  

```csharp
public static Game.Pathfind.PathMethod GetPathMethods(Game.Prefabs.CarLaneData carLaneData);
```

- `public static GetPathMethods(Game.Prefabs.CarData carData) : Game.Pathfind.PathMethod`  

```csharp
public static Game.Pathfind.PathMethod GetPathMethods(Game.Prefabs.CarData carData);
```

- `public static GetPathMethods(Game.Prefabs.WatercraftData watercraftData) : Game.Pathfind.PathMethod`  

```csharp
public static Game.Pathfind.PathMethod GetPathMethods(Game.Prefabs.WatercraftData watercraftData);
```

- `public static GetPathMethods(Game.Prefabs.AircraftData aircraftData) : Game.Pathfind.PathMethod`  

```csharp
public static Game.Pathfind.PathMethod GetPathMethods(Game.Prefabs.AircraftData aircraftData);
```

- `public static GetPreferredLaneFlags(Game.Vehicles.Car carData) : Game.Net.CarLaneFlags`  

```csharp
public static Game.Net.CarLaneFlags GetPreferredLaneFlags(Game.Vehicles.Car carData);
```

- `public static GetPriority(Game.Vehicles.Car carData) : System.Int32`  

```csharp
public static System.Int32 GetPriority(Game.Vehicles.Car carData);
```

- `public static GetPriority(Game.Prefabs.TrainData trainData) : System.Int32`  

```csharp
public static System.Int32 GetPriority(Game.Prefabs.TrainData trainData);
```

- `public static GetPriority(Game.Prefabs.WatercraftData prefabWatercraftData) : System.Int32`  

```csharp
public static System.Int32 GetPriority(Game.Prefabs.WatercraftData prefabWatercraftData);
```

- `public static GetPriority(Game.Prefabs.AircraftData prefabAircraftData) : System.Int32`  

```csharp
public static System.Int32 GetPriority(Game.Prefabs.AircraftData prefabAircraftData);
```

- `public static GetSignalDistance(Game.Prefabs.TrainData prefabTrainData, System.Single speed) : System.Single`  

```csharp
public static System.Single GetSignalDistance(Game.Prefabs.TrainData prefabTrainData, System.Single speed);
```

- `public static GetSpeedLimitFactor(Game.Vehicles.Car carData) : System.Single`  

```csharp
public static System.Single GetSpeedLimitFactor(Game.Vehicles.Car carData);
```

- `public static IsCarLane(Unity.Entities.Entity lane, Unity.Entities.ComponentLookup`1[[Game.Net.CarLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& carLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Objects.SpawnLocation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnLocationData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnLocationData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabSpawnLocationData) : System.Boolean`  

```csharp
public static System.Boolean IsCarLane(Unity.Entities.Entity lane, Unity.Entities.ComponentLookup`1[[Game.Net.CarLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& carLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Objects.SpawnLocation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnLocationData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnLocationData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabSpawnLocationData);
```

- `public static IsParkingLane(Unity.Entities.Entity lane, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData) : System.Boolean`  

```csharp
public static System.Boolean IsParkingLane(Unity.Entities.Entity lane, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData);
```

- `public static IsReversedPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.ComponentLookup<Game.Vehicles.TrainCurrentLane> currentLaneData, Unity.Entities.ComponentLookup<Game.Vehicles.Train> trainData, Unity.Entities.ComponentLookup<Game.Objects.Transform> transformData) : System.Boolean`  

```csharp
public static System.Boolean IsReversedPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.ComponentLookup<Game.Vehicles.TrainCurrentLane> currentLaneData, Unity.Entities.ComponentLookup<Game.Vehicles.Train> trainData, Unity.Entities.ComponentLookup<Game.Objects.Transform> transformData);
```

- `public static IsStuck(Game.Pathfind.PathOwner pathOwner) : System.Boolean`  

```csharp
public static System.Boolean IsStuck(Game.Pathfind.PathOwner pathOwner);
```

- `public static ModifyDriveSpeed(System.Single& driveSpeed, Game.Net.LaneCondition condition) : System.Void`  

```csharp
public static System.Void ModifyDriveSpeed(System.Single& driveSpeed, Game.Net.LaneCondition condition);
```

- `private static MoveBufferPosition(Unity.Mathematics.float3 comparePosition, Game.Vehicles.TrainBogiePosition& targetPosition, System.Single minDistance, Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float2& curveDelta) : System.Boolean`  

```csharp
private static System.Boolean MoveBufferPosition(Unity.Mathematics.float3 comparePosition, Game.Vehicles.TrainBogiePosition& targetPosition, System.Single minDistance, Colossal.Mathematics.Bezier4x3 curve, Unity.Mathematics.float2& curveDelta);
```

- `public static ParkingSpaceReached(Game.Vehicles.CarCurrentLane currentLane, Game.Pathfind.PathOwner pathOwner) : System.Boolean`  

```csharp
public static System.Boolean ParkingSpaceReached(Game.Vehicles.CarCurrentLane currentLane, Game.Pathfind.PathOwner pathOwner);
```

- `public static ParkingSpaceReached(Game.Vehicles.AircraftCurrentLane currentLane, Game.Pathfind.PathOwner pathOwner) : System.Boolean`  

```csharp
public static System.Boolean ParkingSpaceReached(Game.Vehicles.AircraftCurrentLane currentLane, Game.Pathfind.PathOwner pathOwner);
```

- `public static PathEndReached(Game.Vehicles.CarCurrentLane currentLane) : System.Boolean`  

```csharp
public static System.Boolean PathEndReached(Game.Vehicles.CarCurrentLane currentLane);
```

- `public static PathEndReached(Game.Vehicles.TrainCurrentLane currentLane) : System.Boolean`  

```csharp
public static System.Boolean PathEndReached(Game.Vehicles.TrainCurrentLane currentLane);
```

- `public static PathEndReached(Game.Vehicles.WatercraftCurrentLane currentLane) : System.Boolean`  

```csharp
public static System.Boolean PathEndReached(Game.Vehicles.WatercraftCurrentLane currentLane);
```

- `public static PathEndReached(Game.Vehicles.AircraftCurrentLane currentLane) : System.Boolean`  

```csharp
public static System.Boolean PathEndReached(Game.Vehicles.AircraftCurrentLane currentLane);
```

- `public static PathfindFailed(Game.Pathfind.PathOwner pathOwner) : System.Boolean`  

```csharp
public static System.Boolean PathfindFailed(Game.Pathfind.PathOwner pathOwner);
```

- `public static QueueReached(Game.Vehicles.CarCurrentLane currentLane) : System.Boolean`  

```csharp
public static System.Boolean QueueReached(Game.Vehicles.CarCurrentLane currentLane);
```

- `public static RequireNewPath(Game.Pathfind.PathOwner pathOwner) : System.Boolean`  

```csharp
public static System.Boolean RequireNewPath(Game.Pathfind.PathOwner pathOwner);
```

- `public static ResetParkingLaneStatus(Unity.Entities.Entity entity, Game.Vehicles.CarCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.EntityStorageInfoLookup& entityLookup, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.CarLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& carLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Objects.SpawnLocation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnLocationData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnLocationData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabSpawnLocationData) : System.Void`  

```csharp
public static System.Void ResetParkingLaneStatus(Unity.Entities.Entity entity, Game.Vehicles.CarCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.EntityStorageInfoLookup& entityLookup, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.CarLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& carLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Objects.SpawnLocation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnLocationData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.SpawnLocationData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabSpawnLocationData);
```

- `public static ResetUpdatedPath(Game.Pathfind.PathOwner& pathOwner) : System.Boolean`  

```csharp
public static System.Boolean ResetUpdatedPath(Game.Pathfind.PathOwner& pathOwner);
```

- `public static ReturnEndReached(Game.Vehicles.TrainCurrentLane currentLane) : System.Boolean`  

```csharp
public static System.Boolean ReturnEndReached(Game.Vehicles.TrainCurrentLane currentLane);
```

- `public static ReverseCarriage(Unity.Entities.Entity vehicle, Unity.Entities.Entity lastLane, System.Single lastCurvePos, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Train, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trainData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainCurrentLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentLaneData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainNavigation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& navigationData, Game.Vehicles.TrainBogieCache& rearCache) : System.Void`  

```csharp
public static System.Void ReverseCarriage(Unity.Entities.Entity vehicle, Unity.Entities.Entity lastLane, System.Single lastCurvePos, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Train, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trainData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainCurrentLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentLaneData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainNavigation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& navigationData, Game.Vehicles.TrainBogieCache& rearCache);
```

- `public static ReverseTrain(Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Train, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trainData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainCurrentLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentLaneData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainNavigation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& navigationData) : System.Void`  

```csharp
public static System.Void ReverseTrain(Unity.Entities.Entity vehicle, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Train, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trainData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainCurrentLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentLaneData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainNavigation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& navigationData);
```

- `public static SetAreaTarget(Unity.Mathematics.float3 prev2, Unity.Mathematics.float3 prev, Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Entities.Entity areaEntity, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Mathematics.float3 comparePosition, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isBackward, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves, Unity.Entities.ComponentLookup<Game.Common.Owner> owners) : System.Boolean`  

```csharp
public static System.Boolean SetAreaTarget(Unity.Mathematics.float3 prev2, Unity.Mathematics.float3 prev, Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Entities.Entity areaEntity, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Mathematics.float3 comparePosition, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isBackward, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves, Unity.Entities.ComponentLookup<Game.Common.Owner> owners);
```

- `public static SetAreaTarget(Unity.Mathematics.float3 prev2, Unity.Mathematics.float3 prev, Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Entities.Entity areaEntity, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Mathematics.float3 comparePosition, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isBackward, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves, Unity.Entities.ComponentLookup<Game.Common.Owner> owners) : System.Boolean`  

```csharp
public static System.Boolean SetAreaTarget(Unity.Mathematics.float3 prev2, Unity.Mathematics.float3 prev, Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Entities.Entity areaEntity, Unity.Entities.DynamicBuffer<Game.Areas.Node> nodes, Unity.Mathematics.float3 comparePosition, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isBackward, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves, Unity.Entities.ComponentLookup<Game.Common.Owner> owners);
```

- `public static SetParkingCurvePos(Unity.Entities.Entity entity, Unity.Mathematics.Random& random, Game.Vehicles.CarCurrentLane currentLane, Game.Pathfind.PathOwner pathOwner, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Vehicles.ParkedCar, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarData, Unity.Entities.ComponentLookup`1[[Game.Objects.Unspawned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unspawnedData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabObjectGeometryData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ParkingLaneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabParkingLaneData, Unity.Entities.BufferLookup`1[[Game.Net.LaneObject, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneObjectData, Unity.Entities.BufferLookup`1[[Game.Net.LaneOverlap, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneOverlapData, System.Boolean ignoreDriveways) : System.Int32`  

```csharp
public static System.Int32 SetParkingCurvePos(Unity.Entities.Entity entity, Unity.Mathematics.Random& random, Game.Vehicles.CarCurrentLane currentLane, Game.Pathfind.PathOwner pathOwner, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Vehicles.ParkedCar, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarData, Unity.Entities.ComponentLookup`1[[Game.Objects.Unspawned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unspawnedData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabObjectGeometryData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ParkingLaneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabParkingLaneData, Unity.Entities.BufferLookup`1[[Game.Net.LaneObject, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneObjectData, Unity.Entities.BufferLookup`1[[Game.Net.LaneOverlap, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneOverlapData, System.Boolean ignoreDriveways);
```

- `public static SetParkingCurvePos(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, System.Int32 index, Unity.Entities.Entity currentLane, System.Single curvePos, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData) : System.Void`  

```csharp
public static System.Void SetParkingCurvePos(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, System.Int32 index, Unity.Entities.Entity currentLane, System.Single curvePos, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData);
```

- `public static SetParkingCurvePos(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, Game.Vehicles.CarCurrentLane& currentLaneData, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navLanes, System.Int32 navIndex, System.Single curvePos, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData) : System.Void`  

```csharp
public static System.Void SetParkingCurvePos(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, Game.Vehicles.CarCurrentLane& currentLaneData, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navLanes, System.Int32 navIndex, System.Single curvePos, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData);
```

- `public static SetTarget(Game.Pathfind.PathOwner& pathOwner, Game.Common.Target& targetData, Unity.Entities.Entity newTarget) : System.Void`  

```csharp
public static System.Void SetTarget(Game.Pathfind.PathOwner& pathOwner, Game.Common.Target& targetData, Unity.Entities.Entity newTarget);
```

- `public static SetTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 comparePosition, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves) : System.Boolean`  

```csharp
public static System.Boolean SetTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 comparePosition, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves);
```

- `public static SetTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 comparePosition, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves) : System.Boolean`  

```csharp
public static System.Boolean SetTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 comparePosition, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Collections.NativeArray<Game.Pathfind.PathElement> pathElements, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single lanePosition, System.Single curveDelta, System.Single navigationSize, System.Boolean isSingle, Unity.Entities.ComponentLookup<Game.Objects.Transform> transforms, Unity.Entities.ComponentLookup<Game.Net.AreaLane> areaLanes, Unity.Entities.ComponentLookup<Game.Net.Curve> curves);
```

- `public static SetTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 comparePosition, Unity.Mathematics.float3 lastTarget, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single navigationSize, System.Boolean isSingle) : System.Boolean`  

```csharp
public static System.Boolean SetTriangleTarget(Unity.Mathematics.float3 left, Unity.Mathematics.float3 right, Unity.Mathematics.float3 next, Unity.Mathematics.float3 comparePosition, Unity.Mathematics.float3 lastTarget, Unity.Mathematics.float3& targetPosition, System.Single minDistance, System.Single navigationSize, System.Boolean isSingle);
```

- `public static SetupPathfind(Game.Vehicles.CarCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> queue, Game.Pathfind.SetupQueueItem item) : System.Void`  

```csharp
public static System.Void SetupPathfind(Game.Vehicles.CarCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> queue, Game.Pathfind.SetupQueueItem item);
```

- `public static SetupPathfind(Game.Vehicles.TrainCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> queue, Game.Pathfind.SetupQueueItem item) : System.Void`  

```csharp
public static System.Void SetupPathfind(Game.Vehicles.TrainCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> queue, Game.Pathfind.SetupQueueItem item);
```

- `public static SetupPathfind(Game.Vehicles.WatercraftCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> queue, Game.Pathfind.SetupQueueItem item) : System.Void`  

```csharp
public static System.Void SetupPathfind(Game.Vehicles.WatercraftCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> queue, Game.Pathfind.SetupQueueItem item);
```

- `public static SetupPathfind(Game.Vehicles.AircraftCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> queue, Game.Pathfind.SetupQueueItem item) : System.Void`  

```csharp
public static System.Void SetupPathfind(Game.Vehicles.AircraftCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Collections.NativeQueue<Game.Pathfind.SetupQueueItem> queue, Game.Pathfind.SetupQueueItem item);
```

- `public static UpdateCarriageLocations(Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout, Unity.Collections.NativeList<Game.Pathfind.PathElement> laneBuffer, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Train, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trainData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.ParkedTrain, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedTrainData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainCurrentLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentLaneData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainNavigation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& navigationData, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transformData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.TrainData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabTrainData) : System.Void`  

```csharp
public static System.Void UpdateCarriageLocations(Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout, Unity.Collections.NativeList<Game.Pathfind.PathElement> laneBuffer, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Train, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& trainData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.ParkedTrain, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedTrainData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainCurrentLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentLaneData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.TrainNavigation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& navigationData, Unity.Entities.ComponentLookup`1[[Game.Objects.Transform, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& transformData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.TrainData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabTrainData);
```

- `public static ValidateParkingSpace(Unity.Entities.Entity entity, Unity.Mathematics.Random& random, Game.Vehicles.CarCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Vehicles.ParkedCar, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Blocker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& blockerData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Objects.Unspawned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unspawnedData, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.GarageLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& garageLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ParkingLaneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabParkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabObjectGeometryData, Unity.Entities.BufferLookup`1[[Game.Net.LaneObject, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneObjectData, Unity.Entities.BufferLookup`1[[Game.Net.LaneOverlap, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneOverlapData, System.Boolean ignoreDriveways, System.Boolean ignoreDisabled, System.Boolean boardingOnly) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity ValidateParkingSpace(Unity.Entities.Entity entity, Unity.Mathematics.Random& random, Game.Vehicles.CarCurrentLane& currentLane, Game.Pathfind.PathOwner& pathOwner, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup`1[[Game.Vehicles.ParkedCar, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkedCarData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Blocker, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& blockerData, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Objects.Unspawned, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& unspawnedData, Unity.Entities.ComponentLookup`1[[Game.Net.ParkingLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& parkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.GarageLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& garageLaneData, Unity.Entities.ComponentLookup`1[[Game.Net.ConnectionLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectionLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ParkingLaneData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabParkingLaneData, Unity.Entities.ComponentLookup`1[[Game.Prefabs.ObjectGeometryData, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabObjectGeometryData, Unity.Entities.BufferLookup`1[[Game.Net.LaneObject, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneObjectData, Unity.Entities.BufferLookup`1[[Game.Net.LaneOverlap, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneOverlapData, System.Boolean ignoreDriveways, System.Boolean ignoreDisabled, System.Boolean boardingOnly);
```

- `public static WaypointReached(Game.Vehicles.CarCurrentLane currentLane) : System.Boolean`  

```csharp
public static System.Boolean WaypointReached(Game.Vehicles.CarCurrentLane currentLane);
```


