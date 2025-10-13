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
public static float CalculateCost(in PathSpecification pathSpecification, in AvailabilityParameters availabilityParameters, float2 delta)
	{
		float num = math.lerp(1f, pathSpecification.m_Density, availabilityParameters.m_DensityWeight);
		return pathSpecification.m_Length * num * math.abs(delta.y - delta.x) * availabilityParameters.m_CostFactor / pathSpecification.m_MaxSpeed;
	}
```

- `public static CalculateCost(Game.Pathfind.PathSpecification& pathSpecification, Game.Pathfind.CoverageParameters& coverageParameters, Unity.Mathematics.float2 delta) : System.Single`  

```csharp
public static float CalculateCost(in PathSpecification pathSpecification, in AvailabilityParameters availabilityParameters, float2 delta)
	{
		float num = math.lerp(1f, pathSpecification.m_Density, availabilityParameters.m_DensityWeight);
		return pathSpecification.m_Length * num * math.abs(delta.y - delta.x) * availabilityParameters.m_CostFactor / pathSpecification.m_MaxSpeed;
	}
```

- `public static CalculateCost(Game.Pathfind.PathSpecification& pathSpecification, Game.Pathfind.AvailabilityParameters& availabilityParameters, Unity.Mathematics.float2 delta) : System.Single`  

```csharp
public static float CalculateCost(in PathSpecification pathSpecification, in AvailabilityParameters availabilityParameters, float2 delta)
	{
		float num = math.lerp(1f, pathSpecification.m_Density, availabilityParameters.m_DensityWeight);
		return pathSpecification.m_Length * num * math.abs(delta.y - delta.x) * availabilityParameters.m_CostFactor / pathSpecification.m_MaxSpeed;
	}
```

- `public static CalculateLength(Game.Pathfind.PathSpecification& pathSpecification, Unity.Mathematics.float2 delta) : System.Single`  

```csharp
public static float CalculateLength(in PathSpecification pathSpecification, float2 delta)
	{
		return pathSpecification.m_Length * math.abs(delta.y - delta.x);
	}
```

- `public static CalculateSpeed(Game.Pathfind.PathSpecification& pathSpecification, Game.Pathfind.PathfindParameters& pathfindParameters) : System.Single`  

```csharp
public static float CalculateSpeed(in PathSpecification pathSpecification, in PathfindParameters pathfindParameters)
	{
		PathMethod pathMethod = pathSpecification.m_Methods & pathfindParameters.m_Methods;
		float2 @float = math.select(pathfindParameters.m_MaxSpeed, pathfindParameters.m_WalkSpeed, (pathMethod & PathMethod.Pedestrian) != 0);
		bool test = (pathSpecification.m_Flags & EdgeFlags.Secondary) != 0;
		float trueValue = math.min(math.select(@float.x, @float.y, test), pathSpecification.m_MaxSpeed);
		trueValue = math.select(pathSpecification.m_MaxSpeed, trueValue, (pathMethod & (PathMethod.Pedestrian | PathMethod.Road | PathMethod.Track | PathMethod.Flying | PathMethod.MediumRoad)) != 0);
		return math.select(trueValue - (float)(int)pathSpecification.m_FlowOffset * 0.00390625f * trueValue, trueValue, (pathfindParameters.m_PathfindFlags & PathfindFlags.IgnoreFlow) != 0);
	}
```

- `public static CombinePaths(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> sourceElements1, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> sourceElements2, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> targetElements) : System.Void`  

```csharp
public static PathInformation CombinePaths(PathInformation pathInformation1, PathInformation pathInformation2)
	{
		pathInformation1.m_Distance += pathInformation2.m_Distance;
		pathInformation1.m_Duration += pathInformation2.m_Duration;
		pathInformation1.m_TotalCost += pathInformation2.m_TotalCost;
		pathInformation1.m_Destination = pathInformation2.m_Destination;
		return pathInformation1;
	}
```

- `public static CombinePaths(Game.Pathfind.PathInformation pathInformation1, Game.Pathfind.PathInformation pathInformation2) : Game.Pathfind.PathInformation`  

```csharp
public static PathInformation CombinePaths(PathInformation pathInformation1, PathInformation pathInformation2)
	{
		pathInformation1.m_Distance += pathInformation2.m_Distance;
		pathInformation1.m_Duration += pathInformation2.m_Duration;
		pathInformation1.m_TotalCost += pathInformation2.m_TotalCost;
		pathInformation1.m_Destination = pathInformation2.m_Destination;
		return pathInformation1;
	}
```

- `public static CopyPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> sourceElements, Game.Pathfind.PathOwner sourceOwner, System.Int32 skipCount, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> targetElements) : System.Void`  

```csharp
public static void CopyPath(DynamicBuffer<PathElement> sourceElements, PathOwner sourceOwner, int skipCount, int endIndex, DynamicBuffer<PathElement> targetElements)
	{
		endIndex = math.min(endIndex, sourceElements.Length);
		int num = sourceOwner.m_ElementIndex + skipCount;
		int num2 = endIndex - num;
		if (num2 > 0)
		{
			targetElements.ResizeUninitialized(num2);
			sourceElements.AsNativeArray().GetSubArray(num, num2).CopyTo(targetElements.AsNativeArray());
		}
		else
		{
			targetElements.Clear();
		}
	}
```

- `public static CopyPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> sourceElements, Game.Pathfind.PathOwner sourceOwner, System.Int32 skipCount, System.Int32 endIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> targetElements) : System.Void`  

```csharp
public static void CopyPath(DynamicBuffer<PathElement> sourceElements, PathOwner sourceOwner, int skipCount, int endIndex, DynamicBuffer<PathElement> targetElements)
	{
		endIndex = math.min(endIndex, sourceElements.Length);
		int num = sourceOwner.m_ElementIndex + skipCount;
		int num2 = endIndex - num;
		if (num2 > 0)
		{
			targetElements.ResizeUninitialized(num2);
			sourceElements.AsNativeArray().GetSubArray(num, num2).CopyTo(targetElements.AsNativeArray());
		}
		else
		{
			targetElements.Clear();
		}
	}
```

- `public static ExtendPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, System.Single& distance, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdges, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes) : System.Void`  

```csharp
public static void ExtendPath(DynamicBuffer<PathElement> path, PathOwner pathOwner, ref float distance, ref ComponentLookup<Curve> curveData, ref ComponentLookup<Lane> laneData, ref ComponentLookup<EdgeLane> edgeLaneData, ref ComponentLookup<Owner> ownerData, ref ComponentLookup<Game.Net.Edge> edgeData, ref BufferLookup<ConnectedEdge> connectedEdges, ref BufferLookup<Game.Net.SubLane> subLanes)
	{
		float num = distance;
		distance = 0f;
		if (!GetEndDirection(path, pathOwner, ref curveData, out var endOffset, out var forward))
		{
			return;
		}
		PathElement elem = path[path.Length - endOffset - 1];
		elem.m_TargetDelta = new float2(elem.m_TargetDelta.y, math.select(0f, 1f, forward));
		for (int i = 0; i < 10000; i++)
		{
			if (!curveData.HasComponent(elem.m_Target))
			{
				break;
			}
			if (elem.m_TargetDelta.x != elem.m_TargetDelta.y)
			{
				float num2 = curveData[elem.m_Target].m_Length * math.abs(elem.m_TargetDelta.y - elem.m_TargetDelta.x);
				if (num2 >= num)
				{
					float t = math.select(num / num2, 1f, num2 == 0f);
					elem.m_TargetDelta.y = math.lerp(elem.m_TargetDelta.x, elem.m_TargetDelta.y, t);
					path.Insert(path.Length - endOffset, elem);
					distance += num;
					break;
				}
				path.Insert(path.Length - endOffset, elem);
				distance += num2;
				num -= num2;
			}
			if (!NetUtils.FindConnectedLane(ref elem.m_Target, ref forward, ref laneData, ref edgeLaneData, ref ownerData, ref edgeData, ref connectedEdges, ref subLanes))
			{
				break;
			}
			elem.m_TargetDelta = math.select(new float2(1f, 0f), new float2(0f, 1f), forward);
			elem.m_Flags = ~(PathElementFlags.Secondary | PathElementFlags.PathStart | PathElementFlags.Action | PathElementFlags.Return | PathElementFlags.Reverse | PathElementFlags.WaitPosition | PathElementFlags.Leader | PathElementFlags.Hangaround);
		}
	}
```

- `public static ExtendReverseLocations(Game.Pathfind.PathElement prevElement, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, System.Single distance, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.EdgeLane> edgeLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.ComponentLookup<Game.Net.Edge> edgeData, Unity.Entities.BufferLookup<Game.Net.ConnectedEdge> connectedEdges, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes) : System.Void`  

```csharp
public static void ExtendReverseLocations(PathElement prevElement, DynamicBuffer<PathElement> path, PathOwner pathOwner, float distance, ComponentLookup<Curve> curveData, ComponentLookup<Lane> laneData, ComponentLookup<EdgeLane> edgeLaneData, ComponentLookup<Owner> ownerData, ComponentLookup<Game.Net.Edge> edgeData, BufferLookup<ConnectedEdge> connectedEdges, BufferLookup<Game.Net.SubLane> subLanes)
	{
		if (pathOwner.m_ElementIndex >= path.Length)
		{
			return;
		}
		int num = pathOwner.m_ElementIndex - 1;
		if (prevElement.m_Target == Entity.Null)
		{
			prevElement = path[++num];
		}
		Entity entity = Entity.Null;
		if ((prevElement.m_Flags & PathElementFlags.Return) == 0 && prevElement.m_TargetDelta.x != prevElement.m_TargetDelta.y && ownerData.HasComponent(prevElement.m_Target))
		{
			entity = ownerData[prevElement.m_Target].m_Owner;
		}
		while (++num < path.Length)
		{
			PathElement pathElement = path[num];
			if (pathElement.m_TargetDelta.x == pathElement.m_TargetDelta.y)
			{
				if ((pathElement.m_Flags & PathElementFlags.Return) != 0)
				{
					entity = Entity.Null;
				}
				continue;
			}
			Entity entity2 = Entity.Null;
			if (pathElement.m_TargetDelta.x != pathElement.m_TargetDelta.y && ownerData.HasComponent(pathElement.m_Target))
			{
				entity2 = ownerData[pathElement.m_Target].m_Owner;
			}
			if (entity2 != Entity.Null && entity2 == entity && curveData.HasComponent(prevElement.m_Target) && curveData.HasComponent(pathElement.m_Target))
			{
				Curve curve = curveData[prevElement.m_Target];
				Curve curve2 = curveData[pathElement.m_Target];
				float3 x = MathUtils.Tangent(curve.m_Bezier, prevElement.m_TargetDelta.y);
				float3 y = MathUtils.Tangent(curve2.m_Bezier, pathElement.m_TargetDelta.x);
				bool forward = prevElement.m_TargetDelta.y > prevElement.m_TargetDelta.x;
				bool flag = pathElement.m_TargetDelta.y > pathElement.m_TargetDelta.x;
				if (math.dot(x, y) * math.select(1f, -1f, forward != flag) < 0f)
				{
					float num2 = distance;
					prevElement.m_TargetDelta = new float2(prevElement.m_TargetDelta.y, math.select(0f, 1f, forward));
					for (int i = 0; i < 10000; i++)
					{
						if (prevElement.m_TargetDelta.x != prevElement.m_TargetDelta.y)
						{
							float num3 = curveData[prevElement.m_Target].m_Length * math.abs(prevElement.m_TargetDelta.y - prevElement.m_TargetDelta.x);
							if (num3 >= num2)
							{
								float t = math.select(num2 / num3, 1f, num3 == 0f);
								prevElement.m_TargetDelta.y = math.lerp(prevElement.m_TargetDelta.x, prevElement.m_TargetDelta.y, t);
								path.Insert(num++, prevElement);
								num2 = 0f;
								break;
							}
							path.Insert(num++, prevElement);
							num2 -= num3;
						}
						if (!NetUtils.FindConnectedLane(ref prevElement.m_Target, ref forward, ref laneData, ref edgeLaneData, ref ownerData, ref edgeData, ref connectedEdges, ref subLanes))
						{
							break;
						}
						prevElement.m_TargetDelta = math.select(new float2(1f, 0f), new float2(0f, 1f), forward);
						prevElement.m_Flags = PathElementFlags.Reverse;
					}
					if (num > 0)
					{
						prevElement = path[num - 1];
						prevElement.m_Flags |= PathElementFlags.Return;
						path[num - 1] = prevElement;
					}
					else
					{
						prevElement.m_TargetDelta.x = prevElement.m_TargetDelta.y;
						prevElement.m_Flags |= PathElementFlags.Return;
						path.Insert(num++, prevElement);
					}
					if (num2 > 0f)
					{
						while (num < path.Length)
						{
							pathElement = path[num];
							if (!curveData.HasComponent(pathElement.m_Target))
							{
								break;
							}
							float num4 = curveData[pathElement.m_Target].m_Length * math.abs(pathElement.m_TargetDelta.y - pathElement.m_TargetDelta.x);
							if (num4 >= num2)
							{
								float t2 = math.select(num2 / num4, 1f, num4 == 0f);
								pathElement.m_TargetDelta.x = math.lerp(pathElement.m_TargetDelta.x, pathElement.m_TargetDelta.y, t2);
								path[num] = pathElement;
								num2 = 0f;
								break;
							}
							path.RemoveAt(num);
							num2 -= num4;
						}
					}
				}
			}
			prevElement = pathElement;
			entity = (((pathElement.m_Flags & PathElementFlags.Return) == 0) ? entity2 : Entity.Null);
		}
	}
