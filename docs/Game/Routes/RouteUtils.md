# Game.Routes.RouteUtils

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class static public  

**Base:** `System.Object`  

## Fields

- `public static const System.Single WAYPOINT_CONNECTION_DISTANCE`  
- `public static const System.Single ROUTE_VISIBLE_THROUGH_DISTANCE`  
- `public static const System.Single TRANSPORT_DAY_START_TIME`  
- `public static const System.Single TRANSPORT_DAY_END_TIME`  
- `public static const System.Single DEFAULT_TRAVEL_TIME`  
- `public static const System.Single TAXI_DISTANCE_FEE`  

## Methods

- `public static ApplyModifier(System.Single& value, Unity.Entities.DynamicBuffer<Game.Routes.RouteModifier> modifiers, Game.Routes.RouteModifierType type) : System.Void`  
- `public static CalculateBounds(Game.Routes.Position waypointPosition, Game.Prefabs.RouteData routeData) : Colossal.Mathematics.Bounds3`  
- `public static CalculateBounds(Game.Routes.CurveElement curveElement, Game.Prefabs.RouteData routeData) : Colossal.Mathematics.Bounds3`  
- `public static CalculateDepartureFrame(Game.Routes.TransportLine transportLine, Game.Prefabs.TransportLineData prefabLineData, Unity.Entities.DynamicBuffer<Game.Routes.RouteModifier> routeModifiers, System.Single targetStopTime, System.UInt32 lastDepartureFrame, System.UInt32 simulationFrame) : System.UInt32`  
- `public static CheckOption(Game.Routes.Route route, Game.Routes.RouteOption option) : System.Boolean`  
- `public static CheckVehicleModel(Game.Routes.VehicleModel vehicleModel, Game.Prefabs.PrefabRef prefabRef, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData) : System.Boolean`  
- `public static GetBoardingVehicle(Unity.Entities.Entity currentLane, Unity.Entities.Entity currentWaypoint, Unity.Entities.Entity targetWaypoint, System.UInt32 minDeparture, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Routes.Connected, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedData, Unity.Entities.ComponentLookup`1[[Game.Routes.BoardingVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& boardingVehicleData, Unity.Entities.ComponentLookup`1[[Game.Routes.CurrentRoute, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentRouteData, Unity.Entities.ComponentLookup`1[[Game.Routes.AccessLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& accessLaneData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.PublicTransport, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& publicTransportData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Taxi, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& taxiData, Unity.Entities.BufferLookup`1[[Game.Routes.ConnectedRoute, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedRoutes, Unity.Entities.Entity& vehicle, System.Boolean& testing, System.Boolean& obsolete) : System.Boolean`  
- `public static GetMaxTaxiCount(Game.Routes.WaitingPassengers waitingPassengers) : System.Int32`  
- `public static GetMinWaypointDistance(Game.Prefabs.RouteData routeData) : System.Single`  
- `public static GetPathMethods(Game.Prefabs.RouteConnectionType routeConnectionType, Game.Routes.RouteType routeType, Game.Net.TrackTypes trackTypes, Game.Net.RoadTypes roadTypes, Game.Vehicles.SizeClass sizeClass) : Game.Pathfind.PathMethod`  
- `public static GetPublicTransportMethods(System.Single timeOfDay, System.Single predictionOffset = 0,020833334) : Game.Pathfind.PathMethod`  
- `public static GetPublicTransportMethods(Game.Creatures.Resident resident, System.Single timeOfDay, System.Single predictionOffset = 0,020833334) : Game.Pathfind.PathMethod`  
- `public static GetStopDuration(Game.Prefabs.TransportLineData prefabLineData, Game.Routes.TransportStop transportStop) : System.Single`  
- `public static GetTaxiMethods(Game.Creatures.Resident resident) : Game.Pathfind.PathMethod`  
- `public static HasOption(Game.Prefabs.RouteOptionData optionData, Game.Routes.RouteOption option) : System.Boolean`  
- `private static OffsetPathTarget_AreaLane(Unity.Mathematics.Random& random, System.Single distance, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.ConnectionLane> connectionLaneData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, Unity.Entities.BufferLookup<Game.Areas.Node> areaNodes, Unity.Entities.BufferLookup<Game.Areas.Triangle> areaTriangles) : System.Void`  
- `private static OffsetPathTarget_EdgeLane(Unity.Mathematics.Random& random, System.Single distance, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes) : System.Void`  
- `public static ShouldExitVehicle(Unity.Entities.Entity nextLane, Unity.Entities.Entity targetWaypoint, Unity.Entities.Entity currentVehicle, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Routes.Connected, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedData, Unity.Entities.ComponentLookup`1[[Game.Routes.BoardingVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& boardingVehicleData, Unity.Entities.ComponentLookup`1[[Game.Routes.CurrentRoute, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentRouteData, Unity.Entities.ComponentLookup`1[[Game.Routes.AccessLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& accessLaneData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.PublicTransport, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& publicTransportData, Unity.Entities.BufferLookup`1[[Game.Routes.ConnectedRoute, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedRoutes, System.Boolean testing, System.Boolean& obsolete) : System.Boolean`  
- `public static StripTransportSegments<TTransportEstimateBuffer>(Unity.Mathematics.Random& random, System.Int32 length, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Routes.Connected> connectedData, Unity.Entities.ComponentLookup<Game.Routes.BoardingVehicle> boardingVehicleData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.ConnectionLane> connectionLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefData, Unity.Entities.ComponentLookup<Game.Prefabs.TransportStopData> prefabTransportStopData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, Unity.Entities.BufferLookup<Game.Areas.Node> areaNodes, Unity.Entities.BufferLookup<Game.Areas.Triangle> areaTriangles, TTransportEstimateBuffer transportEstimateBuffer) : System.Void`  
- `public static UpdateAverageTravelTime(System.Single oldTravelTime, System.UInt32 departureFrame, System.UInt32 arrivalFrame) : System.Single`  

## Nested types

- `Game.Routes.RouteUtils+ITransportEstimateBuffer`  

