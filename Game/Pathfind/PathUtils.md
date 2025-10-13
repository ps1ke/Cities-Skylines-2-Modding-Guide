# Game.Pathfind.PathUtils

**Assembly:** `Game`  
**Namespace:** `Game.Pathfind`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class PathUtils
{
    public static const System.Single MIN_DENSITY;

    public static System.Single CalculateCost(Unity.Mathematics.Random& random, Game.Pathfind.PathSpecification& pathSpecification, Game.Pathfind.PathfindParameters& pathfindParameters);
    public static System.Single CalculateCost(Game.Pathfind.PathSpecification& pathSpecification, Game.Pathfind.CoverageParameters& coverageParameters, Unity.Mathematics.float2 delta);
    public static System.Single CalculateCost(Game.Pathfind.PathSpecification& pathSpecification, Game.Pathfind.AvailabilityParameters& availabilityParameters, Unity.Mathematics.float2 delta);
    public static System.Single CalculateLength(Game.Pathfind.PathSpecification& pathSpecification, Unity.Mathematics.float2 delta);
    public static System.Single CalculateSpeed(Game.Pathfind.PathSpecification& pathSpecification, Game.Pathfind.PathfindParameters& pathfindParameters);
    public static System.Void CombinePaths(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> sourceElements1, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> sourceElements2, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> targetElements);
    public static Game.Pathfind.PathInformation CombinePaths(Game.Pathfind.PathInformation pathInformation1, Game.Pathfind.PathInformation pathInformation2);
    public static System.Void CopyPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> sourceElements, Game.Pathfind.PathOwner sourceOwner, System.Int32 skipCount, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> targetElements);
    public static System.Void CopyPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> sourceElements, Game.Pathfind.PathOwner sourceOwner, System.Int32 skipCount, System.Int32 endIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> targetElements);
    public static System.Void ExtendPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, System.Single& distance, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdges, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes);
    public static System.Void ExtendReverseLocations(Game.Pathfind.PathElement prevElement, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, System.Single distance, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.EdgeLane> edgeLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.ComponentLookup<Game.Net.Edge> edgeData, Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> connectedEdges, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes);
    public static System.Int32 FindFirstLane(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathOwner pathOwner, System.Int32 skipCount, Unity.Entities.ComponentLookup<Game.Net.ParkingLane> parkingLaneData);
    public static Game.Pathfind.PathSpecification GetCarDriveSpecification(Game.Net.Curve curve, Game.Net.CarLane carLane, Game.Prefabs.CarLaneData carLaneData, Game.Prefabs.PathfindCarData carPathfindData, System.Single density);
    public static Game.Pathfind.PathSpecification GetCarDriveSpecification(Game.Net.Curve curve, Game.Net.CarLane carLane, Game.Net.TrackLane trackLaneData, Game.Prefabs.CarLaneData carLaneData, Game.Prefabs.PathfindCarData carPathfindData, System.Single density);
    public static System.Boolean GetEndDirection(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, System.Int32& endOffset, System.Boolean& forward);
    public static Game.Pathfind.LocationSpecification GetLocationSpecification(Game.Net.Curve curveData);
    public static Game.Pathfind.LocationSpecification GetLocationSpecification(Game.Net.Curve curveData, Game.Net.ParkingLane parkingLaneData);
    public static Game.Pathfind.LocationSpecification GetLocationSpecification(Unity.Mathematics.float3 position);
    public static Game.Pathfind.LocationSpecification GetLocationSpecification(Unity.Mathematics.float3 position1, Unity.Mathematics.float3 position2);
    public static Unity.Entities.Entity GetMasterLane(Unity.Entities.Entity lane, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes);
    public static Game.Pathfind.PathSpecification GetParkingSpaceSpecification(Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData parkingLaneData, Game.Prefabs.PathfindCarData carPathfindData);
    public static Game.Pathfind.PathSpecification GetSecondarySpecification(Game.Net.Curve curveData, Game.Net.ConnectionLane connectionLaneData, Game.Net.OutsideConnection outsideConnection, Game.Prefabs.PathfindConnectionData connectionPathfindData);
    public static Game.Pathfind.PathSpecification GetSpawnLocationSpecification(Game.Prefabs.PathfindPedestrianData pedestrianPathfindData, System.Single distance, Unity.Entities.Entity accessRestriction, System.Boolean requireAuthorization, System.Boolean allowEnter, System.Boolean allowExit);
    public static Game.Pathfind.PathSpecification GetSpawnLocationSpecification(Game.Prefabs.RouteConnectionType connectionType, Game.Prefabs.PathfindCarData carPathfindData, Game.Net.CarLane carLane, System.Single distance, System.Int32 laneCrossCount, Unity.Entities.Entity accessRestriction, System.Boolean requireAuthorization, System.Boolean allowEnter, System.Boolean allowExit);
    public static Game.Pathfind.PathSpecification GetSpawnLocationSpecification(Game.Prefabs.PathfindTrackData trackPathfindData, Unity.Entities.Entity accessRestriction);
    public static Game.Pathfind.PathSpecification GetSpawnLocationSpecification(Game.Prefabs.RouteConnectionType connectionType, Game.Prefabs.PathfindConnectionData connectionPathfindData, Game.Net.RoadTypes roadType, System.Single distance, Unity.Entities.Entity accessRestriction, System.Boolean requireAuthorization, System.Boolean allowEnter, System.Boolean allowExit);
    public static Game.Pathfind.PathSpecification GetSpecification(Game.Net.Curve curveData, Game.Net.PedestrianLane pedestrianLaneData, Game.Prefabs.PathfindPedestrianData pedestrianPathfindData);
    public static Game.Pathfind.PathSpecification GetSpecification(Game.Net.Curve curveData, Game.Net.ConnectionLane connectionLaneData, Game.Net.GarageLane garageLane, Game.Net.OutsideConnection outsideConnection, Game.Prefabs.PathfindConnectionData connectionPathfindData);
    public static System.Boolean GetStartDirection(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, System.Int32& startOffset, System.Boolean& forward);
    public static Game.Pathfind.PathSpecification GetTaxiAccessSpecification(Game.Net.ParkingLane parkingLaneData, Game.Prefabs.PathfindCarData carPathfindData, Game.Prefabs.PathfindTransportData transportPathfindData);
    public static System.Single GetTaxiAvailabilityDelay(Game.Net.ParkingLane parkingLaneData);
    public static Game.Pathfind.PathSpecification GetTaxiDriveSpecification(Game.Net.Curve curveData, Game.Net.CarLane carLaneData, Game.Prefabs.PathfindCarData carPathfindData, Game.Prefabs.PathfindTransportData transportPathfindData, System.Single density);
    public static Game.Pathfind.PathSpecification GetTaxiStopSpecification(Game.Routes.TransportStop transportStop, Game.Routes.TaxiStand taxiStand, Game.Routes.WaitingPassengers waitingPassengers, Game.Prefabs.PathfindTransportData transportPathfindData);
    public static Game.Pathfind.PathSpecification GetTrackDriveSpecification(Game.Net.Curve curveData, Game.Net.TrackLane trackLaneData, Game.Prefabs.PathfindTrackData trackPathfindData);
    public static Game.Pathfind.PathSpecification GetTransportLineSpecification(Game.Prefabs.TransportLineData transportLineData, Game.Prefabs.PathfindTransportData transportPathfindData, Game.Routes.RouteInfo routeInfo);
    public static Game.Pathfind.PathSpecification GetTransportStopSpecification(Game.Routes.TransportStop transportStop, Game.Routes.TransportLine transportLine, Game.Routes.WaitingPassengers waitingPassengers, Game.Prefabs.TransportLineData transportLineData, Game.Prefabs.PathfindTransportData transportPathfindData, System.Boolean isWaypoint);
    public static System.Void InitializeSpawnPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Collections.NativeList<Game.Pathfind.PathElement> laneBuffer, Unity.Entities.Entity parkingLocation, Game.Pathfind.PathOwner& pathOwner, System.Single length, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.ComponentLookup`1[[Game.Objects.SpawnLocation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnLocationData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdges, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes);
    public static System.Boolean IsPathfindingPurpose(Game.Citizens.Purpose purpose);
    public static System.Void ResetPath(Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes);
    public static System.Void ResetPath(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes);
    public static System.Void ResetPath(Game.Vehicles.AircraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path);
    public static System.Void TrimPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathOwner& pathOwner);
    public static System.Void TrimPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathOwner& pathOwner, System.Int32 startIndex);
    public static System.Void TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add);
    public static System.Void TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add, System.Single distance);
    public static System.Void TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add, Colossal.Mathematics.Bezier4x3 curve);
    public static System.Void TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add, System.Boolean doIt);
    public static System.Void TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add, System.Single distance, System.Boolean doIt);
    public static System.Boolean TryAppendPath(Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes);
    public static System.Boolean TryAppendPath(Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, System.Int32& appendedCount);
    public static System.Boolean TryAppendPath(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes);
    public static System.Boolean TryAppendPath(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, System.Int32& appendedCount);
    public static System.Boolean TryAppendPath(Game.Vehicles.AircraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.AircraftNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath);
    public static System.Boolean TryAppendPath(Game.Vehicles.TrainCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.TrainNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath);
    public static System.Void UpdateOwnedVehicleMethods(Unity.Entities.Entity householdEntity, Unity.Entities.BufferLookup`1[[Game.Vehicles.OwnedVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownedVehicleBuffs, Game.Pathfind.PathfindParameters& parameters, Game.Pathfind.SetupQueueTarget& origin, Game.Pathfind.SetupQueueTarget& destination);
}
```


## Fields

- `public static const System.Single MIN_DENSITY`  

```csharp
public static const System.Single MIN_DENSITY;
```


## Methods

- `public static CalculateCost(Unity.Mathematics.Random& random, Game.Pathfind.PathSpecification& pathSpecification, Game.Pathfind.PathfindParameters& pathfindParameters) : System.Single`  

```csharp
public static System.Single CalculateCost(Unity.Mathematics.Random& random, Game.Pathfind.PathSpecification& pathSpecification, Game.Pathfind.PathfindParameters& pathfindParameters);
```

- `public static CalculateCost(Game.Pathfind.PathSpecification& pathSpecification, Game.Pathfind.CoverageParameters& coverageParameters, Unity.Mathematics.float2 delta) : System.Single`  

```csharp
public static System.Single CalculateCost(Game.Pathfind.PathSpecification& pathSpecification, Game.Pathfind.CoverageParameters& coverageParameters, Unity.Mathematics.float2 delta);
```

- `public static CalculateCost(Game.Pathfind.PathSpecification& pathSpecification, Game.Pathfind.AvailabilityParameters& availabilityParameters, Unity.Mathematics.float2 delta) : System.Single`  

```csharp
public static System.Single CalculateCost(Game.Pathfind.PathSpecification& pathSpecification, Game.Pathfind.AvailabilityParameters& availabilityParameters, Unity.Mathematics.float2 delta);
```

- `public static CalculateLength(Game.Pathfind.PathSpecification& pathSpecification, Unity.Mathematics.float2 delta) : System.Single`  

```csharp
public static System.Single CalculateLength(Game.Pathfind.PathSpecification& pathSpecification, Unity.Mathematics.float2 delta);
```

- `public static CalculateSpeed(Game.Pathfind.PathSpecification& pathSpecification, Game.Pathfind.PathfindParameters& pathfindParameters) : System.Single`  

```csharp
public static System.Single CalculateSpeed(Game.Pathfind.PathSpecification& pathSpecification, Game.Pathfind.PathfindParameters& pathfindParameters);
```

- `public static CombinePaths(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> sourceElements1, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> sourceElements2, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> targetElements) : System.Void`  

```csharp
public static System.Void CombinePaths(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> sourceElements1, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> sourceElements2, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> targetElements);
```

- `public static CombinePaths(Game.Pathfind.PathInformation pathInformation1, Game.Pathfind.PathInformation pathInformation2) : Game.Pathfind.PathInformation`  

```csharp
public static Game.Pathfind.PathInformation CombinePaths(Game.Pathfind.PathInformation pathInformation1, Game.Pathfind.PathInformation pathInformation2);
```

- `public static CopyPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> sourceElements, Game.Pathfind.PathOwner sourceOwner, System.Int32 skipCount, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> targetElements) : System.Void`  

```csharp
public static System.Void CopyPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> sourceElements, Game.Pathfind.PathOwner sourceOwner, System.Int32 skipCount, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> targetElements);
```

- `public static CopyPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> sourceElements, Game.Pathfind.PathOwner sourceOwner, System.Int32 skipCount, System.Int32 endIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> targetElements) : System.Void`  

```csharp
public static System.Void CopyPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> sourceElements, Game.Pathfind.PathOwner sourceOwner, System.Int32 skipCount, System.Int32 endIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> targetElements);
```

- `public static ExtendPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, System.Single& distance, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdges, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes) : System.Void`  

```csharp
public static System.Void ExtendPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, System.Single& distance, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdges, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes);
```

- `public static ExtendReverseLocations(Game.Pathfind.PathElement prevElement, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, System.Single distance, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.EdgeLane> edgeLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.ComponentLookup<Game.Net.Edge> edgeData, Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> connectedEdges, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes) : System.Void`  

```csharp
public static System.Void ExtendReverseLocations(Game.Pathfind.PathElement prevElement, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, System.Single distance, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.EdgeLane> edgeLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.ComponentLookup<Game.Net.Edge> edgeData, Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> connectedEdges, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes);
```

- `public static FindFirstLane(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathOwner pathOwner, System.Int32 skipCount, Unity.Entities.ComponentLookup<Game.Net.ParkingLane> parkingLaneData) : System.Int32`  

```csharp
public static System.Int32 FindFirstLane(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathOwner pathOwner, System.Int32 skipCount, Unity.Entities.ComponentLookup<Game.Net.ParkingLane> parkingLaneData);
```

- `public static GetCarDriveSpecification(Game.Net.Curve curve, Game.Net.CarLane carLane, Game.Prefabs.CarLaneData carLaneData, Game.Prefabs.PathfindCarData carPathfindData, System.Single density) : Game.Pathfind.PathSpecification`  

```csharp
public static Game.Pathfind.PathSpecification GetCarDriveSpecification(Game.Net.Curve curve, Game.Net.CarLane carLane, Game.Prefabs.CarLaneData carLaneData, Game.Prefabs.PathfindCarData carPathfindData, System.Single density);
```

- `public static GetCarDriveSpecification(Game.Net.Curve curve, Game.Net.CarLane carLane, Game.Net.TrackLane trackLaneData, Game.Prefabs.CarLaneData carLaneData, Game.Prefabs.PathfindCarData carPathfindData, System.Single density) : Game.Pathfind.PathSpecification`  

```csharp
public static Game.Pathfind.PathSpecification GetCarDriveSpecification(Game.Net.Curve curve, Game.Net.CarLane carLane, Game.Net.TrackLane trackLaneData, Game.Prefabs.CarLaneData carLaneData, Game.Prefabs.PathfindCarData carPathfindData, System.Single density);
```

- `public static GetEndDirection(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, System.Int32& endOffset, System.Boolean& forward) : System.Boolean`  

```csharp
public static System.Boolean GetEndDirection(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, System.Int32& endOffset, System.Boolean& forward);
```

- `public static GetLocationSpecification(Game.Net.Curve curveData) : Game.Pathfind.LocationSpecification`  

```csharp
public static Game.Pathfind.LocationSpecification GetLocationSpecification(Game.Net.Curve curveData);
```

- `public static GetLocationSpecification(Game.Net.Curve curveData, Game.Net.ParkingLane parkingLaneData) : Game.Pathfind.LocationSpecification`  

```csharp
public static Game.Pathfind.LocationSpecification GetLocationSpecification(Game.Net.Curve curveData, Game.Net.ParkingLane parkingLaneData);
```

- `public static GetLocationSpecification(Unity.Mathematics.float3 position) : Game.Pathfind.LocationSpecification`  

```csharp
public static Game.Pathfind.LocationSpecification GetLocationSpecification(Unity.Mathematics.float3 position);
```

- `public static GetLocationSpecification(Unity.Mathematics.float3 position1, Unity.Mathematics.float3 position2) : Game.Pathfind.LocationSpecification`  

```csharp
public static Game.Pathfind.LocationSpecification GetLocationSpecification(Unity.Mathematics.float3 position1, Unity.Mathematics.float3 position2);
```

- `public static GetMasterLane(Unity.Entities.Entity lane, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes) : Unity.Entities.Entity`  

```csharp
public static Unity.Entities.Entity GetMasterLane(Unity.Entities.Entity lane, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes);
```

- `public static GetParkingSpaceSpecification(Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData parkingLaneData, Game.Prefabs.PathfindCarData carPathfindData) : Game.Pathfind.PathSpecification`  

```csharp
public static Game.Pathfind.PathSpecification GetParkingSpaceSpecification(Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData parkingLaneData, Game.Prefabs.PathfindCarData carPathfindData);
```

- `public static GetSecondarySpecification(Game.Net.Curve curveData, Game.Net.ConnectionLane connectionLaneData, Game.Net.OutsideConnection outsideConnection, Game.Prefabs.PathfindConnectionData connectionPathfindData) : Game.Pathfind.PathSpecification`  

```csharp
public static Game.Pathfind.PathSpecification GetSecondarySpecification(Game.Net.Curve curveData, Game.Net.ConnectionLane connectionLaneData, Game.Net.OutsideConnection outsideConnection, Game.Prefabs.PathfindConnectionData connectionPathfindData);
```

- `public static GetSpawnLocationSpecification(Game.Prefabs.PathfindPedestrianData pedestrianPathfindData, System.Single distance, Unity.Entities.Entity accessRestriction, System.Boolean requireAuthorization, System.Boolean allowEnter, System.Boolean allowExit) : Game.Pathfind.PathSpecification`  

```csharp
public static Game.Pathfind.PathSpecification GetSpawnLocationSpecification(Game.Prefabs.PathfindPedestrianData pedestrianPathfindData, System.Single distance, Unity.Entities.Entity accessRestriction, System.Boolean requireAuthorization, System.Boolean allowEnter, System.Boolean allowExit);
```

- `public static GetSpawnLocationSpecification(Game.Prefabs.RouteConnectionType connectionType, Game.Prefabs.PathfindCarData carPathfindData, Game.Net.CarLane carLane, System.Single distance, System.Int32 laneCrossCount, Unity.Entities.Entity accessRestriction, System.Boolean requireAuthorization, System.Boolean allowEnter, System.Boolean allowExit) : Game.Pathfind.PathSpecification`  

```csharp
public static Game.Pathfind.PathSpecification GetSpawnLocationSpecification(Game.Prefabs.RouteConnectionType connectionType, Game.Prefabs.PathfindCarData carPathfindData, Game.Net.CarLane carLane, System.Single distance, System.Int32 laneCrossCount, Unity.Entities.Entity accessRestriction, System.Boolean requireAuthorization, System.Boolean allowEnter, System.Boolean allowExit);
```

- `public static GetSpawnLocationSpecification(Game.Prefabs.PathfindTrackData trackPathfindData, Unity.Entities.Entity accessRestriction) : Game.Pathfind.PathSpecification`  

```csharp
public static Game.Pathfind.PathSpecification GetSpawnLocationSpecification(Game.Prefabs.PathfindTrackData trackPathfindData, Unity.Entities.Entity accessRestriction);
```

- `public static GetSpawnLocationSpecification(Game.Prefabs.RouteConnectionType connectionType, Game.Prefabs.PathfindConnectionData connectionPathfindData, Game.Net.RoadTypes roadType, System.Single distance, Unity.Entities.Entity accessRestriction, System.Boolean requireAuthorization, System.Boolean allowEnter, System.Boolean allowExit) : Game.Pathfind.PathSpecification`  

```csharp
public static Game.Pathfind.PathSpecification GetSpawnLocationSpecification(Game.Prefabs.RouteConnectionType connectionType, Game.Prefabs.PathfindConnectionData connectionPathfindData, Game.Net.RoadTypes roadType, System.Single distance, Unity.Entities.Entity accessRestriction, System.Boolean requireAuthorization, System.Boolean allowEnter, System.Boolean allowExit);
```

- `public static GetSpecification(Game.Net.Curve curveData, Game.Net.PedestrianLane pedestrianLaneData, Game.Prefabs.PathfindPedestrianData pedestrianPathfindData) : Game.Pathfind.PathSpecification`  

```csharp
public static Game.Pathfind.PathSpecification GetSpecification(Game.Net.Curve curveData, Game.Net.PedestrianLane pedestrianLaneData, Game.Prefabs.PathfindPedestrianData pedestrianPathfindData);
```

- `public static GetSpecification(Game.Net.Curve curveData, Game.Net.ConnectionLane connectionLaneData, Game.Net.GarageLane garageLane, Game.Net.OutsideConnection outsideConnection, Game.Prefabs.PathfindConnectionData connectionPathfindData) : Game.Pathfind.PathSpecification`  

```csharp
public static Game.Pathfind.PathSpecification GetSpecification(Game.Net.Curve curveData, Game.Net.ConnectionLane connectionLaneData, Game.Net.GarageLane garageLane, Game.Net.OutsideConnection outsideConnection, Game.Prefabs.PathfindConnectionData connectionPathfindData);
```

- `public static GetStartDirection(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, System.Int32& startOffset, System.Boolean& forward) : System.Boolean`  

```csharp
public static System.Boolean GetStartDirection(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, System.Int32& startOffset, System.Boolean& forward);
```

- `public static GetTaxiAccessSpecification(Game.Net.ParkingLane parkingLaneData, Game.Prefabs.PathfindCarData carPathfindData, Game.Prefabs.PathfindTransportData transportPathfindData) : Game.Pathfind.PathSpecification`  

```csharp
public static Game.Pathfind.PathSpecification GetTaxiAccessSpecification(Game.Net.ParkingLane parkingLaneData, Game.Prefabs.PathfindCarData carPathfindData, Game.Prefabs.PathfindTransportData transportPathfindData);
```

- `public static GetTaxiAvailabilityDelay(Game.Net.ParkingLane parkingLaneData) : System.Single`  

```csharp
public static System.Single GetTaxiAvailabilityDelay(Game.Net.ParkingLane parkingLaneData);
```

- `public static GetTaxiDriveSpecification(Game.Net.Curve curveData, Game.Net.CarLane carLaneData, Game.Prefabs.PathfindCarData carPathfindData, Game.Prefabs.PathfindTransportData transportPathfindData, System.Single density) : Game.Pathfind.PathSpecification`  

```csharp
public static Game.Pathfind.PathSpecification GetTaxiDriveSpecification(Game.Net.Curve curveData, Game.Net.CarLane carLaneData, Game.Prefabs.PathfindCarData carPathfindData, Game.Prefabs.PathfindTransportData transportPathfindData, System.Single density);
```

- `public static GetTaxiStopSpecification(Game.Routes.TransportStop transportStop, Game.Routes.TaxiStand taxiStand, Game.Routes.WaitingPassengers waitingPassengers, Game.Prefabs.PathfindTransportData transportPathfindData) : Game.Pathfind.PathSpecification`  

```csharp
public static Game.Pathfind.PathSpecification GetTaxiStopSpecification(Game.Routes.TransportStop transportStop, Game.Routes.TaxiStand taxiStand, Game.Routes.WaitingPassengers waitingPassengers, Game.Prefabs.PathfindTransportData transportPathfindData);
```

- `public static GetTrackDriveSpecification(Game.Net.Curve curveData, Game.Net.TrackLane trackLaneData, Game.Prefabs.PathfindTrackData trackPathfindData) : Game.Pathfind.PathSpecification`  

```csharp
public static Game.Pathfind.PathSpecification GetTrackDriveSpecification(Game.Net.Curve curveData, Game.Net.TrackLane trackLaneData, Game.Prefabs.PathfindTrackData trackPathfindData);
```

- `public static GetTransportLineSpecification(Game.Prefabs.TransportLineData transportLineData, Game.Prefabs.PathfindTransportData transportPathfindData, Game.Routes.RouteInfo routeInfo) : Game.Pathfind.PathSpecification`  

```csharp
public static Game.Pathfind.PathSpecification GetTransportLineSpecification(Game.Prefabs.TransportLineData transportLineData, Game.Prefabs.PathfindTransportData transportPathfindData, Game.Routes.RouteInfo routeInfo);
```

- `public static GetTransportStopSpecification(Game.Routes.TransportStop transportStop, Game.Routes.TransportLine transportLine, Game.Routes.WaitingPassengers waitingPassengers, Game.Prefabs.TransportLineData transportLineData, Game.Prefabs.PathfindTransportData transportPathfindData, System.Boolean isWaypoint) : Game.Pathfind.PathSpecification`  

```csharp
public static Game.Pathfind.PathSpecification GetTransportStopSpecification(Game.Routes.TransportStop transportStop, Game.Routes.TransportLine transportLine, Game.Routes.WaitingPassengers waitingPassengers, Game.Prefabs.TransportLineData transportLineData, Game.Prefabs.PathfindTransportData transportPathfindData, System.Boolean isWaypoint);
```

- `public static InitializeSpawnPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Collections.NativeList<Game.Pathfind.PathElement> laneBuffer, Unity.Entities.Entity parkingLocation, Game.Pathfind.PathOwner& pathOwner, System.Single length, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.ComponentLookup`1[[Game.Objects.SpawnLocation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnLocationData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdges, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes) : System.Void`  