```

- `public static FindFirstLane(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathOwner pathOwner, System.Int32 skipCount, Unity.Entities.ComponentLookup<Game.Net.ParkingLane> parkingLaneData) : System.Int32`  

```csharp
public static int FindFirstLane(DynamicBuffer<PathElement> pathElements, PathOwner pathOwner, int skipCount, ComponentLookup<Game.Net.ParkingLane> parkingLaneData)
	{
		for (int i = pathOwner.m_ElementIndex + skipCount; i < pathElements.Length; i++)
		{
			if (parkingLaneData.HasComponent(pathElements[i].m_Target))
			{
				return i;
			}
		}
		return pathElements.Length;
	}
```

- `public static GetCarDriveSpecification(Game.Net.Curve curve, Game.Net.CarLane carLane, Game.Prefabs.CarLaneData carLaneData, Game.Prefabs.PathfindCarData carPathfindData, System.Single density) : Game.Pathfind.PathSpecification`  

```csharp
public static PathSpecification GetCarDriveSpecification(Curve curve, Game.Net.CarLane carLane, Game.Net.TrackLane trackLaneData, CarLaneData carLaneData, PathfindCarData carPathfindData, float density)
	{
		PathSpecification result = new PathSpecification
		{
			m_Flags = EdgeFlags.Forward,
			m_Methods = (VehicleUtils.GetPathMethods(carLaneData) | PathMethod.Track),
			m_Length = curve.m_Length,
			m_MaxSpeed = carLane.m_SpeedLimit,
			m_Density = math.sqrt(density),
			m_FlowOffset = carLane.m_FlowOffset,
			m_AccessRequirement = math.select(-1, carLane.m_AccessRestriction.Index, carLane.m_AccessRestriction != Entity.Null)
		};
		TryAddCosts(ref result.m_Costs, carPathfindData.m_DrivingCost, result.m_Length);
		TryAddCosts(ref result.m_Costs, carPathfindData.m_CurveAngleCost, curve.m_Bezier);
		TryAddCosts(ref result.m_Costs, carPathfindData.m_LaneCrossCost, (int)carLane.m_LaneCrossCount);
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.Approach) == 0)
		{
			bool flag = (carLane.m_Flags & Game.Net.CarLaneFlags.Forbidden) != 0;
			bool flag2 = (carLane.m_Flags & Game.Net.CarLaneFlags.Unsafe) != 0;
			bool flag3 = (carLane.m_Flags & Game.Net.CarLaneFlags.Highway) != 0;
			bool doIt = (carLane.m_Flags & (Game.Net.CarLaneFlags.TurnLeft | Game.Net.CarLaneFlags.TurnRight | Game.Net.CarLaneFlags.GentleTurnLeft | Game.Net.CarLaneFlags.GentleTurnRight)) != 0;
			bool flag4 = (carLane.m_Flags & (Game.Net.CarLaneFlags.UTurnLeft | Game.Net.CarLaneFlags.UTurnRight)) != 0;
			TryAddCosts(ref result.m_Costs, carPathfindData.m_ForbiddenCost, flag || (flag2 && flag3 && flag4));
			TryAddCosts(ref result.m_Costs, carPathfindData.m_TurningCost, doIt);
			if ((carLane.m_Flags & Game.Net.CarLaneFlags.Unsafe) != 0)
			{
				TryAddCosts(ref result.m_Costs, carPathfindData.m_UnsafeUTurnCost, flag4);
			}
			else
			{
				TryAddCosts(ref result.m_Costs, carPathfindData.m_UTurnCost, flag4);
			}
		}
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.Unsafe) == 0 || (trackLaneData.m_Flags & TrackLaneFlags.AllowMiddle) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowMiddle;
		}
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.Twoway) != 0 || (trackLaneData.m_Flags & TrackLaneFlags.Twoway) != 0)
		{
			result.m_Flags |= EdgeFlags.Backward;
		}
		if (carLane.m_BlockageEnd >= carLane.m_BlockageStart)
		{
			result.m_Rules |= RuleFlags.HasBlockage;
			result.m_BlockageStart = carLane.m_BlockageStart;
			result.m_BlockageEnd = carLane.m_BlockageEnd;
		}
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.ForbidCombustionEngines) != 0)
		{
			result.m_Rules |= RuleFlags.ForbidCombustionEngines;
		}
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.ForbidTransitTraffic) != 0)
		{
			result.m_Rules |= RuleFlags.ForbidTransitTraffic;
		}
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.ForbidHeavyTraffic) != 0)
		{
			result.m_Rules |= RuleFlags.ForbidHeavyTraffic;
		}
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.PublicOnly) != 0)
		{
			result.m_Rules |= RuleFlags.ForbidPrivateTraffic;
		}
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.Highway) != 0)
		{
			result.m_Rules |= RuleFlags.ForbidSlowTraffic;
		}
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.SideConnection) != 0)
		{
			result.m_Flags |= EdgeFlags.SingleOnly;
		}
		if (((uint)carLane.m_Flags & 0x80000000u) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowEnter;
		}
		return result;
	}
```

- `public static GetCarDriveSpecification(Game.Net.Curve curve, Game.Net.CarLane carLane, Game.Net.TrackLane trackLaneData, Game.Prefabs.CarLaneData carLaneData, Game.Prefabs.PathfindCarData carPathfindData, System.Single density) : Game.Pathfind.PathSpecification`  

```csharp
public static PathSpecification GetCarDriveSpecification(Curve curve, Game.Net.CarLane carLane, Game.Net.TrackLane trackLaneData, CarLaneData carLaneData, PathfindCarData carPathfindData, float density)
	{
		PathSpecification result = new PathSpecification
		{
			m_Flags = EdgeFlags.Forward,
			m_Methods = (VehicleUtils.GetPathMethods(carLaneData) | PathMethod.Track),
			m_Length = curve.m_Length,
			m_MaxSpeed = carLane.m_SpeedLimit,
			m_Density = math.sqrt(density),
			m_FlowOffset = carLane.m_FlowOffset,
			m_AccessRequirement = math.select(-1, carLane.m_AccessRestriction.Index, carLane.m_AccessRestriction != Entity.Null)
		};
		TryAddCosts(ref result.m_Costs, carPathfindData.m_DrivingCost, result.m_Length);
		TryAddCosts(ref result.m_Costs, carPathfindData.m_CurveAngleCost, curve.m_Bezier);
		TryAddCosts(ref result.m_Costs, carPathfindData.m_LaneCrossCost, (int)carLane.m_LaneCrossCount);
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.Approach) == 0)
		{
			bool flag = (carLane.m_Flags & Game.Net.CarLaneFlags.Forbidden) != 0;
			bool flag2 = (carLane.m_Flags & Game.Net.CarLaneFlags.Unsafe) != 0;
			bool flag3 = (carLane.m_Flags & Game.Net.CarLaneFlags.Highway) != 0;
			bool doIt = (carLane.m_Flags & (Game.Net.CarLaneFlags.TurnLeft | Game.Net.CarLaneFlags.TurnRight | Game.Net.CarLaneFlags.GentleTurnLeft | Game.Net.CarLaneFlags.GentleTurnRight)) != 0;
			bool flag4 = (carLane.m_Flags & (Game.Net.CarLaneFlags.UTurnLeft | Game.Net.CarLaneFlags.UTurnRight)) != 0;
			TryAddCosts(ref result.m_Costs, carPathfindData.m_ForbiddenCost, flag || (flag2 && flag3 && flag4));
			TryAddCosts(ref result.m_Costs, carPathfindData.m_TurningCost, doIt);
			if ((carLane.m_Flags & Game.Net.CarLaneFlags.Unsafe) != 0)
			{
				TryAddCosts(ref result.m_Costs, carPathfindData.m_UnsafeUTurnCost, flag4);
			}
			else
			{
				TryAddCosts(ref result.m_Costs, carPathfindData.m_UTurnCost, flag4);
			}
		}
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.Unsafe) == 0 || (trackLaneData.m_Flags & TrackLaneFlags.AllowMiddle) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowMiddle;
		}
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.Twoway) != 0 || (trackLaneData.m_Flags & TrackLaneFlags.Twoway) != 0)
		{
			result.m_Flags |= EdgeFlags.Backward;
		}
		if (carLane.m_BlockageEnd >= carLane.m_BlockageStart)
		{
			result.m_Rules |= RuleFlags.HasBlockage;
			result.m_BlockageStart = carLane.m_BlockageStart;
			result.m_BlockageEnd = carLane.m_BlockageEnd;
		}
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.ForbidCombustionEngines) != 0)
		{
			result.m_Rules |= RuleFlags.ForbidCombustionEngines;
		}
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.ForbidTransitTraffic) != 0)
		{
			result.m_Rules |= RuleFlags.ForbidTransitTraffic;
		}
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.ForbidHeavyTraffic) != 0)
		{
			result.m_Rules |= RuleFlags.ForbidHeavyTraffic;
		}
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.PublicOnly) != 0)
		{
			result.m_Rules |= RuleFlags.ForbidPrivateTraffic;
		}
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.Highway) != 0)
		{
			result.m_Rules |= RuleFlags.ForbidSlowTraffic;
		}
		if ((carLane.m_Flags & Game.Net.CarLaneFlags.SideConnection) != 0)
		{
			result.m_Flags |= EdgeFlags.SingleOnly;
		}
		if (((uint)carLane.m_Flags & 0x80000000u) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowEnter;
		}
		return result;
	}
```

- `public static GetEndDirection(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, System.Int32& endOffset, System.Boolean& forward) : System.Boolean`  

```csharp
public static bool GetEndDirection(DynamicBuffer<PathElement> path, PathOwner pathOwner, ref ComponentLookup<Curve> curveData, out int endOffset, out bool forward)
	{
		endOffset = 0;
		forward = true;
		if (pathOwner.m_ElementIndex >= path.Length)
		{
			return false;
		}
		PathElement pathElement = path[path.Length - 1];
		while (!curveData.HasComponent(pathElement.m_Target))
		{
			int num = path.Length - 1 - ++endOffset;
			if (num < pathOwner.m_ElementIndex)
			{
				return false;
			}
			pathElement = path[num];
		}
		if (pathElement.m_TargetDelta.x != pathElement.m_TargetDelta.y)
		{
			forward = pathElement.m_TargetDelta.y > pathElement.m_TargetDelta.x;
			return true;
		}
		forward = pathElement.m_TargetDelta.x == 0f;
		bool result = forward || pathElement.m_TargetDelta.x == 1f;
		for (int num2 = path.Length - endOffset - 2; num2 >= pathOwner.m_ElementIndex; num2--)
		{
			PathElement pathElement2 = path[num2];
			if (pathElement2.m_Target != pathElement.m_Target)
			{
				return result;
			}
			if (pathElement2.m_TargetDelta.x != pathElement2.m_TargetDelta.y)
			{
				forward = pathElement2.m_TargetDelta.y > pathElement2.m_TargetDelta.x;
				return true;
			}
		}
		return result;
	}
```

- `public static GetLocationSpecification(Game.Net.Curve curveData) : Game.Pathfind.LocationSpecification`  

```csharp
public static LocationSpecification GetLocationSpecification(float3 position1, float3 position2)
	{
		return new LocationSpecification
		{
			m_Line = new Line3.Segment(position1, position2)
		};
	}
```

- `public static GetLocationSpecification(Game.Net.Curve curveData, Game.Net.ParkingLane parkingLaneData) : Game.Pathfind.LocationSpecification`  

```csharp
public static LocationSpecification GetLocationSpecification(float3 position1, float3 position2)
	{
		return new LocationSpecification
		{
			m_Line = new Line3.Segment(position1, position2)
		};
	}
```

- `public static GetLocationSpecification(Unity.Mathematics.float3 position) : Game.Pathfind.LocationSpecification`  

```csharp
public static LocationSpecification GetLocationSpecification(float3 position1, float3 position2)
	{
		return new LocationSpecification
		{
			m_Line = new Line3.Segment(position1, position2)
		};
	}
```

- `public static GetLocationSpecification(Unity.Mathematics.float3 position1, Unity.Mathematics.float3 position2) : Game.Pathfind.LocationSpecification`  

```csharp
public static LocationSpecification GetLocationSpecification(float3 position1, float3 position2)
	{
		return new LocationSpecification
		{
			m_Line = new Line3.Segment(position1, position2)
		};
	}
