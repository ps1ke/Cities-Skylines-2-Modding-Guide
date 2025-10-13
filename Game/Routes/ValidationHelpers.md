# Game.Routes.ValidationHelpers

**Assembly:** `Game`  
**Namespace:** `Game.Routes`  

**Type:** class static public  

**Base:** `System.Object`  

## Code

```csharp
public static class ValidationHelpers
{
    private static Unity.Mathematics.bool2 FindStopLanes(Game.Objects.Attached attached, Game.Prefabs.RouteConnectionData connectionData, Game.Tools.ValidationSystem+EntityData data);
    private static Game.Tools.ErrorType RouteConnectionToError(Game.Prefabs.RouteConnectionType type);
    public static System.Void ValidateRoute(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Prefabs.PrefabRef prefabRef, Unity.Entities.DynamicBuffer<Game.Routes.RouteWaypoint> waypoints, Unity.Entities.DynamicBuffer<Game.Routes.RouteSegment> segments, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
    public static System.Void ValidateStop(System.Boolean editorMode, Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Objects.Attached attached, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue);
}
```


## Methods

- `private static FindStopLanes(Game.Objects.Attached attached, Game.Prefabs.RouteConnectionData connectionData, Game.Tools.ValidationSystem+EntityData data) : Unity.Mathematics.bool2`  

```csharp
private static bool2 FindStopLanes(Attached attached, RouteConnectionData connectionData, ValidationSystem.EntityData data)
	{
		bool2 @bool = new bool2
		{
			x = (connectionData.m_RouteConnectionType == RouteConnectionType.None),
			y = (connectionData.m_AccessConnectionType == RouteConnectionType.None)
		};
		if (!data.m_Lanes.HasBuffer(attached.m_Parent))
		{
			return @bool;
		}
		DynamicBuffer<Game.Net.SubLane> dynamicBuffer = data.m_Lanes[attached.m_Parent];
		bool2 bool2 = new bool2
		{
			x = (connectionData.m_RouteConnectionType == RouteConnectionType.Road),
			y = (connectionData.m_AccessConnectionType == RouteConnectionType.Road)
		};
		bool2 bool3 = new bool2
		{
			x = (connectionData.m_RouteConnectionType == RouteConnectionType.Track),
			y = (connectionData.m_AccessConnectionType == RouteConnectionType.Track)
		};
		bool2 bool4 = new bool2
		{
			x = (connectionData.m_RouteConnectionType == RouteConnectionType.Pedestrian),
			y = (connectionData.m_AccessConnectionType == RouteConnectionType.Pedestrian)
		};
		for (int i = 0; i < dynamicBuffer.Length; i++)
		{
			Entity subLane = dynamicBuffer[i].m_SubLane;
			if (math.any(bool2) && data.m_CarLane.HasComponent(subLane))
			{
				PrefabRef prefabRef = data.m_PrefabRef[subLane];
				CarLaneData carLaneData = data.m_CarLaneData[prefabRef.m_Prefab];
				bool2 bool5 = new bool2
				{
					x = ((carLaneData.m_RoadTypes & connectionData.m_RouteRoadType) != 0),
					y = ((carLaneData.m_RoadTypes & connectionData.m_AccessRoadType) != 0)
				};
				@bool |= bool2 & bool5;
			}
			if (math.any(bool3) && data.m_TrackLane.HasComponent(subLane))
			{
				PrefabRef prefabRef2 = data.m_PrefabRef[subLane];
				TrackLaneData trackLaneData = data.m_TrackLaneData[prefabRef2.m_Prefab];
				bool2 bool6 = new bool2
				{
					x = ((trackLaneData.m_TrackTypes & connectionData.m_RouteTrackType) != 0),
					y = ((trackLaneData.m_TrackTypes & connectionData.m_AccessTrackType) != 0)
				};
				@bool |= bool3 & bool6;
			}
			if (math.any(bool4) && data.m_PedestrianLane.HasComponent(subLane))
			{
				@bool |= bool4;
			}
			if (math.all(@bool))
			{
				return @bool;
			}
		}
		return @bool;
	}
```

- `private static RouteConnectionToError(Game.Prefabs.RouteConnectionType type) : Game.Tools.ErrorType`  

```csharp
private static ErrorType RouteConnectionToError(RouteConnectionType type)
	{
		return type switch
		{
			RouteConnectionType.Road => ErrorType.NoCarAccess, 
			RouteConnectionType.Track => ErrorType.NoTrainAccess, 
			RouteConnectionType.Pedestrian => ErrorType.NoPedestrianAccess, 
			RouteConnectionType.Cargo => ErrorType.NoCargoAccess, 
			_ => ErrorType.None, 
		};
	}
```

