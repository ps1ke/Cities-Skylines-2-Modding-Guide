# Game.Routes.RouteUtils

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class RouteUtils
{
    public static const System.Single WAYPOINT_CONNECTION_DISTANCE;
    public static const System.Single ROUTE_VISIBLE_THROUGH_DISTANCE;
    public static const System.Single TRANSPORT_DAY_START_TIME;
    public static const System.Single TRANSPORT_DAY_END_TIME;
    public static const System.Single DEFAULT_TRAVEL_TIME;
    public static const System.Single TAXI_DISTANCE_FEE;

    public static System.Void ApplyModifier(System.Single& value, Unity.Entities.DynamicBuffer<Game.Routes.RouteModifier> modifiers, Game.Routes.RouteModifierType type);
    public static Colossal.Mathematics.Bounds3 CalculateBounds(Game.Routes.Position waypointPosition, Game.Prefabs.RouteData routeData);
    public static Colossal.Mathematics.Bounds3 CalculateBounds(Game.Routes.CurveElement curveElement, Game.Prefabs.RouteData routeData);
    public static System.UInt32 CalculateDepartureFrame(Game.Routes.TransportLine transportLine, Game.Prefabs.TransportLineData prefabLineData, Unity.Entities.DynamicBuffer<Game.Routes.RouteModifier> routeModifiers, System.Single targetStopTime, System.UInt32 lastDepartureFrame, System.UInt32 simulationFrame);
    public static System.Boolean CheckOption(Game.Routes.Route route, Game.Routes.RouteOption option);
    public static System.Boolean CheckVehicleModel(Game.Routes.VehicleModel vehicleModel, Game.Prefabs.PrefabRef prefabRef, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData);
    public static System.Boolean GetBoardingVehicle(Unity.Entities.Entity currentLane, Unity.Entities.Entity currentWaypoint, Unity.Entities.Entity targetWaypoint, System.UInt32 minDeparture, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Routes.Connected, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedData, Unity.Entities.ComponentLookup`1[[Game.Routes.BoardingVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& boardingVehicleData, Unity.Entities.ComponentLookup`1[[Game.Routes.CurrentRoute, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentRouteData, Unity.Entities.ComponentLookup`1[[Game.Routes.AccessLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& accessLaneData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.PublicTransport, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& publicTransportData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Taxi, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& taxiData, Unity.Entities.BufferLookup`1[[Game.Routes.ConnectedRoute, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedRoutes, Unity.Entities.Entity& vehicle, System.Boolean& testing, System.Boolean& obsolete);
    public static System.Int32 GetMaxTaxiCount(Game.Routes.WaitingPassengers waitingPassengers);
    public static System.Single GetMinWaypointDistance(Game.Prefabs.RouteData routeData);
    public static Game.Pathfind.PathMethod GetPathMethods(Game.Prefabs.RouteConnectionType routeConnectionType, Game.Routes.RouteType routeType, Game.Net.TrackTypes trackTypes, Game.Net.RoadTypes roadTypes, Game.Vehicles.SizeClass sizeClass);
    public static Game.Pathfind.PathMethod GetPublicTransportMethods(System.Single timeOfDay, System.Single predictionOffset);
    public static Game.Pathfind.PathMethod GetPublicTransportMethods(Game.Creatures.Resident resident, System.Single timeOfDay, System.Single predictionOffset);
    public static System.Single GetStopDuration(Game.Prefabs.TransportLineData prefabLineData, Game.Routes.TransportStop transportStop);
    public static Game.Pathfind.PathMethod GetTaxiMethods(Game.Creatures.Resident resident);
    public static System.Boolean HasOption(Game.Prefabs.RouteOptionData optionData, Game.Routes.RouteOption option);
    private static System.Void OffsetPathTarget_AreaLane(Unity.Mathematics.Random& random, System.Single distance, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.ConnectionLane> connectionLaneData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, Unity.Entities.BufferLookup<Game.Areas.Node> areaNodes, Unity.Entities.BufferLookup<Game.Areas.Triangle> areaTriangles);
    private static System.Void OffsetPathTarget_EdgeLane(Unity.Mathematics.Random& random, System.Single distance, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes);
    public static System.Boolean ShouldExitVehicle(Unity.Entities.Entity nextLane, Unity.Entities.Entity targetWaypoint, Unity.Entities.Entity currentVehicle, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Routes.Connected, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedData, Unity.Entities.ComponentLookup`1[[Game.Routes.BoardingVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& boardingVehicleData, Unity.Entities.ComponentLookup`1[[Game.Routes.CurrentRoute, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentRouteData, Unity.Entities.ComponentLookup`1[[Game.Routes.AccessLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& accessLaneData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.PublicTransport, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& publicTransportData, Unity.Entities.BufferLookup`1[[Game.Routes.ConnectedRoute, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedRoutes, System.Boolean testing, System.Boolean& obsolete);
    public static System.Void StripTransportSegments<TTransportEstimateBuffer>(Unity.Mathematics.Random& random, System.Int32 length, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Routes.Connected> connectedData, Unity.Entities.ComponentLookup<Game.Routes.BoardingVehicle> boardingVehicleData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.ConnectionLane> connectionLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefData, Unity.Entities.ComponentLookup<Game.Prefabs.TransportStopData> prefabTransportStopData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, Unity.Entities.BufferLookup<Game.Areas.Node> areaNodes, Unity.Entities.BufferLookup<Game.Areas.Triangle> areaTriangles, TTransportEstimateBuffer transportEstimateBuffer);
    public static System.Single UpdateAverageTravelTime(System.Single oldTravelTime, System.UInt32 departureFrame, System.UInt32 arrivalFrame);
}
```


## Fields

- `public static const System.Single WAYPOINT_CONNECTION_DISTANCE`  

```csharp
public static const System.Single WAYPOINT_CONNECTION_DISTANCE;
```

- `public static const System.Single ROUTE_VISIBLE_THROUGH_DISTANCE`  

```csharp
public static const System.Single ROUTE_VISIBLE_THROUGH_DISTANCE;
```

- `public static const System.Single TRANSPORT_DAY_START_TIME`  

```csharp
public static const System.Single TRANSPORT_DAY_START_TIME;
```

- `public static const System.Single TRANSPORT_DAY_END_TIME`  

```csharp
public static const System.Single TRANSPORT_DAY_END_TIME;
```

- `public static const System.Single DEFAULT_TRAVEL_TIME`  

```csharp
public static const System.Single DEFAULT_TRAVEL_TIME;
```

- `public static const System.Single TAXI_DISTANCE_FEE`  

```csharp
public static const System.Single TAXI_DISTANCE_FEE;
```


## Methods

- `public static ApplyModifier(System.Single& value, Unity.Entities.DynamicBuffer<Game.Routes.RouteModifier> modifiers, Game.Routes.RouteModifierType type) : System.Void`  

```csharp
public static void ApplyModifier(ref float value, DynamicBuffer<RouteModifier> modifiers, RouteModifierType type)
	{
		if (modifiers.Length > (int)type)
		{
			float2 delta = modifiers[(int)type].m_Delta;
			value += delta.x;
			value += value * delta.y;
		}
	}
```

- `public static CalculateBounds(Game.Routes.Position waypointPosition, Game.Prefabs.RouteData routeData) : Colossal.Mathematics.Bounds3`  

```csharp
public static Bounds3 CalculateBounds(CurveElement curveElement, RouteData routeData)
	{
		float snapDistance = routeData.m_SnapDistance;
		return MathUtils.Expand(MathUtils.Bounds(curveElement.m_Curve), snapDistance);
	}
```

- `public static CalculateBounds(Game.Routes.CurveElement curveElement, Game.Prefabs.RouteData routeData) : Colossal.Mathematics.Bounds3`  

```csharp
public static Bounds3 CalculateBounds(CurveElement curveElement, RouteData routeData)
	{
		float snapDistance = routeData.m_SnapDistance;
		return MathUtils.Expand(MathUtils.Bounds(curveElement.m_Curve), snapDistance);
	}
```

- `public static CalculateDepartureFrame(Game.Routes.TransportLine transportLine, Game.Prefabs.TransportLineData prefabLineData, Unity.Entities.DynamicBuffer<Game.Routes.RouteModifier> routeModifiers, System.Single targetStopTime, System.UInt32 lastDepartureFrame, System.UInt32 simulationFrame) : System.UInt32`  

```csharp
public static uint CalculateDepartureFrame(TransportLine transportLine, TransportLineData prefabLineData, DynamicBuffer<RouteModifier> routeModifiers, float targetStopTime, uint lastDepartureFrame, uint simulationFrame)
	{
		float num = (float)(simulationFrame - lastDepartureFrame) / 60f;
		if (num >= 0f)
		{
			float value = prefabLineData.m_DefaultVehicleInterval;
			ApplyModifier(ref value, routeModifiers, RouteModifierType.VehicleInterval);
			float vehicleInterval = transportLine.m_VehicleInterval;
			float unbunchingFactor = transportLine.m_UnbunchingFactor;
			float num2 = math.min(value, 2f * vehicleInterval * vehicleInterval / (num + vehicleInterval) - vehicleInterval) * unbunchingFactor;
			num2 = math.max(num2 + targetStopTime, 1f);
			return simulationFrame + (uint)(num2 * 60f);
		}
		return simulationFrame;
	}
```

- `public static CheckOption(Game.Routes.Route route, Game.Routes.RouteOption option) : System.Boolean`  

```csharp
public static bool CheckOption(Route route, RouteOption option)
	{
		return (route.m_OptionMask & (uint)(1 << (int)option)) != 0;
	}
```

- `public static CheckVehicleModel(Game.Routes.VehicleModel vehicleModel, Game.Prefabs.PrefabRef prefabRef, Unity.Entities.DynamicBuffer<Game.Vehicles.LayoutElement> layout, Unity.Entities.ComponentLookup`1[[Game.Prefabs.PrefabRef, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& prefabRefData) : System.Boolean`  

```csharp
public static bool CheckVehicleModel(VehicleModel vehicleModel, PrefabRef prefabRef, DynamicBuffer<LayoutElement> layout, ref ComponentLookup<PrefabRef> prefabRefData)
	{
		if (vehicleModel.m_PrimaryPrefab != Entity.Null)
		{
			if (prefabRef.m_Prefab != vehicleModel.m_PrimaryPrefab)
			{
				return false;
			}
			if (vehicleModel.m_SecondaryPrefab != Entity.Null)
			{
				if (layout.IsCreated)
				{
					for (int i = 0; i < layout.Length; i++)
					{
						prefabRef = prefabRefData[layout[i].m_Vehicle];
						if (prefabRef == vehicleModel.m_SecondaryPrefab)
						{
							return true;
						}
					}
				}
				return false;
			}
		}
		return true;
	}
```

- `public static GetBoardingVehicle(Unity.Entities.Entity currentLane, Unity.Entities.Entity currentWaypoint, Unity.Entities.Entity targetWaypoint, System.UInt32 minDeparture, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Routes.Connected, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedData, Unity.Entities.ComponentLookup`1[[Game.Routes.BoardingVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& boardingVehicleData, Unity.Entities.ComponentLookup`1[[Game.Routes.CurrentRoute, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentRouteData, Unity.Entities.ComponentLookup`1[[Game.Routes.AccessLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& accessLaneData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.PublicTransport, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& publicTransportData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.Taxi, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& taxiData, Unity.Entities.BufferLookup`1[[Game.Routes.ConnectedRoute, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedRoutes, Unity.Entities.Entity& vehicle, System.Boolean& testing, System.Boolean& obsolete) : System.Boolean`  

```csharp
public static bool GetBoardingVehicle(Entity currentLane, Entity currentWaypoint, Entity targetWaypoint, uint minDeparture, ref ComponentLookup<Owner> ownerData, ref ComponentLookup<Connected> connectedData, ref ComponentLookup<BoardingVehicle> boardingVehicleData, ref ComponentLookup<CurrentRoute> currentRouteData, ref ComponentLookup<AccessLane> accessLaneData, ref ComponentLookup<Game.Vehicles.PublicTransport> publicTransportData, ref ComponentLookup<Game.Vehicles.Taxi> taxiData, ref BufferLookup<ConnectedRoute> connectedRoutes, out Entity vehicle, out bool testing, out bool obsolete)
	{
		if (currentLane != currentWaypoint && accessLaneData.TryGetComponent(currentWaypoint, out var componentData))
		{
			Entity entity = Entity.Null;
			Entity entity2 = Entity.Null;
			if (ownerData.TryGetComponent(currentLane, out var componentData2))
			{
				entity = componentData2.m_Owner;
			}
			if (ownerData.TryGetComponent(componentData.m_Lane, out var componentData3))
			{
				entity2 = componentData3.m_Owner;
			}
			if (entity != entity2 && (!connectedData.TryGetComponent(currentWaypoint, out var componentData4) || componentData4.m_Connected != currentLane))
			{
				vehicle = Entity.Null;
				testing = false;
				obsolete = true;
				return false;
			}
		}
		if (boardingVehicleData.TryGetComponent(currentWaypoint, out var componentData5))
		{
			if (componentData5.m_Vehicle != Entity.Null && taxiData.TryGetComponent(componentData5.m_Vehicle, out var componentData6) && (componentData6.m_State & TaxiFlags.Boarding) != 0)
			{
				vehicle = componentData5.m_Vehicle;
				testing = false;
				obsolete = false;
				return true;
			}
			vehicle = Entity.Null;
			testing = false;
			obsolete = false;
			return false;
		}
		if (connectedData.TryGetComponent(currentWaypoint, out var componentData7) && connectedData.TryGetComponent(targetWaypoint, out var componentData8))
		{
			Entity connected = componentData7.m_Connected;
			Entity connected2 = componentData8.m_Connected;
			if (boardingVehicleData.TryGetComponent(connected, out componentData5) && connectedRoutes.TryGetBuffer(connected2, out var bufferData))
			{
				if (currentRouteData.TryGetComponent(componentData5.m_Vehicle, out var componentData9) && (!publicTransportData.TryGetComponent(componentData5.m_Vehicle, out var componentData10) || ((componentData10.m_State & (PublicTransportFlags.EnRoute | PublicTransportFlags.Boarding)) == (PublicTransportFlags.EnRoute | PublicTransportFlags.Boarding) && (componentData10.m_DepartureFrame >= minDeparture || componentData10.m_MaxBoardingDistance != float.MaxValue))))
				{
					for (int i = 0; i < bufferData.Length; i++)
					{
						if (ownerData[bufferData[i].m_Waypoint].m_Owner == componentData9.m_Route)
						{
							vehicle = componentData5.m_Vehicle;
							testing = false;
							obsolete = false;
							return true;
						}
					}
				}
				if (currentRouteData.TryGetComponent(componentData5.m_Testing, out componentData9) && (!publicTransportData.TryGetComponent(componentData5.m_Testing, out var componentData11) || (componentData11.m_State & (PublicTransportFlags.EnRoute | PublicTransportFlags.Testing | PublicTransportFlags.RequireStop)) == (PublicTransportFlags.EnRoute | PublicTransportFlags.Testing)))
				{
					for (int j = 0; j < bufferData.Length; j++)
					{
						if (ownerData[bufferData[j].m_Waypoint].m_Owner == componentData9.m_Route)
						{
							vehicle = componentData5.m_Testing;
							testing = true;
							obsolete = false;
							return false;
						}
					}
				}
				vehicle = Entity.Null;
				testing = false;
				obsolete = false;
				return false;
			}
		}
		vehicle = Entity.Null;
		testing = false;
		obsolete = true;
		return false;
	}
```

- `public static GetMaxTaxiCount(Game.Routes.WaitingPassengers waitingPassengers) : System.Int32`  

```csharp
public static int GetMaxTaxiCount(WaitingPassengers waitingPassengers)
	{
		return 3 + (waitingPassengers.m_Count + 3 >> 2);
	}
```

- `public static GetMinWaypointDistance(Game.Prefabs.RouteData routeData) : System.Single`  

```csharp
public static float GetMinWaypointDistance(RouteData routeData)
	{
		return routeData.m_SnapDistance * 0.5f;
	}
```

- `public static GetPathMethods(Game.Prefabs.RouteConnectionType routeConnectionType, Game.Routes.RouteType routeType, Game.Net.TrackTypes trackTypes, Game.Net.RoadTypes roadTypes, Game.Vehicles.SizeClass sizeClass) : Game.Pathfind.PathMethod`  

```csharp
public static PathMethod GetPathMethods(RouteConnectionType routeConnectionType, RouteType routeType, TrackTypes trackTypes, RoadTypes roadTypes, SizeClass sizeClass)
	{
		switch (routeConnectionType)
		{
		case RouteConnectionType.Pedestrian:
			return PathMethod.Pedestrian;
		case RouteConnectionType.Road:
		case RouteConnectionType.Air:
		{
			PathMethod pathMethod = PathMethod.Road;
			if (routeType == RouteType.WorkRoute)
			{
				pathMethod |= PathMethod.Offroad;
			}
			if ((int)sizeClass <= 1)
			{
				pathMethod |= PathMethod.MediumRoad;
			}
			if ((roadTypes & (RoadTypes.Helicopter | RoadTypes.Airplane)) != RoadTypes.None)
			{
				pathMethod |= PathMethod.Flying;
			}
			return pathMethod;
		}
		case RouteConnectionType.Track:
			return PathMethod.Track;
		default:
			return (PathMethod)0;
		}
	}
```

- `public static GetPublicTransportMethods(System.Single timeOfDay, System.Single predictionOffset = 0,020833334) : Game.Pathfind.PathMethod`  

```csharp
public static PathMethod GetPublicTransportMethods(Game.Creatures.Resident resident, float timeOfDay, float predictionOffset = 1f / 48f)
	{
		if ((resident.m_Flags & ResidentFlags.IgnoreTransport) != ResidentFlags.None)
		{
			return (PathMethod)0;
		}
		timeOfDay = math.frac(timeOfDay + predictionOffset);
		if (!(timeOfDay >= 0.25f) || !(timeOfDay < 11f / 12f))
		{
			return PathMethod.PublicTransportNight;
		}
		return PathMethod.PublicTransportDay;
	}
```

- `public static GetPublicTransportMethods(Game.Creatures.Resident resident, System.Single timeOfDay, System.Single predictionOffset = 0,020833334) : Game.Pathfind.PathMethod`  

```csharp
public static PathMethod GetPublicTransportMethods(Game.Creatures.Resident resident, float timeOfDay, float predictionOffset = 1f / 48f)
	{
		if ((resident.m_Flags & ResidentFlags.IgnoreTransport) != ResidentFlags.None)
		{
			return (PathMethod)0;
		}
		timeOfDay = math.frac(timeOfDay + predictionOffset);
		if (!(timeOfDay >= 0.25f) || !(timeOfDay < 11f / 12f))
		{
			return PathMethod.PublicTransportNight;
		}
		return PathMethod.PublicTransportDay;
	}
```

- `public static GetStopDuration(Game.Prefabs.TransportLineData prefabLineData, Game.Routes.TransportStop transportStop) : System.Single`  

```csharp
public static float GetStopDuration(TransportLineData prefabLineData, TransportStop transportStop)
	{
		return prefabLineData.m_StopDuration / math.max(0.25f, transportStop.m_LoadingFactor);
	}
```

- `public static GetTaxiMethods(Game.Creatures.Resident resident) : Game.Pathfind.PathMethod`  

```csharp
public static PathMethod GetTaxiMethods(Game.Creatures.Resident resident)
	{
		if ((resident.m_Flags & ResidentFlags.IgnoreTaxi) != ResidentFlags.None)
		{
			return (PathMethod)0;
		}
		return PathMethod.Taxi;
	}
```

- `public static HasOption(Game.Prefabs.RouteOptionData optionData, Game.Routes.RouteOption option) : System.Boolean`  

```csharp
public static bool HasOption(RouteOptionData optionData, RouteOption option)
	{
		return (optionData.m_OptionMask & (uint)(1 << (int)option)) != 0;
	}
```

- `private static OffsetPathTarget_AreaLane(Unity.Mathematics.Random& random, System.Single distance, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.ConnectionLane> connectionLaneData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, Unity.Entities.BufferLookup<Game.Areas.Node> areaNodes, Unity.Entities.BufferLookup<Game.Areas.Triangle> areaTriangles) : System.Void`  

```csharp
private static void OffsetPathTarget_AreaLane(ref Unity.Mathematics.Random random, float distance, int elementIndex, DynamicBuffer<PathElement> path, ComponentLookup<Owner> ownerData, ComponentLookup<Curve> curveData, ComponentLookup<Lane> laneData, ComponentLookup<Game.Net.ConnectionLane> connectionLaneData, BufferLookup<Game.Net.SubLane> subLanes, BufferLookup<Game.Areas.Node> areaNodes, BufferLookup<Triangle> areaTriangles)
	{
		PathElement pathElement = path[elementIndex];
		Curve curve = curveData[pathElement.m_Target];
		Entity owner = ownerData[pathElement.m_Target].m_Owner;
		float3 position = MathUtils.Position(curve.m_Bezier, pathElement.m_TargetDelta.y);
		DynamicBuffer<Game.Areas.Node> nodes = areaNodes[owner];
		DynamicBuffer<Triangle> dynamicBuffer = areaTriangles[owner];
		int num = -1;
		float num2 = 0f;
		float2 t;
		for (int i = 0; i < dynamicBuffer.Length; i++)
		{
			Triangle3 triangle = AreaUtils.GetTriangle3(nodes, dynamicBuffer[i]);
			if (!(MathUtils.Distance(triangle, position, out t) >= distance))
			{
				float num3 = MathUtils.Area(triangle.xz);
				num2 += num3;
				if (random.NextFloat(num2) < num3)
				{
					num = i;
				}
			}
		}
		if (num == -1)
		{
			return;
		}
		DynamicBuffer<Game.Net.SubLane> lanes = subLanes[owner];
		float2 @float = random.NextFloat2(1f);
		@float = math.select(@float, 1f - @float, math.csum(@float) > 1f);
		Triangle3 triangle2 = AreaUtils.GetTriangle3(nodes, dynamicBuffer[num]);
		float3 position2 = MathUtils.Position(triangle2, @float);
		float num4 = float.MaxValue;
		Entity entity = Entity.Null;
		float endCurvePos = 0f;
		for (int j = 0; j < lanes.Length; j++)
		{
			Entity subLane = lanes[j].m_SubLane;
			if (!connectionLaneData.HasComponent(subLane) || (connectionLaneData[subLane].m_Flags & ConnectionLaneFlags.Pedestrian) == 0)
			{
				continue;
			}
			curve = curveData[subLane];
			bool2 x = new bool2(MathUtils.Intersect(triangle2.xz, curve.m_Bezier.a.xz, out t), MathUtils.Intersect(triangle2.xz, curve.m_Bezier.d.xz, out t));
			if (math.any(x))
			{
				float t2;
				float num5 = MathUtils.Distance(curve.m_Bezier, position2, out t2);
				if (num5 < num4)
				{
					float2 float2 = math.select(new float2(0f, 0.49f), math.select(new float2(0.51f, 1f), new float2(0f, 1f), x.x), x.y);
					num4 = num5;
					entity = subLane;
					endCurvePos = random.NextFloat(float2.x, float2.y);
				}
			}
		}
		if (entity == Entity.Null)
		{
			UnityEngine.Debug.Log($"Target path lane not found ({position2.x}, {position2.y}, {position2.z})");
			return;
		}
		int num6 = elementIndex;
		Owner componentData;
		while (num6 > 0 && ownerData.TryGetComponent(path[num6 - 1].m_Target, out componentData) && !(componentData.m_Owner != owner))
		{
			num6--;
		}
		NativeList<PathElement> path2 = new NativeList<PathElement>(lanes.Length, Allocator.Temp);
		PathElement pathElement2 = path[num6];
		AreaUtils.FindAreaPath(ref random, path2, lanes, pathElement2.m_Target, pathElement2.m_TargetDelta.x, entity, endCurvePos, laneData, curveData);
		if (path2.Length != 0)
		{
			int num7 = elementIndex - num6 + 1;
			int num8 = math.min(num7, path2.Length);
			for (int k = 0; k < num8; k++)
			{
				path[num6 + k] = path2[k];
			}
			if (path2.Length < num7)
			{
				path.RemoveRange(num6 + path2.Length, num7 - path2.Length);
			}
			else
			{
				for (int l = num7; l < path2.Length; l++)
				{
					path.Insert(num6 + l, path2[l]);
				}
			}
		}
		path2.Dispose();
	}
```

- `private static OffsetPathTarget_EdgeLane(Unity.Mathematics.Random& random, System.Single distance, System.Int32 elementIndex, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes) : System.Void`  

```csharp
private static void OffsetPathTarget_EdgeLane(ref Unity.Mathematics.Random random, float distance, int elementIndex, DynamicBuffer<PathElement> path, ComponentLookup<Owner> ownerData, ComponentLookup<Lane> laneData, ComponentLookup<Curve> curveData, BufferLookup<Game.Net.SubLane> subLanes)
	{
		PathElement value = path[elementIndex];
		Curve curve = curveData[value.m_Target];
		float num = random.NextFloat(0f - distance, distance);
		if (num >= 0f)
		{
			Bounds1 t = new Bounds1(value.m_TargetDelta.y, 1f);
			float length = num;
			if (MathUtils.ClampLength(curve.m_Bezier.xz, ref t, ref length))
			{
				value.m_TargetDelta.y = t.max;
				path[elementIndex] = value;
				return;
			}
			Entity entity = value.m_Target;
			if (NetUtils.FindNextLane(ref entity, ref ownerData, ref laneData, ref subLanes))
			{
				num = math.max(0f, num - length);
				t = new Bounds1(0f, 1f);
				MathUtils.ClampLength(curveData[entity].m_Bezier.xz, ref t, num);
				if (elementIndex > 0 && path[elementIndex - 1].m_Target == entity)
				{
					path.RemoveAt(elementIndex--);
					value = path[elementIndex];
					value.m_TargetDelta.y = t.max;
					path[elementIndex] = value;
				}
				else
				{
					path.Insert(elem: new PathElement
					{
						m_Target = value.m_Target,
						m_TargetDelta = new float2(value.m_TargetDelta.x, 1f)
					}, index: elementIndex++);
					value.m_Target = entity;
					value.m_TargetDelta = new float2(0f, t.max);
					path[elementIndex] = value;
				}
			}
			else
			{
				value.m_TargetDelta.y = math.saturate(value.m_TargetDelta.y + (1f - value.m_TargetDelta.y) * num / distance);
				path[elementIndex] = value;
			}
			return;
		}
		num = 0f - num;
		Bounds1 t2 = new Bounds1(0f, value.m_TargetDelta.y);
		float length2 = num;
		if (MathUtils.ClampLengthInverse(curve.m_Bezier.xz, ref t2, ref length2))
		{
			value.m_TargetDelta.y = t2.min;
			path[elementIndex] = value;
			return;
		}
		Entity entity2 = value.m_Target;
		if (NetUtils.FindPrevLane(ref entity2, ref ownerData, ref laneData, ref subLanes))
		{
			num = math.max(0f, num - length2);
			t2 = new Bounds1(0f, 1f);
			MathUtils.ClampLengthInverse(curveData[entity2].m_Bezier.xz, ref t2, num);
			if (elementIndex > 0 && path[elementIndex - 1].m_Target == entity2)
			{
				path.RemoveAt(elementIndex--);
				value = path[elementIndex];
				value.m_TargetDelta.y = t2.min;
				path[elementIndex] = value;
			}
			else
			{
				path.Insert(elem: new PathElement
				{
					m_Target = value.m_Target,
					m_TargetDelta = new float2(value.m_TargetDelta.x, 0f)
				}, index: elementIndex++);
				value.m_Target = entity2;
				value.m_TargetDelta = new float2(1f, t2.min);
				path[elementIndex] = value;
			}
		}
		else
		{
			value.m_TargetDelta.y = math.saturate(value.m_TargetDelta.y - value.m_TargetDelta.y * num / distance);
			path[elementIndex] = value;
		}
	}
```

- `public static ShouldExitVehicle(Unity.Entities.Entity nextLane, Unity.Entities.Entity targetWaypoint, Unity.Entities.Entity currentVehicle, Unity.Entities.ComponentLookup`1[[Game.Common.Owner, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& ownerData, Unity.Entities.ComponentLookup`1[[Game.Routes.Connected, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedData, Unity.Entities.ComponentLookup`1[[Game.Routes.BoardingVehicle, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& boardingVehicleData, Unity.Entities.ComponentLookup`1[[Game.Routes.CurrentRoute, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& currentRouteData, Unity.Entities.ComponentLookup`1[[Game.Routes.AccessLane, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& accessLaneData, Unity.Entities.ComponentLookup`1[[Game.Vehicles.PublicTransport, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& publicTransportData, Unity.Entities.BufferLookup`1[[Game.Routes.ConnectedRoute, Game, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& connectedRoutes, System.Boolean testing, System.Boolean& obsolete) : System.Boolean`  

```csharp
public static bool ShouldExitVehicle(Entity nextLane, Entity targetWaypoint, Entity currentVehicle, ref ComponentLookup<Owner> ownerData, ref ComponentLookup<Connected> connectedData, ref ComponentLookup<BoardingVehicle> boardingVehicleData, ref ComponentLookup<CurrentRoute> currentRouteData, ref ComponentLookup<AccessLane> accessLaneData, ref ComponentLookup<Game.Vehicles.PublicTransport> publicTransportData, ref BufferLookup<ConnectedRoute> connectedRoutes, bool testing, out bool obsolete)
	{
		if (connectedData.TryGetComponent(targetWaypoint, out var componentData) && currentRouteData.TryGetComponent(currentVehicle, out var componentData2))
		{
			Entity connected = componentData.m_Connected;
			if (boardingVehicleData.TryGetComponent(connected, out var componentData3) && connectedRoutes.TryGetBuffer(connected, out var bufferData))
			{
				if ((testing ? componentData3.m_Testing : componentData3.m_Vehicle) == currentVehicle)
				{
					obsolete = false;
					if (nextLane != Entity.Null && accessLaneData.TryGetComponent(targetWaypoint, out var componentData4))
					{
						Entity entity = Entity.Null;
						Entity entity2 = Entity.Null;
						if (ownerData.TryGetComponent(nextLane, out var componentData5))
						{
							entity = componentData5.m_Owner;
						}
						if (ownerData.TryGetComponent(componentData4.m_Lane, out var componentData6))
						{
							entity2 = componentData6.m_Owner;
						}
						if (entity != entity2)
						{
							obsolete = true;
						}
					}
					return true;
				}
				if (publicTransportData.TryGetComponent(currentVehicle, out var componentData7) && (componentData7.m_State & PublicTransportFlags.EnRoute) == 0)
				{
					obsolete = true;
					return true;
				}
				for (int i = 0; i < bufferData.Length; i++)
				{
					if (ownerData[bufferData[i].m_Waypoint].m_Owner == componentData2.m_Route)
					{
						obsolete = false;
						return false;
					}
				}
			}
		}
		obsolete = true;
		return true;
	}
```

- `public static StripTransportSegments<TTransportEstimateBuffer>(Unity.Mathematics.Random& random, System.Int32 length, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Routes.Connected> connectedData, Unity.Entities.ComponentLookup<Game.Routes.BoardingVehicle> boardingVehicleData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.ConnectionLane> connectionLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefData, Unity.Entities.ComponentLookup<Game.Prefabs.TransportStopData> prefabTransportStopData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, Unity.Entities.BufferLookup<Game.Areas.Node> areaNodes, Unity.Entities.BufferLookup<Game.Areas.Triangle> areaTriangles, TTransportEstimateBuffer transportEstimateBuffer) : System.Void`  

```csharp
public static System.Void StripTransportSegments<TTransportEstimateBuffer>(Unity.Mathematics.Random& random, System.Int32 length, Unity.Entities.DynamicBuffer<Game.Pathfind.PathElement> path, Unity.Entities.ComponentLookup<Game.Routes.Connected> connectedData, Unity.Entities.ComponentLookup<Game.Routes.BoardingVehicle> boardingVehicleData, Unity.Entities.ComponentLookup<Game.Common.Owner> ownerData, Unity.Entities.ComponentLookup<Game.Net.Lane> laneData, Unity.Entities.ComponentLookup<Game.Net.ConnectionLane> connectionLaneData, Unity.Entities.ComponentLookup<Game.Net.Curve> curveData, Unity.Entities.ComponentLookup<Game.Prefabs.PrefabRef> prefabRefData, Unity.Entities.ComponentLookup<Game.Prefabs.TransportStopData> prefabTransportStopData, Unity.Entities.BufferLookup<Game.Net.SubLane> subLanes, Unity.Entities.BufferLookup<Game.Areas.Node> areaNodes, Unity.Entities.BufferLookup<Game.Areas.Triangle> areaTriangles, TTransportEstimateBuffer transportEstimateBuffer);
```

- `public static UpdateAverageTravelTime(System.Single oldTravelTime, System.UInt32 departureFrame, System.UInt32 arrivalFrame) : System.Single`  

```csharp
public static float UpdateAverageTravelTime(float oldTravelTime, uint departureFrame, uint arrivalFrame)
	{
		if (departureFrame == 0)
		{
			return oldTravelTime;
		}
		float num = (float)(arrivalFrame - departureFrame) / 60f;
		if (oldTravelTime == 0f)
		{
			return num;
		}
		return math.lerp(oldTravelTime, num, 0.5f);
	}
```


## Nested types

- `Game.Routes.RouteUtils+ITransportEstimateBuffer`  