```

- `public static GetMasterLane(Unity.Entities.Entity lane, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes) : Unity.Entities.Entity`  

```csharp
public static Entity GetMasterLane(Entity lane, ComponentLookup<SlaveLane> slaveLaneData, ComponentLookup<Owner> ownerData, BufferLookup<Game.Net.SubLane> subLanes)
	{
		if (slaveLaneData.HasComponent(lane) && ownerData.HasComponent(lane))
		{
			SlaveLane slaveLane = slaveLaneData[lane];
			Owner owner = ownerData[lane];
			if (subLanes.HasBuffer(owner.m_Owner))
			{
				return subLanes[owner.m_Owner][slaveLane.m_MasterIndex].m_SubLane;
			}
		}
		return lane;
	}
```

- `public static GetParkingSpaceSpecification(Game.Net.ParkingLane parkingLane, Game.Prefabs.ParkingLaneData parkingLaneData, Game.Prefabs.PathfindCarData carPathfindData) : Game.Pathfind.PathSpecification`  

```csharp
public static PathSpecification GetParkingSpaceSpecification(Game.Net.ParkingLane parkingLane, ParkingLaneData parkingLaneData, PathfindCarData carPathfindData)
	{
		PathSpecification result = new PathSpecification
		{
			m_Flags = (EdgeFlags.Forward | EdgeFlags.Backward | EdgeFlags.FreeBackward),
			m_Methods = PathMethod.Boarding,
			m_Length = 0f,
			m_MaxSpeed = math.max(1f, parkingLane.m_FreeSpace),
			m_Density = VehicleUtils.GetParkingSize(parkingLaneData).x,
			m_AccessRequirement = math.select(-1, parkingLane.m_AccessRestriction.Index, parkingLane.m_AccessRestriction != Entity.Null)
		};
		if ((parkingLane.m_Flags & ParkingLaneFlags.VirtualLane) == 0)
		{
			result.m_Methods |= (PathMethod)(((parkingLane.m_Flags & ParkingLaneFlags.SpecialVehicles) != 0) ? 4096 : 4);
			result.m_MaxSpeed = math.select(result.m_MaxSpeed, 1f, (parkingLane.m_Flags & ParkingLaneFlags.ParkingDisabled) != 0);
		}
		if ((parkingLane.m_Flags & ParkingLaneFlags.AllowEnter) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowEnter;
		}
		if ((parkingLane.m_Flags & ParkingLaneFlags.AllowExit) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowExit;
		}
		carPathfindData.m_ParkingCost.m_Value.z *= (int)parkingLane.m_ParkingFee;
		carPathfindData.m_ParkingCost.m_Value.w *= (float)(65535 - parkingLane.m_ComfortFactor) * 1.5259022E-05f;
		TryAddCosts(ref result.m_Costs, carPathfindData.m_ParkingCost);
		return result;
	}
```

- `public static GetSecondarySpecification(Game.Net.Curve curveData, Game.Net.ConnectionLane connectionLaneData, Game.Net.OutsideConnection outsideConnection, Game.Prefabs.PathfindConnectionData connectionPathfindData) : Game.Pathfind.PathSpecification`  

```csharp
public static PathSpecification GetSecondarySpecification(Curve curveData, Game.Net.ConnectionLane connectionLaneData, Game.Net.OutsideConnection outsideConnection, PathfindConnectionData connectionPathfindData)
	{
		PathSpecification result = new PathSpecification
		{
			m_Flags = (EdgeFlags.Forward | EdgeFlags.Backward),
			m_Length = 0f,
			m_MaxSpeed = 1f,
			m_Density = 0f,
			m_AccessRequirement = math.select(-1, connectionLaneData.m_AccessRestriction.Index, connectionLaneData.m_AccessRestriction != Entity.Null),
			m_Costs = 
			{
				m_Value = 
				{
					x = outsideConnection.m_Delay
				}
			}
		};
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Road) != 0)
		{
			result.m_Methods |= PathMethod.Taxi;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Track) != 0)
		{
			result.m_Methods |= PathMethod.Track;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Pedestrian) != 0)
		{
			result.m_Methods |= PathMethod.Pedestrian;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.AllowMiddle) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowMiddle;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.SecondaryStart) != 0)
		{
			result.m_Flags |= EdgeFlags.SecondaryStart;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.SecondaryEnd) != 0)
		{
			result.m_Flags |= EdgeFlags.SecondaryEnd;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Outside) != 0)
		{
			result.m_Flags |= EdgeFlags.OutsideConnection;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.AllowEnter) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowEnter;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.AllowExit) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowExit;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Parking) != 0)
		{
			result.m_Methods |= PathMethod.Taxi;
			result.m_Flags |= EdgeFlags.FreeForward;
			TryAddCosts(ref result.m_Costs, connectionPathfindData.m_TaxiStartCost);
		}
		else
		{
			TryAddCosts(ref result.m_Costs, ((connectionLaneData.m_Flags & ConnectionLaneFlags.Pedestrian) != 0) ? connectionPathfindData.m_PedestrianBorderCost : connectionPathfindData.m_BorderCost, (connectionLaneData.m_Flags & ConnectionLaneFlags.Start) != 0);
			TryAddCosts(ref result.m_Costs, connectionPathfindData.m_DistanceCost, math.select(0f, curveData.m_Length, (connectionLaneData.m_Flags & ConnectionLaneFlags.Distance) != 0));
		}
		return result;
	}
```

- `public static GetSpawnLocationSpecification(Game.Prefabs.PathfindPedestrianData pedestrianPathfindData, System.Single distance, Unity.Entities.Entity accessRestriction, System.Boolean requireAuthorization, System.Boolean allowEnter, System.Boolean allowExit) : Game.Pathfind.PathSpecification`  

```csharp
public static PathSpecification GetSpawnLocationSpecification(RouteConnectionType connectionType, PathfindConnectionData connectionPathfindData, RoadTypes roadType, float distance, Entity accessRestriction, bool requireAuthorization, bool allowEnter, bool allowExit)
	{
		PathSpecification result = new PathSpecification
		{
			m_Flags = (EdgeFlags.Forward | EdgeFlags.Backward),
			m_AccessRequirement = math.select(-1, accessRestriction.Index, accessRestriction != Entity.Null)
		};
		if (requireAuthorization)
		{
			result.m_Flags |= EdgeFlags.RequireAuthorization;
		}
		if (allowEnter)
		{
			result.m_Flags |= EdgeFlags.AllowEnter;
		}
		if (allowExit)
		{
			result.m_Flags |= EdgeFlags.AllowExit;
		}
		switch (connectionType)
		{
		case RouteConnectionType.Pedestrian:
			result.m_Methods = PathMethod.Pedestrian;
			result.m_Length = distance;
			result.m_MaxSpeed = 5.555556f;
			TryAddCosts(ref result.m_Costs, connectionPathfindData.m_PedestrianSpawnCost);
			break;
		case RouteConnectionType.Road:
			result.m_Methods = PathMethod.Road;
			result.m_Flags |= EdgeFlags.SingleOnly;
			if (roadType == RoadTypes.Car)
			{
				result.m_Length = distance;
				result.m_MaxSpeed = 3f;
				TryAddCosts(ref result.m_Costs, connectionPathfindData.m_CarSpawnCost);
			}
			else
			{
				result.m_MaxSpeed = 1f;
			}
			break;
		case RouteConnectionType.Track:
			result.m_Methods = PathMethod.Track;
			result.m_MaxSpeed = 1f;
			break;
		case RouteConnectionType.Air:
			result.m_Methods = PathMethod.Flying;
			switch (roadType)
			{
			case RoadTypes.Helicopter:
				result.m_Length = 750f;
				result.m_MaxSpeed = 83.333336f;
				TryAddCosts(ref result.m_Costs, connectionPathfindData.m_HelicopterTakeoffCost);
				break;
			case RoadTypes.Airplane:
				result.m_Length = 1500f;
				result.m_MaxSpeed = 277.77777f;
				TryAddCosts(ref result.m_Costs, connectionPathfindData.m_AirplaneTakeoffCost);
				break;
			default:
				result.m_MaxSpeed = 1f;
				break;
			}
			break;
		}
		return result;
	}
```

- `public static GetSpawnLocationSpecification(Game.Prefabs.RouteConnectionType connectionType, Game.Prefabs.PathfindCarData carPathfindData, Game.Net.CarLane carLane, System.Single distance, System.Int32 laneCrossCount, Unity.Entities.Entity accessRestriction, System.Boolean requireAuthorization, System.Boolean allowEnter, System.Boolean allowExit) : Game.Pathfind.PathSpecification`  

```csharp
public static PathSpecification GetSpawnLocationSpecification(RouteConnectionType connectionType, PathfindConnectionData connectionPathfindData, RoadTypes roadType, float distance, Entity accessRestriction, bool requireAuthorization, bool allowEnter, bool allowExit)
	{
		PathSpecification result = new PathSpecification
		{
			m_Flags = (EdgeFlags.Forward | EdgeFlags.Backward),
			m_AccessRequirement = math.select(-1, accessRestriction.Index, accessRestriction != Entity.Null)
		};
		if (requireAuthorization)
		{
			result.m_Flags |= EdgeFlags.RequireAuthorization;
		}
		if (allowEnter)
		{
			result.m_Flags |= EdgeFlags.AllowEnter;
		}
		if (allowExit)
		{
			result.m_Flags |= EdgeFlags.AllowExit;
		}
		switch (connectionType)
		{
		case RouteConnectionType.Pedestrian:
			result.m_Methods = PathMethod.Pedestrian;
			result.m_Length = distance;
			result.m_MaxSpeed = 5.555556f;
			TryAddCosts(ref result.m_Costs, connectionPathfindData.m_PedestrianSpawnCost);
			break;
		case RouteConnectionType.Road:
			result.m_Methods = PathMethod.Road;
			result.m_Flags |= EdgeFlags.SingleOnly;
			if (roadType == RoadTypes.Car)
			{
				result.m_Length = distance;
				result.m_MaxSpeed = 3f;
				TryAddCosts(ref result.m_Costs, connectionPathfindData.m_CarSpawnCost);
			}
			else
			{
				result.m_MaxSpeed = 1f;
			}
			break;
		case RouteConnectionType.Track:
			result.m_Methods = PathMethod.Track;
			result.m_MaxSpeed = 1f;
			break;
		case RouteConnectionType.Air:
			result.m_Methods = PathMethod.Flying;
			switch (roadType)
			{
			case RoadTypes.Helicopter:
				result.m_Length = 750f;
				result.m_MaxSpeed = 83.333336f;
				TryAddCosts(ref result.m_Costs, connectionPathfindData.m_HelicopterTakeoffCost);
				break;
			case RoadTypes.Airplane:
				result.m_Length = 1500f;
				result.m_MaxSpeed = 277.77777f;
				TryAddCosts(ref result.m_Costs, connectionPathfindData.m_AirplaneTakeoffCost);
				break;
			default:
				result.m_MaxSpeed = 1f;
				break;
			}
			break;
		}
		return result;
	}
```

- `public static GetSpawnLocationSpecification(Game.Prefabs.PathfindTrackData trackPathfindData, Unity.Entities.Entity accessRestriction) : Game.Pathfind.PathSpecification`  

```csharp
public static PathSpecification GetSpawnLocationSpecification(RouteConnectionType connectionType, PathfindConnectionData connectionPathfindData, RoadTypes roadType, float distance, Entity accessRestriction, bool requireAuthorization, bool allowEnter, bool allowExit)
	{
		PathSpecification result = new PathSpecification
		{
			m_Flags = (EdgeFlags.Forward | EdgeFlags.Backward),
			m_AccessRequirement = math.select(-1, accessRestriction.Index, accessRestriction != Entity.Null)
		};
		if (requireAuthorization)
		{
			result.m_Flags |= EdgeFlags.RequireAuthorization;
		}
		if (allowEnter)
		{
			result.m_Flags |= EdgeFlags.AllowEnter;
		}
		if (allowExit)
		{
			result.m_Flags |= EdgeFlags.AllowExit;
		}
		switch (connectionType)
		{
		case RouteConnectionType.Pedestrian:
			result.m_Methods = PathMethod.Pedestrian;
			result.m_Length = distance;
			result.m_MaxSpeed = 5.555556f;
			TryAddCosts(ref result.m_Costs, connectionPathfindData.m_PedestrianSpawnCost);
			break;
		case RouteConnectionType.Road:
			result.m_Methods = PathMethod.Road;
			result.m_Flags |= EdgeFlags.SingleOnly;
			if (roadType == RoadTypes.Car)
			{
				result.m_Length = distance;
				result.m_MaxSpeed = 3f;
				TryAddCosts(ref result.m_Costs, connectionPathfindData.m_CarSpawnCost);
			}
			else
			{
				result.m_MaxSpeed = 1f;
			}
			break;
		case RouteConnectionType.Track:
			result.m_Methods = PathMethod.Track;
			result.m_MaxSpeed = 1f;
			break;
		case RouteConnectionType.Air:
			result.m_Methods = PathMethod.Flying;
			switch (roadType)
			{
			case RoadTypes.Helicopter:
				result.m_Length = 750f;
				result.m_MaxSpeed = 83.333336f;
				TryAddCosts(ref result.m_Costs, connectionPathfindData.m_HelicopterTakeoffCost);
				break;
			case RoadTypes.Airplane:
				result.m_Length = 1500f;
				result.m_MaxSpeed = 277.77777f;
				TryAddCosts(ref result.m_Costs, connectionPathfindData.m_AirplaneTakeoffCost);
				break;
			default:
				result.m_MaxSpeed = 1f;
				break;
			}
			break;
		}
		return result;
	}