- `public static ValidateRoute(Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Prefabs.PrefabRef prefabRef, Unity.Entities.DynamicBuffer<Game.Routes.RouteWaypoint> waypoints, Unity.Entities.DynamicBuffer<Game.Routes.RouteSegment> segments, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static void ValidateRoute(Entity entity, Temp temp, PrefabRef prefabRef, DynamicBuffer<RouteWaypoint> waypoints, DynamicBuffer<RouteSegment> segments, ValidationSystem.EntityData data, NativeQueue<ErrorData>.ParallelWriter errorQueue)
	{
		if (data.m_TransportLineData.TryGetComponent(prefabRef.m_Prefab, out var componentData))
		{
			for (int i = 0; i < waypoints.Length; i++)
			{
				Entity waypoint = waypoints[i].m_Waypoint;
				if (data.m_RouteConnected.TryGetComponent(waypoint, out var componentData2) && data.m_PrefabRef.TryGetComponent(componentData2.m_Connected, out var componentData3) && data.m_TransportStopData.TryGetComponent(componentData3.m_Prefab, out var componentData4))
				{
					if (componentData.m_PassengerTransport & !componentData4.m_PassengerTransport)
					{
						errorQueue.Enqueue(new ErrorData
						{
							m_ErrorSeverity = ErrorSeverity.Error,
							m_ErrorType = ErrorType.NoPedestrianAccess,
							m_Position = float.NaN,
							m_TempEntity = waypoint
						});
					}
					if (componentData.m_CargoTransport & !componentData4.m_CargoTransport)
					{
						errorQueue.Enqueue(new ErrorData
						{
							m_ErrorSeverity = ErrorSeverity.Error,
							m_ErrorType = ErrorType.NoCargoAccess,
							m_Position = float.NaN,
							m_TempEntity = waypoint
						});
					}
				}
			}
		}
		bool flag = false;
		if (data.m_Route.TryGetComponent(temp.m_Original, out var componentData5))
		{
			flag = (componentData5.m_Flags & RouteFlags.Complete) != 0;
		}
		for (int j = 0; j < segments.Length; j++)
		{
			Entity segment = segments[j].m_Segment;
			if (data.m_PathInformation.HasComponent(segment) && data.m_PathInformation[segment].m_Distance < 0f)
			{
				Entity waypoint2 = waypoints[j].m_Waypoint;
				Entity waypoint3 = waypoints[math.select(j + 1, 0, j + 1 == waypoints.Length)].m_Waypoint;
				ErrorData value = new ErrorData
				{
					m_ErrorSeverity = (flag ? ErrorSeverity.Warning : ErrorSeverity.Error),
					m_ErrorType = ErrorType.PathfindFailed,
					m_Position = float.NaN,
					m_TempEntity = waypoint2
				};
				errorQueue.Enqueue(value);
				value.m_TempEntity = waypoint3;
				errorQueue.Enqueue(value);
			}
		}
	}
```

- `public static ValidateStop(System.Boolean editorMode, Unity.Entities.Entity entity, Game.Tools.Temp temp, Game.Common.Owner owner, Game.Objects.Transform transform, Game.Prefabs.PrefabRef prefabRef, Game.Objects.Attached attached, Game.Tools.ValidationSystem+EntityData data, Unity.Collections.NativeQueue<Game.Tools.ErrorData> errorQueue) : System.Void`  

```csharp
public static void ValidateStop(bool editorMode, Entity entity, Temp temp, Owner owner, Transform transform, PrefabRef prefabRef, Attached attached, ValidationSystem.EntityData data, NativeQueue<ErrorData>.ParallelWriter errorQueue)
	{
		if ((temp.m_Flags & (TempFlags.Create | TempFlags.Modify)) == 0)
		{
			return;
		}
		PlaceableObjectData placeableObjectData = default(PlaceableObjectData);
		if (data.m_PlaceableObject.HasComponent(prefabRef.m_Prefab))
		{
			placeableObjectData = data.m_PlaceableObject[prefabRef.m_Prefab];
		}
		if ((placeableObjectData.m_Flags & Game.Objects.PlacementFlags.NetObject) == 0 || (attached.m_Parent != Entity.Null && owner.m_Owner != Entity.Null))
		{
			return;
		}
		RouteConnectionData connectionData = data.m_RouteConnectionData[prefabRef.m_Prefab];
		bool2 x = FindStopLanes(attached, connectionData, data);
		if (math.all(x))
		{
			return;
		}
		ErrorData value = default(ErrorData);
		if (editorMode)
		{
			value.m_ErrorSeverity = ErrorSeverity.Warning;
		}
		else
		{
			value.m_ErrorSeverity = ErrorSeverity.Error;
		}
		if (!math.any(x))
		{
			if (!editorMode && connectionData.m_RouteConnectionType == RouteConnectionType.Road && connectionData.m_AccessConnectionType == RouteConnectionType.Pedestrian)
			{
				value.m_ErrorType = ErrorType.NoRoadAccess;
			}
			else if (!editorMode && connectionData.m_RouteConnectionType == RouteConnectionType.Track && connectionData.m_AccessConnectionType == RouteConnectionType.Pedestrian)
			{
				value.m_ErrorType = ErrorType.NoTrackAccess;
			}
			else
			{
				value.m_ErrorType = RouteConnectionToError(connectionData.m_RouteConnectionType);
			}
		}
		else if (x.x)
		{
			value.m_ErrorType = RouteConnectionToError(connectionData.m_AccessConnectionType);
		}
		else
		{
			value.m_ErrorType = RouteConnectionToError(connectionData.m_RouteConnectionType);
		}
		value.m_TempEntity = entity;
		value.m_Position = float.NaN;
		errorQueue.Enqueue(value);
	}
```