```csharp
public static System.Void InitializeSpawnPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Collections.NativeList<Game.Pathfind.PathElement> laneBuffer, Unity.Entities.Entity parkingLocation, Game.Pathfind.PathOwner& pathOwner, System.Single length, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.ComponentLookup`1[[Game.Objects.SpawnLocation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnLocationData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdges, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes);
```

- `public static IsPathfindingPurpose(Game.Citizens.Purpose purpose) : System.Boolean`  

```csharp
public static System.Boolean IsPathfindingPurpose(Game.Citizens.Purpose purpose);
```

- `public static ResetPath(Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes) : System.Void`  

```csharp
public static System.Void ResetPath(Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes);
```

- `public static ResetPath(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes) : System.Void`  

```csharp
public static System.Void ResetPath(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes);
```

- `public static ResetPath(Game.Vehicles.AircraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path) : System.Void`  

```csharp
public static System.Void ResetPath(Game.Vehicles.AircraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path);
```

- `public static TrimPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathOwner& pathOwner) : System.Void`  

```csharp
public static System.Void TrimPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathOwner& pathOwner);
```

- `public static TrimPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathOwner& pathOwner, System.Int32 startIndex) : System.Void`  

```csharp
public static System.Void TrimPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathOwner& pathOwner, System.Int32 startIndex);
```

- `public static TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add) : System.Void`  

```csharp
public static System.Void TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add);
```

- `public static TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add, System.Single distance) : System.Void`  

```csharp
public static System.Void TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add, System.Single distance);
```

- `public static TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add, Colossal.Mathematics.Bezier4x3 curve) : System.Void`  

```csharp
public static System.Void TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add, Colossal.Mathematics.Bezier4x3 curve);
```

- `public static TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add, System.Boolean doIt) : System.Void`  

```csharp
public static System.Void TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add, System.Boolean doIt);
```

- `public static TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add, System.Single distance, System.Boolean doIt) : System.Void`  

```csharp
public static System.Void TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add, System.Single distance, System.Boolean doIt);
```

- `public static TryAppendPath(Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes) : System.Boolean`  

```csharp
public static System.Boolean TryAppendPath(Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes);
```

- `public static TryAppendPath(Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, System.Int32& appendedCount) : System.Boolean`  

```csharp
public static System.Boolean TryAppendPath(Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, System.Int32& appendedCount);
```

- `public static TryAppendPath(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes) : System.Boolean`  

```csharp
public static System.Boolean TryAppendPath(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes);
```

- `public static TryAppendPath(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, System.Int32& appendedCount) : System.Boolean`  

```csharp
public static System.Boolean TryAppendPath(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, System.Int32& appendedCount);
```

- `public static TryAppendPath(Game.Vehicles.AircraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.AircraftNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath) : System.Boolean`  

```csharp
public static System.Boolean TryAppendPath(Game.Vehicles.AircraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.AircraftNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath);
```

- `public static TryAppendPath(Game.Vehicles.TrainCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.TrainNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath) : System.Boolean`  

```csharp
public static System.Boolean TryAppendPath(Game.Vehicles.TrainCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.TrainNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath);
```

- `public static UpdateOwnedVehicleMethods(Unity.Entities.Entity householdEntity, Unity.Entities.BufferLookup`1[[Game.Vehicles.OwnedVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownedVehicleBuffs, Game.Pathfind.PathfindParameters& parameters, Game.Pathfind.SetupQueueTarget& origin, Game.Pathfind.SetupQueueTarget& destination) : System.Void`  

```csharp
public static System.Void UpdateOwnedVehicleMethods(Unity.Entities.Entity householdEntity, Unity.Entities.BufferLookup`1[[Game.Vehicles.OwnedVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownedVehicleBuffs, Game.Pathfind.PathfindParameters& parameters, Game.Pathfind.SetupQueueTarget& origin, Game.Pathfind.SetupQueueTarget& destination);
```


## Nested types

- `Game.Pathfind.PathUtils+AppendPathValue`  