```

- `public static GetSpawnLocationSpecification(Game.Prefabs.RouteConnectionType connectionType, Game.Prefabs.PathfindConnectionData connectionPathfindData, Game.Net.RoadTypes roadType, System.Single distance, Unity.Entities.Entity accessRestriction, System.Boolean requireAuthorization, System.Boolean allowEnter, System.Boolean allowExit) : Game.Pathfind.PathSpecification`  

```csharp
public static PathSpecification GetSpawnLocationSpecification(RouteConnectionType connectionType, PathfindConnectionData connectionPathfindData, RoadTypes roadType, float distance, Entity accessRestriction, bool requireAuthorization, bool allowEnter, bool allowExit)
	{
		PathSpecification result = new PathSpecification
		{
			m_Flags = (EdgeFlags.Forward | EdgeFlags.Backward),
			m_AccessRequirement = math.select(-1, accessRestriction.Index, accessRestriction != Entity.Null)
		};
		if (requireAuthorization)
		{
			result.m_Flags |= EdgeFlags.RequireAuthorization;
		}
		if (allowEnter)
		{
			result.m_Flags |= EdgeFlags.AllowEnter;
		}
		if (allowExit)
		{
			result.m_Flags |= EdgeFlags.AllowExit;
		}
		switch (connectionType)
		{
		case RouteConnectionType.Pedestrian:
			result.m_Methods = PathMethod.Pedestrian;
			result.m_Length = distance;
			result.m_MaxSpeed = 5.555556f;
			TryAddCosts(ref result.m_Costs, connectionPathfindData.m_PedestrianSpawnCost);
			break;
		case RouteConnectionType.Road:
			result.m_Methods = PathMethod.Road;
			result.m_Flags |= EdgeFlags.SingleOnly;
			if (roadType == RoadTypes.Car)
			{
				result.m_Length = distance;
				result.m_MaxSpeed = 3f;
				TryAddCosts(ref result.m_Costs, connectionPathfindData.m_CarSpawnCost);
			}
			else
			{
				result.m_MaxSpeed = 1f;
			}
			break;
		case RouteConnectionType.Track:
			result.m_Methods = PathMethod.Track;
			result.m_MaxSpeed = 1f;
			break;
		case RouteConnectionType.Air:
			result.m_Methods = PathMethod.Flying;
			switch (roadType)
			{
			case RoadTypes.Helicopter:
				result.m_Length = 750f;
				result.m_MaxSpeed = 83.333336f;
				TryAddCosts(ref result.m_Costs, connectionPathfindData.m_HelicopterTakeoffCost);
				break;
			case RoadTypes.Airplane:
				result.m_Length = 1500f;
				result.m_MaxSpeed = 277.77777f;
				TryAddCosts(ref result.m_Costs, connectionPathfindData.m_AirplaneTakeoffCost);
				break;
			default:
				result.m_MaxSpeed = 1f;
				break;
			}
			break;
		}
		return result;
	}
```

- `public static GetSpecification(Game.Net.Curve curveData, Game.Net.PedestrianLane pedestrianLaneData, Game.Prefabs.PathfindPedestrianData pedestrianPathfindData) : Game.Pathfind.PathSpecification`  

```csharp
public static PathSpecification GetSpecification(Curve curveData, Game.Net.ConnectionLane connectionLaneData, GarageLane garageLane, Game.Net.OutsideConnection outsideConnection, PathfindConnectionData connectionPathfindData)
	{
		PathSpecification result = new PathSpecification
		{
			m_Flags = (EdgeFlags.Forward | EdgeFlags.Backward),
			m_AccessRequirement = math.select(-1, connectionLaneData.m_AccessRestriction.Index, connectionLaneData.m_AccessRestriction != Entity.Null),
			m_Costs = 
			{
				m_Value = 
				{
					x = outsideConnection.m_Delay
				}
			}
		};
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Parking) != 0)
		{
			result.m_Methods |= PathMethod.Parking;
			if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Outside) != 0)
			{
				result.m_Methods |= PathMethod.Boarding;
				result.m_MaxSpeed = 1000000f;
				result.m_Density = 1000000f;
			}
			else
			{
				bool test = garageLane.m_VehicleCount < garageLane.m_VehicleCapacity && (connectionLaneData.m_Flags & ConnectionLaneFlags.Disabled) == 0;
				result.m_Flags |= EdgeFlags.FreeBackward;
				result.m_MaxSpeed = math.select(1f, 1000000f, test);
				result.m_Density = math.select(0f, 1000000f, test);
				connectionPathfindData.m_ParkingCost.m_Value.z *= (int)garageLane.m_ParkingFee;
				connectionPathfindData.m_ParkingCost.m_Value.w *= (float)(65535 - garageLane.m_ComfortFactor) * 1.5259022E-05f;
				TryAddCosts(ref result.m_Costs, connectionPathfindData.m_ParkingCost);
			}
		}
		else if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Airway) != 0)
		{
			result.m_Length = curveData.m_Length;
			result.m_MaxSpeed = math.select(83.333336f, 277.77777f, (connectionLaneData.m_RoadTypes & RoadTypes.Airplane) != 0);
		}
		else if ((connectionLaneData.m_Flags & (ConnectionLaneFlags.Inside | ConnectionLaneFlags.Area)) != 0)
		{
			result.m_Length = curveData.m_Length;
			result.m_MaxSpeed = math.select(3f, 5.555556f, (connectionLaneData.m_Flags & ConnectionLaneFlags.Pedestrian) != 0);
		}
		else
		{
			result.m_MaxSpeed = 1f;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Road) != 0)
		{
			if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Area) != 0)
			{
				result.m_Methods |= PathMethod.Offroad;
			}
			else
			{
				result.m_Methods |= PathMethod.Road;
			}
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Track) != 0)
		{
			result.m_Methods |= PathMethod.Track;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Pedestrian) != 0)
		{
			result.m_Methods |= PathMethod.Pedestrian;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.AllowMiddle) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowMiddle;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.AllowCargo) != 0)
		{
			result.m_Methods |= PathMethod.CargoLoading;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Airway) != 0)
		{
			result.m_Methods |= PathMethod.Flying;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Outside) != 0)
		{
			result.m_Flags |= EdgeFlags.OutsideConnection;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.AllowEnter) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowEnter;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.AllowExit) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowExit;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Parking) == 0)
		{
			TryAddCosts(ref result.m_Costs, ((connectionLaneData.m_Flags & ConnectionLaneFlags.Pedestrian) != 0) ? connectionPathfindData.m_PedestrianBorderCost : connectionPathfindData.m_BorderCost, (connectionLaneData.m_Flags & ConnectionLaneFlags.Start) != 0);
			TryAddCosts(ref result.m_Costs, connectionPathfindData.m_DistanceCost, math.select(0f, curveData.m_Length, (connectionLaneData.m_Flags & ConnectionLaneFlags.Distance) != 0));
		}
		TryAddCosts(ref result.m_Costs, connectionPathfindData.m_AirwayCost, result.m_Length, (connectionLaneData.m_Flags & ConnectionLaneFlags.Airway) != 0);
		TryAddCosts(ref result.m_Costs, connectionPathfindData.m_InsideCost, result.m_Length, (connectionLaneData.m_Flags & ConnectionLaneFlags.Inside) != 0);
		TryAddCosts(ref result.m_Costs, connectionPathfindData.m_AreaCost, result.m_Length, (connectionLaneData.m_Flags & ConnectionLaneFlags.Area) != 0);
		return result;
	}
```

- `public static GetSpecification(Game.Net.Curve curveData, Game.Net.ConnectionLane connectionLaneData, Game.Net.GarageLane garageLane, Game.Net.OutsideConnection outsideConnection, Game.Prefabs.PathfindConnectionData connectionPathfindData) : Game.Pathfind.PathSpecification`  

```csharp
public static PathSpecification GetSpecification(Curve curveData, Game.Net.ConnectionLane connectionLaneData, GarageLane garageLane, Game.Net.OutsideConnection outsideConnection, PathfindConnectionData connectionPathfindData)
	{
		PathSpecification result = new PathSpecification
		{
			m_Flags = (EdgeFlags.Forward | EdgeFlags.Backward),
			m_AccessRequirement = math.select(-1, connectionLaneData.m_AccessRestriction.Index, connectionLaneData.m_AccessRestriction != Entity.Null),
			m_Costs = 
			{
				m_Value = 
				{
					x = outsideConnection.m_Delay
				}
			}
		};
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Parking) != 0)
		{
			result.m_Methods |= PathMethod.Parking;
			if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Outside) != 0)
			{
				result.m_Methods |= PathMethod.Boarding;
				result.m_MaxSpeed = 1000000f;
				result.m_Density = 1000000f;
			}
			else
			{
				bool test = garageLane.m_VehicleCount < garageLane.m_VehicleCapacity && (connectionLaneData.m_Flags & ConnectionLaneFlags.Disabled) == 0;
				result.m_Flags |= EdgeFlags.FreeBackward;
				result.m_MaxSpeed = math.select(1f, 1000000f, test);
				result.m_Density = math.select(0f, 1000000f, test);
				connectionPathfindData.m_ParkingCost.m_Value.z *= (int)garageLane.m_ParkingFee;
				connectionPathfindData.m_ParkingCost.m_Value.w *= (float)(65535 - garageLane.m_ComfortFactor) * 1.5259022E-05f;
				TryAddCosts(ref result.m_Costs, connectionPathfindData.m_ParkingCost);
			}
		}
		else if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Airway) != 0)
		{
			result.m_Length = curveData.m_Length;
			result.m_MaxSpeed = math.select(83.333336f, 277.77777f, (connectionLaneData.m_RoadTypes & RoadTypes.Airplane) != 0);
		}
		else if ((connectionLaneData.m_Flags & (ConnectionLaneFlags.Inside | ConnectionLaneFlags.Area)) != 0)
		{
			result.m_Length = curveData.m_Length;
			result.m_MaxSpeed = math.select(3f, 5.555556f, (connectionLaneData.m_Flags & ConnectionLaneFlags.Pedestrian) != 0);
		}
		else
		{
			result.m_MaxSpeed = 1f;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Road) != 0)
		{
			if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Area) != 0)
			{
				result.m_Methods |= PathMethod.Offroad;
			}
			else
			{
				result.m_Methods |= PathMethod.Road;
			}
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Track) != 0)
		{
			result.m_Methods |= PathMethod.Track;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Pedestrian) != 0)
		{
			result.m_Methods |= PathMethod.Pedestrian;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.AllowMiddle) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowMiddle;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.AllowCargo) != 0)
		{
			result.m_Methods |= PathMethod.CargoLoading;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Airway) != 0)
		{
			result.m_Methods |= PathMethod.Flying;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Outside) != 0)
		{
			result.m_Flags |= EdgeFlags.OutsideConnection;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.AllowEnter) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowEnter;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.AllowExit) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowExit;
		}
		if ((connectionLaneData.m_Flags & ConnectionLaneFlags.Parking) == 0)
		{
			TryAddCosts(ref result.m_Costs, ((connectionLaneData.m_Flags & ConnectionLaneFlags.Pedestrian) != 0) ? connectionPathfindData.m_PedestrianBorderCost : connectionPathfindData.m_BorderCost, (connectionLaneData.m_Flags & ConnectionLaneFlags.Start) != 0);
			TryAddCosts(ref result.m_Costs, connectionPathfindData.m_DistanceCost, math.select(0f, curveData.m_Length, (connectionLaneData.m_Flags & ConnectionLaneFlags.Distance) != 0));
		}
		TryAddCosts(ref result.m_Costs, connectionPathfindData.m_AirwayCost, result.m_Length, (connectionLaneData.m_Flags & ConnectionLaneFlags.Airway) != 0);
		TryAddCosts(ref result.m_Costs, connectionPathfindData.m_InsideCost, result.m_Length, (connectionLaneData.m_Flags & ConnectionLaneFlags.Inside) != 0);
		TryAddCosts(ref result.m_Costs, connectionPathfindData.m_AreaCost, result.m_Length, (connectionLaneData.m_Flags & ConnectionLaneFlags.Area) != 0);
		return result;
	}
```

- `public static GetStartDirection(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Game.Pathfind.PathOwner pathOwner, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, System.Int32& startOffset, System.Boolean& forward) : System.Boolean`  

```csharp
public static bool GetStartDirection(DynamicBuffer<PathElement> path, PathOwner pathOwner, ref ComponentLookup<Curve> curveData, out int startOffset, out bool forward)
	{
		startOffset = 0;
		forward = true;
		if (pathOwner.m_ElementIndex >= path.Length)
		{
			return false;
		}
		PathElement pathElement = path[pathOwner.m_ElementIndex];
		while (!curveData.HasComponent(pathElement.m_Target))
		{
			int num = pathOwner.m_ElementIndex + ++startOffset;
			if (num >= path.Length)
			{
				return false;
			}
			pathElement = path[num];
		}
		if (pathElement.m_TargetDelta.x != pathElement.m_TargetDelta.y)
		{
			forward = pathElement.m_TargetDelta.y > pathElement.m_TargetDelta.x;
			return true;
		}
		forward = pathElement.m_TargetDelta.y == 1f;
		bool result = forward || pathElement.m_TargetDelta.y == 0f;
		for (int i = pathOwner.m_ElementIndex + startOffset + 1; i < path.Length; i++)
		{
			PathElement pathElement2 = path[i];
			if (pathElement2.m_Target != pathElement.m_Target)
			{
				return result;
			}
			if (pathElement2.m_TargetDelta.x != pathElement2.m_TargetDelta.y)
			{
				forward = pathElement2.m_TargetDelta.y > pathElement2.m_TargetDelta.x;
				return true;
			}
		}
		return result;
	}
```

- `public static GetTaxiAccessSpecification(Game.Net.ParkingLane parkingLaneData, Game.Prefabs.PathfindCarData carPathfindData, Game.Prefabs.PathfindTransportData transportPathfindData) : Game.Pathfind.PathSpecification`  

```csharp
public static PathSpecification GetTaxiAccessSpecification(Game.Net.ParkingLane parkingLaneData, PathfindCarData carPathfindData, PathfindTransportData transportPathfindData)
	{
		PathSpecification result = new PathSpecification
		{
			m_Flags = (EdgeFlags.Forward | EdgeFlags.SecondaryStart | EdgeFlags.FreeForward),
			m_Methods = PathMethod.Taxi,
			m_Length = 0f,
			m_MaxSpeed = 1f,
			m_Density = 0f,
			m_AccessRequirement = math.select(-1, parkingLaneData.m_AccessRestriction.Index, parkingLaneData.m_AccessRestriction != Entity.Null)
		};
		if ((parkingLaneData.m_Flags & ParkingLaneFlags.AllowEnter) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowEnter;
		}
		if ((parkingLaneData.m_Flags & ParkingLaneFlags.AllowExit) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowExit;
		}
		if (parkingLaneData.m_TaxiAvailability != 0)
		{
			result.m_Flags |= EdgeFlags.Backward;
			transportPathfindData.m_OrderingCost.m_Value.x += GetTaxiAvailabilityDelay(parkingLaneData);
			transportPathfindData.m_StartingCost.m_Value.z *= (int)parkingLaneData.m_TaxiFee;
			TryAddCosts(ref result.m_Costs, transportPathfindData.m_OrderingCost);
			TryAddCosts(ref result.m_Costs, transportPathfindData.m_StartingCost);
		}
		return result;
	}
```

- `public static GetTaxiAvailabilityDelay(Game.Net.ParkingLane parkingLaneData) : System.Single`  

```csharp
public static float GetTaxiAvailabilityDelay(Game.Net.ParkingLane parkingLaneData)
	{
		return 100f / (0.25f + (float)(int)parkingLaneData.m_TaxiAvailability * 1.5259022E-05f) - 80f;
	}
```

- `public static GetTaxiDriveSpecification(Game.Net.Curve curveData, Game.Net.CarLane carLaneData, Game.Prefabs.PathfindCarData carPathfindData, Game.Prefabs.PathfindTransportData transportPathfindData, System.Single density) : Game.Pathfind.PathSpecification`  

```csharp
public static PathSpecification GetTaxiDriveSpecification(Curve curveData, Game.Net.CarLane carLaneData, PathfindCarData carPathfindData, PathfindTransportData transportPathfindData, float density)
	{
		PathSpecification result = new PathSpecification
		{
			m_Flags = (EdgeFlags.Forward | EdgeFlags.SecondaryStart | EdgeFlags.SecondaryEnd),
			m_Methods = PathMethod.Taxi,
			m_Length = curveData.m_Length,
			m_MaxSpeed = carLaneData.m_SpeedLimit,
			m_Density = math.sqrt(density),
			m_FlowOffset = carLaneData.m_FlowOffset,
			m_AccessRequirement = math.select(-1, carLaneData.m_AccessRestriction.Index, carLaneData.m_AccessRestriction != Entity.Null)
		};
		transportPathfindData.m_TravelCost.m_Value.z *= 0.03f;
		TryAddCosts(ref result.m_Costs, transportPathfindData.m_TravelCost, result.m_Length);
		TryAddCosts(ref result.m_Costs, carPathfindData.m_CurveAngleCost, curveData.m_Bezier);
		TryAddCosts(ref result.m_Costs, carPathfindData.m_LaneCrossCost, (int)carLaneData.m_LaneCrossCount);
		if ((carLaneData.m_Flags & Game.Net.CarLaneFlags.Approach) == 0)
		{
			bool flag = (carLaneData.m_Flags & Game.Net.CarLaneFlags.Forbidden) != 0;
			bool flag2 = (carLaneData.m_Flags & Game.Net.CarLaneFlags.Unsafe) != 0;
			bool flag3 = (carLaneData.m_Flags & Game.Net.CarLaneFlags.Highway) != 0;
			bool doIt = (carLaneData.m_Flags & (Game.Net.CarLaneFlags.TurnLeft | Game.Net.CarLaneFlags.TurnRight | Game.Net.CarLaneFlags.GentleTurnLeft | Game.Net.CarLaneFlags.GentleTurnRight)) != 0;
			bool flag4 = (carLaneData.m_Flags & (Game.Net.CarLaneFlags.UTurnLeft | Game.Net.CarLaneFlags.UTurnRight)) != 0;
			TryAddCosts(ref result.m_Costs, carPathfindData.m_ForbiddenCost, flag || (flag2 && flag3 && flag4));
			TryAddCosts(ref result.m_Costs, carPathfindData.m_TurningCost, doIt);
			if ((carLaneData.m_Flags & Game.Net.CarLaneFlags.Unsafe) != 0)
			{
				TryAddCosts(ref result.m_Costs, carPathfindData.m_UnsafeUTurnCost, flag4);
			}
			else
			{
				TryAddCosts(ref result.m_Costs, carPathfindData.m_UTurnCost, flag4);
			}
		}
		if ((carLaneData.m_Flags & Game.Net.CarLaneFlags.Unsafe) == 0)
		{
			result.m_Flags |= EdgeFlags.AllowMiddle;
		}
		if ((carLaneData.m_Flags & Game.Net.CarLaneFlags.Twoway) != 0)
		{
			result.m_Flags |= EdgeFlags.Backward;
		}
		if (carLaneData.m_BlockageEnd >= carLaneData.m_BlockageStart)
		{
			result.m_Rules |= RuleFlags.HasBlockage;
			result.m_BlockageStart = carLaneData.m_BlockageStart;
			result.m_BlockageEnd = carLaneData.m_BlockageEnd;
		}
		if ((carLaneData.m_Flags & Game.Net.CarLaneFlags.ForbidCombustionEngines) != 0)
		{
			result.m_Rules |= RuleFlags.ForbidCombustionEngines;
		}
		if ((carLaneData.m_Flags & Game.Net.CarLaneFlags.ForbidTransitTraffic) != 0)
		{
			result.m_Rules |= RuleFlags.ForbidTransitTraffic;
		}
		if ((carLaneData.m_Flags & Game.Net.CarLaneFlags.ForbidHeavyTraffic) != 0)
		{
			result.m_Rules |= RuleFlags.ForbidHeavyTraffic;
		}
		if ((carLaneData.m_Flags & Game.Net.CarLaneFlags.PublicOnly) != 0)
		{
			result.m_Rules |= RuleFlags.ForbidPrivateTraffic;
		}
		if ((carLaneData.m_Flags & Game.Net.CarLaneFlags.Highway) != 0)
		{
			result.m_Rules |= RuleFlags.ForbidSlowTraffic;
		}
		if ((carLaneData.m_Flags & Game.Net.CarLaneFlags.SideConnection) != 0)
		{
			result.m_Flags |= EdgeFlags.SingleOnly;
		}
		if (((uint)carLaneData.m_Flags & 0x80000000u) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowEnter;
		}
		return result;
	}
```

- `public static GetTaxiStopSpecification(Game.Routes.TransportStop transportStop, Game.Routes.TaxiStand taxiStand, Game.Routes.WaitingPassengers waitingPassengers, Game.Prefabs.PathfindTransportData transportPathfindData) : Game.Pathfind.PathSpecification`  

```csharp
public static PathSpecification GetTaxiStopSpecification(Game.Routes.TransportStop transportStop, TaxiStand taxiStand, WaitingPassengers waitingPassengers, PathfindTransportData transportPathfindData)
	{
		PathSpecification result = new PathSpecification
		{
			m_Flags = EdgeFlags.SecondaryEnd,
			m_Methods = PathMethod.Taxi,
			m_Length = 0f,
			m_MaxSpeed = 1f,
			m_Density = 0f,
			m_AccessRequirement = math.select(-1, transportStop.m_AccessRestriction.Index, transportStop.m_AccessRestriction != Entity.Null)
		};
		if ((transportStop.m_Flags & StopFlags.Active) != 0)
		{
			result.m_Flags |= EdgeFlags.Forward;
		}
		if ((transportStop.m_Flags & StopFlags.AllowEnter) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowEnter;
		}
		if (transportStop.m_AccessRestriction != Entity.Null)
		{
			result.m_Flags |= EdgeFlags.AllowExit;
		}
		transportPathfindData.m_StartingCost.m_Value.x += (int)waitingPassengers.m_AverageWaitingTime;
		transportPathfindData.m_StartingCost.m_Value.z *= (int)taxiStand.m_StartingFee;
		transportPathfindData.m_StartingCost.m_Value.w *= 1f - transportStop.m_ComfortFactor;
		TryAddCosts(ref result.m_Costs, transportPathfindData.m_StartingCost);
		return result;
	}
```

- `public static GetTrackDriveSpecification(Game.Net.Curve curveData, Game.Net.TrackLane trackLaneData, Game.Prefabs.PathfindTrackData trackPathfindData) : Game.Pathfind.PathSpecification`  

```csharp
public static PathSpecification GetTrackDriveSpecification(Curve curveData, Game.Net.TrackLane trackLaneData, PathfindTrackData trackPathfindData)
	{
		PathSpecification result = new PathSpecification
		{
			m_Flags = (((trackLaneData.m_Flags & TrackLaneFlags.Twoway) == 0) ? EdgeFlags.Forward : (EdgeFlags.Forward | EdgeFlags.Backward)),
			m_Methods = PathMethod.Track,
			m_Length = curveData.m_Length,
			m_MaxSpeed = trackLaneData.m_SpeedLimit,
			m_Density = 0f,
			m_AccessRequirement = math.select(-1, trackLaneData.m_AccessRestriction.Index, trackLaneData.m_AccessRestriction != Entity.Null)
		};
		if ((trackLaneData.m_Flags & TrackLaneFlags.AllowMiddle) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowMiddle;
		}
		TryAddCosts(ref result.m_Costs, trackPathfindData.m_DrivingCost, result.m_Length);
		TryAddCosts(ref result.m_Costs, trackPathfindData.m_CurveAngleCost, curveData.m_Bezier);
		TryAddCosts(ref result.m_Costs, trackPathfindData.m_TwowayCost, (trackLaneData.m_Flags & TrackLaneFlags.Twoway) != 0);
		TryAddCosts(ref result.m_Costs, trackPathfindData.m_SwitchCost, (trackLaneData.m_Flags & TrackLaneFlags.Switch) != 0);
		TryAddCosts(ref result.m_Costs, trackPathfindData.m_SwitchCost, (trackLaneData.m_Flags & TrackLaneFlags.DoubleSwitch) != 0);
		TryAddCosts(ref result.m_Costs, trackPathfindData.m_DiamondCrossingCost, (trackLaneData.m_Flags & TrackLaneFlags.DiamondCrossing) != 0);
		return result;
	}
```

- `public static GetTransportLineSpecification(Game.Prefabs.TransportLineData transportLineData, Game.Prefabs.PathfindTransportData transportPathfindData, Game.Routes.RouteInfo routeInfo) : Game.Pathfind.PathSpecification`  

```csharp
public static PathSpecification GetTransportLineSpecification(TransportLineData transportLineData, PathfindTransportData transportPathfindData, RouteInfo routeInfo)
	{
		PathSpecification result = new PathSpecification
		{
			m_Length = routeInfo.m_Distance,
			m_MaxSpeed = math.max(1f, routeInfo.m_Distance) / math.max(1f, routeInfo.m_Duration),
			m_Density = 1f,
			m_AccessRequirement = -1
		};
		if (routeInfo.m_Distance > 0f && routeInfo.m_Duration > 0f)
		{
			result.m_Flags |= EdgeFlags.Forward;
		}
		if (transportLineData.m_PassengerTransport)
		{
			if ((routeInfo.m_Flags & RouteInfoFlags.InactiveDay) == 0)
			{
				result.m_Methods |= PathMethod.PublicTransportDay;
			}
			if ((routeInfo.m_Flags & RouteInfoFlags.InactiveNight) == 0)
			{
				result.m_Methods |= PathMethod.PublicTransportNight;
			}
		}
		if (transportLineData.m_CargoTransport && (routeInfo.m_Flags & (RouteInfoFlags)3) != (RouteInfoFlags)3)
		{
			result.m_Methods |= PathMethod.CargoTransport;
		}
		TryAddCosts(ref result.m_Costs, transportPathfindData.m_TravelCost, routeInfo.m_Distance);
		return result;
	}
```

- `public static GetTransportStopSpecification(Game.Routes.TransportStop transportStop, Game.Routes.TransportLine transportLine, Game.Routes.WaitingPassengers waitingPassengers, Game.Prefabs.TransportLineData transportLineData, Game.Prefabs.PathfindTransportData transportPathfindData, System.Boolean isWaypoint) : Game.Pathfind.PathSpecification`  

```csharp
public static PathSpecification GetTransportStopSpecification(Game.Routes.TransportStop transportStop, TransportLine transportLine, WaitingPassengers waitingPassengers, TransportLineData transportLineData, PathfindTransportData transportPathfindData, bool isWaypoint)
	{
		PathSpecification result = new PathSpecification
		{
			m_Flags = EdgeFlags.FreeBackward,
			m_Length = 0f,
			m_MaxSpeed = 1f,
			m_Density = 0f,
			m_AccessRequirement = math.select(-1, transportStop.m_AccessRestriction.Index, transportStop.m_AccessRestriction != Entity.Null)
		};
		if ((transportStop.m_Flags & StopFlags.Active) != 0)
		{
			result.m_Flags |= EdgeFlags.Forward;
		}
		if ((transportStop.m_Flags & StopFlags.AllowEnter) != 0)
		{
			result.m_Flags |= EdgeFlags.AllowEnter;
		}
		if (!isWaypoint)
		{
			result.m_Flags |= EdgeFlags.Backward;
		}
		if (transportStop.m_AccessRestriction != Entity.Null)
		{
			result.m_Flags |= EdgeFlags.AllowExit;
		}
		if (transportLineData.m_PassengerTransport)
		{
			result.m_Methods |= PathMethod.PublicTransportDay | PathMethod.PublicTransportNight;
		}
		if (transportLineData.m_CargoTransport)
		{
			result.m_Methods |= PathMethod.CargoTransport;
		}
		float stopDuration = RouteUtils.GetStopDuration(transportLineData, transportStop);
		float num = math.max(transportLine.m_VehicleInterval * 0.5f, (int)waitingPassengers.m_AverageWaitingTime) - stopDuration;
		transportPathfindData.m_StartingCost.m_Value.x = math.max(0f, transportPathfindData.m_StartingCost.m_Value.x + num);
		transportPathfindData.m_StartingCost.m_Value.z *= (int)transportLine.m_TicketPrice;
		transportPathfindData.m_StartingCost.m_Value.w *= 1f - transportStop.m_ComfortFactor;
		TryAddCosts(ref result.m_Costs, transportPathfindData.m_StartingCost);
		return result;
	}
```

- `public static InitializeSpawnPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Collections.NativeList<Game.Pathfind.PathElement> laneBuffer, Unity.Entities.Entity parkingLocation, Game.Pathfind.PathOwner& pathOwner, System.Single length, Unity.Entities.ComponentLookup`1[[Game.Net.Curve, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& curveData, Unity.Entities.ComponentLookup`1[[Game.Net.Lane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& laneData, Unity.Entities.ComponentLookup`1[[Game.Net.EdgeLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeLaneData, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Net.Edge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& edgeData, Unity.Entities.ComponentLookup`1[[Game.Objects.SpawnLocation, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& spawnLocationData, Unity.Entities.BufferLookup`1[[Game.Net.ConnectedEdge, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedEdges, Unity.Entities.BufferLookup`1[[Game.Net.SubLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& subLanes) : System.Void`  

```csharp
public static void InitializeSpawnPath(DynamicBuffer<PathElement> path, NativeList<PathElement> laneBuffer, Entity parkingLocation, ref PathOwner pathOwner, float length, ref ComponentLookup<Curve> curveData, ref ComponentLookup<Lane> laneData, ref ComponentLookup<EdgeLane> edgeLaneData, ref ComponentLookup<Owner> ownerData, ref ComponentLookup<Game.Net.Edge> edgeData, ref ComponentLookup<Game.Objects.SpawnLocation> spawnLocationData, ref BufferLookup<ConnectedEdge> connectedEdges, ref BufferLookup<Game.Net.SubLane> subLanes)
	{
		Entity laneEntity;
		Entity laneEntity2;
		bool forward2;
		bool forward3;
		float2 targetDelta2;
		float2 targetDelta;
		if (path.IsCreated)
		{
			if (!GetStartDirection(path, pathOwner, ref curveData, out var startOffset, out var forward))
			{
				return;
			}
			pathOwner.m_ElementIndex += startOffset;
			PathElement pathElement = path[pathOwner.m_ElementIndex];
			laneEntity = pathElement.m_Target;
			laneEntity2 = pathElement.m_Target;
			forward2 = !forward;
			forward3 = forward;
			targetDelta = (forward2 ? new float2(1f, pathElement.m_TargetDelta.x) : new float2(0f, pathElement.m_TargetDelta.x));
			targetDelta2 = (forward3 ? new float2(pathElement.m_TargetDelta.x, 1f) : new float2(pathElement.m_TargetDelta.x, 0f));
		}
		else
		{
			if (!spawnLocationData.TryGetComponent(parkingLocation, out var componentData) || !curveData.HasComponent(componentData.m_ConnectedLane1))
			{
				return;
			}
			laneEntity = componentData.m_ConnectedLane1;
			laneEntity2 = componentData.m_ConnectedLane1;
			forward2 = false;
			forward3 = true;
			targetDelta = new float2(0f, componentData.m_CurvePosition1);
			targetDelta2 = new float2(componentData.m_CurvePosition1, 1f);
		}
		float num = length * 0.5f;
		float num2 = 0f;
		for (int i = 0; i < 10000; i++)
		{
			float num3 = curveData[laneEntity].m_Length * math.abs(targetDelta.y - targetDelta.x);
			if (num3 >= num)
			{
				float t = math.select(num / num3, 1f, num3 == 0f);
				targetDelta.x = math.lerp(targetDelta.y, targetDelta.x, t);
				laneBuffer.Add(new PathElement(laneEntity, targetDelta));
				num2 = num;
				num = 0f;
				break;
			}
			laneBuffer.Add(new PathElement(laneEntity, targetDelta));
			num -= num3;
			if (!NetUtils.FindConnectedLane(ref laneEntity, ref forward2, ref laneData, ref edgeLaneData, ref ownerData, ref edgeData, ref connectedEdges, ref subLanes))
			{
				break;
			}
			targetDelta = (forward2 ? new float2(1f, 0f) : new float2(0f, 1f));
		}
		CollectionUtils.Reverse(laneBuffer.AsArray());
		num += length * 0.5f;
		if (path.IsCreated)
		{
			while (pathOwner.m_ElementIndex < path.Length)
			{
				PathElement value = path[pathOwner.m_ElementIndex];
				if (!curveData.TryGetComponent(value.m_Target, out var componentData2))
				{
					break;
				}
				float num4 = componentData2.m_Length * math.abs(value.m_TargetDelta.y - value.m_TargetDelta.x);
				if (num4 >= num)
				{
					float t2 = math.select(num / num4, 1f, num4 == 0f);
					t2 = math.lerp(value.m_TargetDelta.x, value.m_TargetDelta.y, t2);
					laneBuffer.Add(new PathElement(value.m_Target, new float2(value.m_TargetDelta.x, t2)));
					num = 0f;
					value.m_TargetDelta.x = t2;
					path[pathOwner.m_ElementIndex] = value;
					break;
				}
				laneEntity2 = value.m_Target;
				if (value.m_TargetDelta.y != value.m_TargetDelta.x)
				{
					forward3 = value.m_TargetDelta.y > value.m_TargetDelta.x;
				}
				else if (value.m_TargetDelta.y == 0f)
				{
					forward3 = false;
				}
				else if (value.m_TargetDelta.y == 1f)
				{
					forward3 = true;
				}
				targetDelta2 = (forward3 ? new float2(value.m_TargetDelta.y, 1f) : new float2(value.m_TargetDelta.y, 0f));
				laneBuffer.Add(in value);
				pathOwner.m_ElementIndex++;
				num -= num4;
			}
		}
		if (num > 0f)
		{
			for (int j = 0; j < 10000; j++)
			{
				float num5 = curveData[laneEntity2].m_Length * math.abs(targetDelta2.y - targetDelta2.x);
				if (num5 >= num)
				{
					float t3 = math.select(num / num5, 1f, num5 == 0f);
					targetDelta2.y = math.lerp(targetDelta2.x, targetDelta2.y, t3);
					laneBuffer.Add(new PathElement(laneEntity2, targetDelta2));
					break;
				}
				laneBuffer.Add(new PathElement(laneEntity2, targetDelta2));
				num -= num5;
				if (!NetUtils.FindConnectedLane(ref laneEntity2, ref forward3, ref laneData, ref edgeLaneData, ref ownerData, ref edgeData, ref connectedEdges, ref subLanes))
				{
					break;
				}
				targetDelta2 = (forward3 ? new float2(0f, 1f) : new float2(1f, 0f));
			}
		}
		CollectionUtils.Reverse(laneBuffer.AsArray());
		if (!(num > 0f) || !(num2 > 0f))
		{
			return;
		}
		laneBuffer.RemoveAt(laneBuffer.Length - 1);
		num += num2;
		targetDelta = (forward2 ? new float2(1f, 0f) : new float2(0f, 1f));
		for (int k = 0; k < 10000; k++)
		{
			float num6 = curveData[laneEntity].m_Length * math.abs(targetDelta.y - targetDelta.x);
			if (num6 >= num)
			{
				float t4 = math.select(num / num6, 1f, num6 == 0f);
				targetDelta.x = math.lerp(targetDelta.y, targetDelta.x, t4);
				laneBuffer.Add(new PathElement(laneEntity, targetDelta));
				break;
			}
			laneBuffer.Add(new PathElement(laneEntity, targetDelta));
			num -= num6;
			if (NetUtils.FindConnectedLane(ref laneEntity, ref forward2, ref laneData, ref edgeLaneData, ref ownerData, ref edgeData, ref connectedEdges, ref subLanes))
			{
				targetDelta = (forward2 ? new float2(1f, 0f) : new float2(0f, 1f));
				continue;
			}
			break;
		}
	}
```

- `public static IsPathfindingPurpose(Game.Citizens.Purpose purpose) : System.Boolean`  

```csharp
public static bool IsPathfindingPurpose(Purpose purpose)
	{
		switch (purpose)
		{
		case Purpose.GoingHome:
		case Purpose.Hospital:
		case Purpose.Safety:
		case Purpose.EmergencyShelter:
		case Purpose.Crime:
		case Purpose.Escape:
		case Purpose.Sightseeing:
		case Purpose.VisitAttractions:
			return true;
		default:
			return false;
		}
	}
```

- `public static ResetPath(Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes) : System.Void`  

```csharp
public static void ResetPath(ref AircraftCurrentLane currentLane, DynamicBuffer<PathElement> path)
	{
		if (currentLane.m_Lane != Entity.Null && path.Length > 0)
		{
			PathElement pathElement = path[0];
			if (pathElement.m_Target == currentLane.m_Lane)
			{
				currentLane.m_CurvePosition.z = pathElement.m_TargetDelta.x;
				return;
			}
		}
		if ((currentLane.m_LaneFlags & (AircraftLaneFlags.Airway | AircraftLaneFlags.Flying)) == (AircraftLaneFlags.Airway | AircraftLaneFlags.Flying))
		{
			currentLane.m_LaneFlags |= AircraftLaneFlags.SkipLane;
		}
		currentLane.m_CurvePosition.z = currentLane.m_CurvePosition.y;
	}
```

- `public static ResetPath(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes) : System.Void`  

```csharp
public static void ResetPath(ref AircraftCurrentLane currentLane, DynamicBuffer<PathElement> path)
	{
		if (currentLane.m_Lane != Entity.Null && path.Length > 0)
		{
			PathElement pathElement = path[0];
			if (pathElement.m_Target == currentLane.m_Lane)
			{
				currentLane.m_CurvePosition.z = pathElement.m_TargetDelta.x;
				return;
			}
		}
		if ((currentLane.m_LaneFlags & (AircraftLaneFlags.Airway | AircraftLaneFlags.Flying)) == (AircraftLaneFlags.Airway | AircraftLaneFlags.Flying))
		{
			currentLane.m_LaneFlags |= AircraftLaneFlags.SkipLane;
		}
		currentLane.m_CurvePosition.z = currentLane.m_CurvePosition.y;
	}
```

- `public static ResetPath(Game.Vehicles.AircraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path) : System.Void`  

```csharp
public static void ResetPath(ref AircraftCurrentLane currentLane, DynamicBuffer<PathElement> path)
	{
		if (currentLane.m_Lane != Entity.Null && path.Length > 0)
		{
			PathElement pathElement = path[0];
			if (pathElement.m_Target == currentLane.m_Lane)
			{
				currentLane.m_CurvePosition.z = pathElement.m_TargetDelta.x;
				return;
			}
		}
		if ((currentLane.m_LaneFlags & (AircraftLaneFlags.Airway | AircraftLaneFlags.Flying)) == (AircraftLaneFlags.Airway | AircraftLaneFlags.Flying))
		{
			currentLane.m_LaneFlags |= AircraftLaneFlags.SkipLane;
		}
		currentLane.m_CurvePosition.z = currentLane.m_CurvePosition.y;
	}
```

- `public static TrimPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathOwner& pathOwner) : System.Void`  

```csharp
public static void TrimPath(DynamicBuffer<PathElement> pathElements, ref PathOwner pathOwner, int startIndex)
	{
		if (startIndex > 0)
		{
			if (startIndex >= pathElements.Length)
			{
				pathElements.Clear();
			}
			else
			{
				pathElements.RemoveRange(0, startIndex);
			}
		}
		pathOwner.m_ElementIndex = 0;
	}
```

- `public static TrimPath(Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> pathElements, Game.Pathfind.PathOwner& pathOwner, System.Int32 startIndex) : System.Void`  

```csharp
public static void TrimPath(DynamicBuffer<PathElement> pathElements, ref PathOwner pathOwner, int startIndex)
	{
		if (startIndex > 0)
		{
			if (startIndex >= pathElements.Length)
			{
				pathElements.Clear();
			}
			else
			{
				pathElements.RemoveRange(0, startIndex);
			}
		}
		pathOwner.m_ElementIndex = 0;
	}
```

- `public static TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add) : System.Void`  

```csharp
public static void TryAddCosts(ref PathfindCosts costs, PathfindCosts add, float distance, bool doIt)
	{
		costs.m_Value = math.select(costs.m_Value, costs.m_Value + add.m_Value * distance, doIt);
	}
```

- `public static TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add, System.Single distance) : System.Void`  

```csharp
public static void TryAddCosts(ref PathfindCosts costs, PathfindCosts add, float distance, bool doIt)
	{
		costs.m_Value = math.select(costs.m_Value, costs.m_Value + add.m_Value * distance, doIt);
	}
```

- `public static TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add, Colossal.Mathematics.Bezier4x3 curve) : System.Void`  

```csharp
public static void TryAddCosts(ref PathfindCosts costs, PathfindCosts add, float distance, bool doIt)
	{
		costs.m_Value = math.select(costs.m_Value, costs.m_Value + add.m_Value * distance, doIt);
	}
```

- `public static TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add, System.Boolean doIt) : System.Void`  

```csharp
public static void TryAddCosts(ref PathfindCosts costs, PathfindCosts add, float distance, bool doIt)
	{
		costs.m_Value = math.select(costs.m_Value, costs.m_Value + add.m_Value * distance, doIt);
	}
```

- `public static TryAddCosts(Game.Pathfind.PathfindCosts& costs, Game.Pathfind.PathfindCosts add, System.Single distance, System.Boolean doIt) : System.Void`  

```csharp
public static void TryAddCosts(ref PathfindCosts costs, PathfindCosts add, float distance, bool doIt)
	{
		costs.m_Value = math.select(costs.m_Value, costs.m_Value + add.m_Value * distance, doIt);
	}
```

- `public static TryAppendPath(Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes) : System.Boolean`  

```csharp
public static bool TryAppendPath(ref TrainCurrentLane currentLane, DynamicBuffer<TrainNavigationLane> navigationLanes, DynamicBuffer<PathElement> path, DynamicBuffer<PathElement> appendPath)
	{
		NativeParallelHashMap<Entity, AppendPathValue> nativeParallelHashMap = new NativeParallelHashMap<Entity, AppendPathValue>(navigationLanes.Length + path.Length + 1, Allocator.Temp);
		if (currentLane.m_Front.m_Lane != Entity.Null && (navigationLanes.Length == 0 || (navigationLanes[0].m_Flags & TrainLaneFlags.Reserved) == 0))
		{
			nativeParallelHashMap.TryAdd(currentLane.m_Front.m_Lane, new AppendPathValue
			{
				m_Index = 0,
				m_TargetDelta = currentLane.m_Front.m_CurvePosition.z
			});
		}
		for (int i = 1; i <= navigationLanes.Length; i++)
		{
			if (navigationLanes.Length == i || (navigationLanes[i].m_Flags & TrainLaneFlags.Reserved) == 0)
			{
				TrainNavigationLane trainNavigationLane = navigationLanes[i - 1];
				float targetDelta = math.select(trainNavigationLane.m_CurvePosition.x, trainNavigationLane.m_CurvePosition.y, (trainNavigationLane.m_Flags & TrainLaneFlags.Reserved) != 0);
				nativeParallelHashMap.TryAdd(trainNavigationLane.m_Lane, new AppendPathValue
				{
					m_Index = i,
					m_TargetDelta = targetDelta
				});
			}
		}
		int num = navigationLanes.Length + 1;
		for (int j = 0; j < path.Length; j++)
		{
			PathElement pathElement = path[j];
			nativeParallelHashMap.TryAdd(pathElement.m_Target, new AppendPathValue
			{
				m_Index = num + j,
				m_TargetDelta = pathElement.m_TargetDelta.x
			});
		}
		for (int k = 0; appendPath.Length > k; k++)
		{
			PathElement elem = appendPath[k];
			if (!nativeParallelHashMap.TryGetValue(elem.m_Target, out var item))
			{
				continue;
			}
			if (item.m_Index == 0)
			{
				currentLane.m_Front.m_CurvePosition.w = item.m_TargetDelta;
				navigationLanes.Clear();
				path.Clear();
			}
			else if (item.m_Index <= navigationLanes.Length)
			{
				TrainNavigationLane value = navigationLanes[item.m_Index - 1];
				value.m_CurvePosition.y = item.m_TargetDelta;
				navigationLanes[item.m_Index - 1] = value;
				if (item.m_Index < navigationLanes.Length)
				{
					navigationLanes.RemoveRange(item.m_Index, navigationLanes.Length - item.m_Index);
				}
				path.Clear();
			}
			else if (item.m_Index < num + path.Length)
			{
				path.RemoveRange(item.m_Index - num, num + path.Length - item.m_Index);
			}
			path.EnsureCapacity(path.Length + appendPath.Length - k);
			elem.m_TargetDelta.x = item.m_TargetDelta;
			path.Add(elem);
			for (int l = k + 1; l < appendPath.Length; l++)
			{
				path.Add(appendPath[l]);
			}
			nativeParallelHashMap.Dispose();
			return true;
		}
		nativeParallelHashMap.Dispose();
		return false;
	}
```

- `public static TryAppendPath(Game.Vehicles.CarCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.CarNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, System.Int32& appendedCount) : System.Boolean`  

```csharp
public static bool TryAppendPath(ref TrainCurrentLane currentLane, DynamicBuffer<TrainNavigationLane> navigationLanes, DynamicBuffer<PathElement> path, DynamicBuffer<PathElement> appendPath)
	{
		NativeParallelHashMap<Entity, AppendPathValue> nativeParallelHashMap = new NativeParallelHashMap<Entity, AppendPathValue>(navigationLanes.Length + path.Length + 1, Allocator.Temp);
		if (currentLane.m_Front.m_Lane != Entity.Null && (navigationLanes.Length == 0 || (navigationLanes[0].m_Flags & TrainLaneFlags.Reserved) == 0))
		{
			nativeParallelHashMap.TryAdd(currentLane.m_Front.m_Lane, new AppendPathValue
			{
				m_Index = 0,
				m_TargetDelta = currentLane.m_Front.m_CurvePosition.z
			});
		}
		for (int i = 1; i <= navigationLanes.Length; i++)
		{
			if (navigationLanes.Length == i || (navigationLanes[i].m_Flags & TrainLaneFlags.Reserved) == 0)
			{
				TrainNavigationLane trainNavigationLane = navigationLanes[i - 1];
				float targetDelta = math.select(trainNavigationLane.m_CurvePosition.x, trainNavigationLane.m_CurvePosition.y, (trainNavigationLane.m_Flags & TrainLaneFlags.Reserved) != 0);
				nativeParallelHashMap.TryAdd(trainNavigationLane.m_Lane, new AppendPathValue
				{
					m_Index = i,
					m_TargetDelta = targetDelta
				});
			}
		}
		int num = navigationLanes.Length + 1;
		for (int j = 0; j < path.Length; j++)
		{
			PathElement pathElement = path[j];
			nativeParallelHashMap.TryAdd(pathElement.m_Target, new AppendPathValue
			{
				m_Index = num + j,
				m_TargetDelta = pathElement.m_TargetDelta.x
			});
		}
		for (int k = 0; appendPath.Length > k; k++)
		{
			PathElement elem = appendPath[k];
			if (!nativeParallelHashMap.TryGetValue(elem.m_Target, out var item))
			{
				continue;
			}
			if (item.m_Index == 0)
			{
				currentLane.m_Front.m_CurvePosition.w = item.m_TargetDelta;
				navigationLanes.Clear();
				path.Clear();
			}
			else if (item.m_Index <= navigationLanes.Length)
			{
				TrainNavigationLane value = navigationLanes[item.m_Index - 1];
				value.m_CurvePosition.y = item.m_TargetDelta;
				navigationLanes[item.m_Index - 1] = value;
				if (item.m_Index < navigationLanes.Length)
				{
					navigationLanes.RemoveRange(item.m_Index, navigationLanes.Length - item.m_Index);
				}
				path.Clear();
			}
			else if (item.m_Index < num + path.Length)
			{
				path.RemoveRange(item.m_Index - num, num + path.Length - item.m_Index);
			}
			path.EnsureCapacity(path.Length + appendPath.Length - k);
			elem.m_TargetDelta.x = item.m_TargetDelta;
			path.Add(elem);
			for (int l = k + 1; l < appendPath.Length; l++)
			{
				path.Add(appendPath[l]);
			}
			nativeParallelHashMap.Dispose();
			return true;
		}
		nativeParallelHashMap.Dispose();
		return false;
	}
```

- `public static TryAppendPath(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes) : System.Boolean`  

```csharp
public static bool TryAppendPath(ref TrainCurrentLane currentLane, DynamicBuffer<TrainNavigationLane> navigationLanes, DynamicBuffer<PathElement> path, DynamicBuffer<PathElement> appendPath)
	{
		NativeParallelHashMap<Entity, AppendPathValue> nativeParallelHashMap = new NativeParallelHashMap<Entity, AppendPathValue>(navigationLanes.Length + path.Length + 1, Allocator.Temp);
		if (currentLane.m_Front.m_Lane != Entity.Null && (navigationLanes.Length == 0 || (navigationLanes[0].m_Flags & TrainLaneFlags.Reserved) == 0))
		{
			nativeParallelHashMap.TryAdd(currentLane.m_Front.m_Lane, new AppendPathValue
			{
				m_Index = 0,
				m_TargetDelta = currentLane.m_Front.m_CurvePosition.z
			});
		}
		for (int i = 1; i <= navigationLanes.Length; i++)
		{
			if (navigationLanes.Length == i || (navigationLanes[i].m_Flags & TrainLaneFlags.Reserved) == 0)
			{
				TrainNavigationLane trainNavigationLane = navigationLanes[i - 1];
				float targetDelta = math.select(trainNavigationLane.m_CurvePosition.x, trainNavigationLane.m_CurvePosition.y, (trainNavigationLane.m_Flags & TrainLaneFlags.Reserved) != 0);
				nativeParallelHashMap.TryAdd(trainNavigationLane.m_Lane, new AppendPathValue
				{
					m_Index = i,
					m_TargetDelta = targetDelta
				});
			}
		}
		int num = navigationLanes.Length + 1;
		for (int j = 0; j < path.Length; j++)
		{
			PathElement pathElement = path[j];
			nativeParallelHashMap.TryAdd(pathElement.m_Target, new AppendPathValue
			{
				m_Index = num + j,
				m_TargetDelta = pathElement.m_TargetDelta.x
			});
		}
		for (int k = 0; appendPath.Length > k; k++)
		{
			PathElement elem = appendPath[k];
			if (!nativeParallelHashMap.TryGetValue(elem.m_Target, out var item))
			{
				continue;
			}
			if (item.m_Index == 0)
			{
				currentLane.m_Front.m_CurvePosition.w = item.m_TargetDelta;
				navigationLanes.Clear();
				path.Clear();
			}
			else if (item.m_Index <= navigationLanes.Length)
			{
				TrainNavigationLane value = navigationLanes[item.m_Index - 1];
				value.m_CurvePosition.y = item.m_TargetDelta;
				navigationLanes[item.m_Index - 1] = value;
				if (item.m_Index < navigationLanes.Length)
				{
					navigationLanes.RemoveRange(item.m_Index, navigationLanes.Length - item.m_Index);
				}
				path.Clear();
			}
			else if (item.m_Index < num + path.Length)
			{
				path.RemoveRange(item.m_Index - num, num + path.Length - item.m_Index);
			}
			path.EnsureCapacity(path.Length + appendPath.Length - k);
			elem.m_TargetDelta.x = item.m_TargetDelta;
			path.Add(elem);
			for (int l = k + 1; l < appendPath.Length; l++)
			{
				path.Add(appendPath[l]);
			}
			nativeParallelHashMap.Dispose();
			return true;
		}
		nativeParallelHashMap.Dispose();
		return false;
	}
```

- `public static TryAppendPath(Game.Vehicles.WatercraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.WatercraftNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath, Unity.Entities.ComponentLookup<Game.Net.SlaveLane> slaveLaneData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, System.Int32& appendedCount) : System.Boolean`  

```csharp
public static bool TryAppendPath(ref TrainCurrentLane currentLane, DynamicBuffer<TrainNavigationLane> navigationLanes, DynamicBuffer<PathElement> path, DynamicBuffer<PathElement> appendPath)
	{
		NativeParallelHashMap<Entity, AppendPathValue> nativeParallelHashMap = new NativeParallelHashMap<Entity, AppendPathValue>(navigationLanes.Length + path.Length + 1, Allocator.Temp);
		if (currentLane.m_Front.m_Lane != Entity.Null && (navigationLanes.Length == 0 || (navigationLanes[0].m_Flags & TrainLaneFlags.Reserved) == 0))
		{
			nativeParallelHashMap.TryAdd(currentLane.m_Front.m_Lane, new AppendPathValue
			{
				m_Index = 0,
				m_TargetDelta = currentLane.m_Front.m_CurvePosition.z
			});
		}
		for (int i = 1; i <= navigationLanes.Length; i++)
		{
			if (navigationLanes.Length == i || (navigationLanes[i].m_Flags & TrainLaneFlags.Reserved) == 0)
			{
				TrainNavigationLane trainNavigationLane = navigationLanes[i - 1];
				float targetDelta = math.select(trainNavigationLane.m_CurvePosition.x, trainNavigationLane.m_CurvePosition.y, (trainNavigationLane.m_Flags & TrainLaneFlags.Reserved) != 0);
				nativeParallelHashMap.TryAdd(trainNavigationLane.m_Lane, new AppendPathValue
				{
					m_Index = i,
					m_TargetDelta = targetDelta
				});
			}
		}
		int num = navigationLanes.Length + 1;
		for (int j = 0; j < path.Length; j++)
		{
			PathElement pathElement = path[j];
			nativeParallelHashMap.TryAdd(pathElement.m_Target, new AppendPathValue
			{
				m_Index = num + j,
				m_TargetDelta = pathElement.m_TargetDelta.x
			});
		}
		for (int k = 0; appendPath.Length > k; k++)
		{
			PathElement elem = appendPath[k];
			if (!nativeParallelHashMap.TryGetValue(elem.m_Target, out var item))
			{
				continue;
			}
			if (item.m_Index == 0)
			{
				currentLane.m_Front.m_CurvePosition.w = item.m_TargetDelta;
				navigationLanes.Clear();
				path.Clear();
			}
			else if (item.m_Index <= navigationLanes.Length)
			{
				TrainNavigationLane value = navigationLanes[item.m_Index - 1];
				value.m_CurvePosition.y = item.m_TargetDelta;
				navigationLanes[item.m_Index - 1] = value;
				if (item.m_Index < navigationLanes.Length)
				{
					navigationLanes.RemoveRange(item.m_Index, navigationLanes.Length - item.m_Index);
				}
				path.Clear();
			}
			else if (item.m_Index < num + path.Length)
			{
				path.RemoveRange(item.m_Index - num, num + path.Length - item.m_Index);
			}
			path.EnsureCapacity(path.Length + appendPath.Length - k);
			elem.m_TargetDelta.x = item.m_TargetDelta;
			path.Add(elem);
			for (int l = k + 1; l < appendPath.Length; l++)
			{
				path.Add(appendPath[l]);
			}
			nativeParallelHashMap.Dispose();
			return true;
		}
		nativeParallelHashMap.Dispose();
		return false;
	}
```

- `public static TryAppendPath(Game.Vehicles.AircraftCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.AircraftNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath) : System.Boolean`  

```csharp
public static bool TryAppendPath(ref TrainCurrentLane currentLane, DynamicBuffer<TrainNavigationLane> navigationLanes, DynamicBuffer<PathElement> path, DynamicBuffer<PathElement> appendPath)
	{
		NativeParallelHashMap<Entity, AppendPathValue> nativeParallelHashMap = new NativeParallelHashMap<Entity, AppendPathValue>(navigationLanes.Length + path.Length + 1, Allocator.Temp);
		if (currentLane.m_Front.m_Lane != Entity.Null && (navigationLanes.Length == 0 || (navigationLanes[0].m_Flags & TrainLaneFlags.Reserved) == 0))
		{
			nativeParallelHashMap.TryAdd(currentLane.m_Front.m_Lane, new AppendPathValue
			{
				m_Index = 0,
				m_TargetDelta = currentLane.m_Front.m_CurvePosition.z
			});
		}
		for (int i = 1; i <= navigationLanes.Length; i++)
		{
			if (navigationLanes.Length == i || (navigationLanes[i].m_Flags & TrainLaneFlags.Reserved) == 0)
			{
				TrainNavigationLane trainNavigationLane = navigationLanes[i - 1];
				float targetDelta = math.select(trainNavigationLane.m_CurvePosition.x, trainNavigationLane.m_CurvePosition.y, (trainNavigationLane.m_Flags & TrainLaneFlags.Reserved) != 0);
				nativeParallelHashMap.TryAdd(trainNavigationLane.m_Lane, new AppendPathValue
				{
					m_Index = i,
					m_TargetDelta = targetDelta
				});
			}
		}
		int num = navigationLanes.Length + 1;
		for (int j = 0; j < path.Length; j++)
		{
			PathElement pathElement = path[j];
			nativeParallelHashMap.TryAdd(pathElement.m_Target, new AppendPathValue
			{
				m_Index = num + j,
				m_TargetDelta = pathElement.m_TargetDelta.x
			});
		}
		for (int k = 0; appendPath.Length > k; k++)
		{
			PathElement elem = appendPath[k];
			if (!nativeParallelHashMap.TryGetValue(elem.m_Target, out var item))
			{
				continue;
			}
			if (item.m_Index == 0)
			{
				currentLane.m_Front.m_CurvePosition.w = item.m_TargetDelta;
				navigationLanes.Clear();
				path.Clear();
			}
			else if (item.m_Index <= navigationLanes.Length)
			{
				TrainNavigationLane value = navigationLanes[item.m_Index - 1];
				value.m_CurvePosition.y = item.m_TargetDelta;
				navigationLanes[item.m_Index - 1] = value;
				if (item.m_Index < navigationLanes.Length)
				{
					navigationLanes.RemoveRange(item.m_Index, navigationLanes.Length - item.m_Index);
				}
				path.Clear();
			}
			else if (item.m_Index < num + path.Length)
			{
				path.RemoveRange(item.m_Index - num, num + path.Length - item.m_Index);
			}
			path.EnsureCapacity(path.Length + appendPath.Length - k);
			elem.m_TargetDelta.x = item.m_TargetDelta;
			path.Add(elem);
			for (int l = k + 1; l < appendPath.Length; l++)
			{
				path.Add(appendPath[l]);
			}
			nativeParallelHashMap.Dispose();
			return true;
		}
		nativeParallelHashMap.Dispose();
		return false;
	}
```

- `public static TryAppendPath(Game.Vehicles.TrainCurrentLane& currentLane, Unity.Entities.DynamicBuffer<Game.Vehicles.TrainNavigationLane> navigationLanes, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> appendPath) : System.Boolean`  

```csharp
public static bool TryAppendPath(ref TrainCurrentLane currentLane, DynamicBuffer<TrainNavigationLane> navigationLanes, DynamicBuffer<PathElement> path, DynamicBuffer<PathElement> appendPath)
	{
		NativeParallelHashMap<Entity, AppendPathValue> nativeParallelHashMap = new NativeParallelHashMap<Entity, AppendPathValue>(navigationLanes.Length + path.Length + 1, Allocator.Temp);
		if (currentLane.m_Front.m_Lane != Entity.Null && (navigationLanes.Length == 0 || (navigationLanes[0].m_Flags & TrainLaneFlags.Reserved) == 0))
		{
			nativeParallelHashMap.TryAdd(currentLane.m_Front.m_Lane, new AppendPathValue
			{
				m_Index = 0,
				m_TargetDelta = currentLane.m_Front.m_CurvePosition.z
			});
		}
		for (int i = 1; i <= navigationLanes.Length; i++)
		{
			if (navigationLanes.Length == i || (navigationLanes[i].m_Flags & TrainLaneFlags.Reserved) == 0)
			{
				TrainNavigationLane trainNavigationLane = navigationLanes[i - 1];
				float targetDelta = math.select(trainNavigationLane.m_CurvePosition.x, trainNavigationLane.m_CurvePosition.y, (trainNavigationLane.m_Flags & TrainLaneFlags.Reserved) != 0);
				nativeParallelHashMap.TryAdd(trainNavigationLane.m_Lane, new AppendPathValue
				{
					m_Index = i,
					m_TargetDelta = targetDelta
				});
			}
		}
		int num = navigationLanes.Length + 1;
		for (int j = 0; j < path.Length; j++)
		{
			PathElement pathElement = path[j];
			nativeParallelHashMap.TryAdd(pathElement.m_Target, new AppendPathValue
			{
				m_Index = num + j,
				m_TargetDelta = pathElement.m_TargetDelta.x
			});
		}
		for (int k = 0; appendPath.Length > k; k++)
		{
			PathElement elem = appendPath[k];
			if (!nativeParallelHashMap.TryGetValue(elem.m_Target, out var item))
			{
				continue;
			}
			if (item.m_Index == 0)
			{
				currentLane.m_Front.m_CurvePosition.w = item.m_TargetDelta;
				navigationLanes.Clear();
				path.Clear();
			}
			else if (item.m_Index <= navigationLanes.Length)
			{
				TrainNavigationLane value = navigationLanes[item.m_Index - 1];
				value.m_CurvePosition.y = item.m_TargetDelta;
				navigationLanes[item.m_Index - 1] = value;
				if (item.m_Index < navigationLanes.Length)
				{
					navigationLanes.RemoveRange(item.m_Index, navigationLanes.Length - item.m_Index);
				}
				path.Clear();
			}
			else if (item.m_Index < num + path.Length)
			{
				path.RemoveRange(item.m_Index - num, num + path.Length - item.m_Index);
			}
			path.EnsureCapacity(path.Length + appendPath.Length - k);
			elem.m_TargetDelta.x = item.m_TargetDelta;
			path.Add(elem);
			for (int l = k + 1; l < appendPath.Length; l++)
			{
				path.Add(appendPath[l]);
			}
			nativeParallelHashMap.Dispose();
			return true;
		}
		nativeParallelHashMap.Dispose();
		return false;
	}
```

- `public static UpdateOwnedVehicleMethods(Unity.Entities.Entity householdEntity, Unity.Entities.BufferLookup`1[[Game.Vehicles.OwnedVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownedVehicleBuffs, Game.Pathfind.PathfindParameters& parameters, Game.Pathfind.SetupQueueTarget& origin, Game.Pathfind.SetupQueueTarget& destination) : System.Void`  

```csharp
public static void UpdateOwnedVehicleMethods(Entity householdEntity, ref BufferLookup<OwnedVehicle> ownedVehicleBuffs, ref PathfindParameters parameters, ref SetupQueueTarget origin, ref SetupQueueTarget destination)
	{
		if (ownedVehicleBuffs.TryGetBuffer(householdEntity, out var bufferData) && bufferData.Length != 0)
		{
			parameters.m_Methods |= PathMethod.Road | PathMethod.Parking | PathMethod.MediumRoad;
			parameters.m_ParkingSize = float.MinValue;
			parameters.m_IgnoredRules |= RuleFlags.ForbidCombustionEngines | RuleFlags.ForbidHeavyTraffic | RuleFlags.ForbidSlowTraffic;
			origin.m_Methods |= PathMethod.Road | PathMethod.MediumRoad;
			origin.m_RoadTypes |= RoadTypes.Car;
			destination.m_Methods |= PathMethod.Road | PathMethod.MediumRoad;
			destination.m_RoadTypes |= RoadTypes.Car;
		}
	}
```


## Nested types

- `Game.Pathfind.PathUtils+AppendPathValue`  

