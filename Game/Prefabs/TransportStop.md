# Game.Prefabs.TransportStop

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TransportStop : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.TransportType m_TransportType;
    public Game.Prefabs.RouteConnectionType m_AccessConnectionType;
    public Game.Prefabs.RouteConnectionType m_RouteConnectionType;
    public Game.Net.TrackTypes m_AccessTrackType;
    public Game.Net.TrackTypes m_RouteTrackType;
    public Game.Net.RoadTypes m_AccessRoadType;
    public Game.Net.RoadTypes m_RouteRoadType;
    public System.Single m_EnterDistance;
    public System.Single m_ExitDistance;
    public System.Single m_AccessDistance;
    public System.Single m_BoardingTime;
    public System.Single m_ComfortFactor;
    public System.Single m_LoadingFactor;
    public System.Boolean m_PassengerTransport;
    public System.Boolean m_CargoTransport;

    public TransportStop();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.TransportType m_TransportType`  

```csharp
public Game.Prefabs.TransportType m_TransportType;
```

- `public Game.Prefabs.RouteConnectionType m_AccessConnectionType`  

```csharp
public Game.Prefabs.RouteConnectionType m_AccessConnectionType;
```

- `public Game.Prefabs.RouteConnectionType m_RouteConnectionType`  

```csharp
public Game.Prefabs.RouteConnectionType m_RouteConnectionType;
```

- `public Game.Net.TrackTypes m_AccessTrackType`  

```csharp
public Game.Net.TrackTypes m_AccessTrackType;
```

- `public Game.Net.TrackTypes m_RouteTrackType`  

```csharp
public Game.Net.TrackTypes m_RouteTrackType;
```

- `public Game.Net.RoadTypes m_AccessRoadType`  

```csharp
public Game.Net.RoadTypes m_AccessRoadType;
```

- `public Game.Net.RoadTypes m_RouteRoadType`  

```csharp
public Game.Net.RoadTypes m_RouteRoadType;
```

- `public System.Single m_EnterDistance`  

```csharp
public System.Single m_EnterDistance;
```

- `public System.Single m_ExitDistance`  

```csharp
public System.Single m_ExitDistance;
```

- `public System.Single m_AccessDistance`  

```csharp
public System.Single m_AccessDistance;
```

- `public System.Single m_BoardingTime`  

```csharp
public System.Single m_BoardingTime;
```

- `public System.Single m_ComfortFactor`  

```csharp
public System.Single m_ComfortFactor;
```

- `public System.Single m_LoadingFactor`  

```csharp
public System.Single m_LoadingFactor;
```

- `public System.Boolean m_PassengerTransport`  

```csharp
public System.Boolean m_PassengerTransport;
```

- `public System.Boolean m_CargoTransport`  

```csharp
public System.Boolean m_CargoTransport;
```


## Constructors

- `public TransportStop()`  

```csharp
public TransportStop();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Routes.TransportStop>());
		components.Add(ComponentType.ReadWrite<Game.Objects.Color>());
		switch (m_TransportType)
		{
		case TransportType.Bus:
			components.Add(ComponentType.ReadWrite<ConnectedRoute>());
			components.Add(ComponentType.ReadWrite<BoardingVehicle>());
			components.Add(ComponentType.ReadWrite<BusStop>());
			break;
		case TransportType.Train:
			components.Add(ComponentType.ReadWrite<ConnectedRoute>());
			components.Add(ComponentType.ReadWrite<BoardingVehicle>());
			components.Add(ComponentType.ReadWrite<TrainStop>());
			break;
		case TransportType.Taxi:
			components.Add(ComponentType.ReadWrite<BoardingVehicle>());
			components.Add(ComponentType.ReadWrite<RouteVehicle>());
			components.Add(ComponentType.ReadWrite<TaxiStand>());
			components.Add(ComponentType.ReadWrite<DispatchedRequest>());
			if (m_AccessConnectionType != RouteConnectionType.None)
			{
				components.Add(ComponentType.ReadWrite<AccessLane>());
			}
			if (m_RouteConnectionType != RouteConnectionType.None)
			{
				components.Add(ComponentType.ReadWrite<RouteLane>());
			}
			if (m_PassengerTransport)
			{
				components.Add(ComponentType.ReadWrite<WaitingPassengers>());
			}
			break;
		case TransportType.Tram:
			components.Add(ComponentType.ReadWrite<ConnectedRoute>());
			components.Add(ComponentType.ReadWrite<BoardingVehicle>());
			components.Add(ComponentType.ReadWrite<TramStop>());
			break;
		case TransportType.Ship:
			components.Add(ComponentType.ReadWrite<ConnectedRoute>());
			components.Add(ComponentType.ReadWrite<BoardingVehicle>());
			components.Add(ComponentType.ReadWrite<ShipStop>());
			break;
		case TransportType.Helicopter:
		case TransportType.Rocket:
			components.Add(ComponentType.ReadWrite<BoardingVehicle>());
			components.Add(ComponentType.ReadWrite<ConnectedRoute>());
			break;
		case TransportType.Airplane:
			components.Add(ComponentType.ReadWrite<BoardingVehicle>());
			components.Add(ComponentType.ReadWrite<ConnectedRoute>());
			components.Add(ComponentType.ReadWrite<AirplaneStop>());
			if (GetComponent<OutsideConnection>() != null)
			{
				components.Add(ComponentType.ReadWrite<Game.Net.SubLane>());
			}
			break;
		case TransportType.Subway:
			components.Add(ComponentType.ReadWrite<ConnectedRoute>());
			components.Add(ComponentType.ReadWrite<BoardingVehicle>());
			components.Add(ComponentType.ReadWrite<SubwayStop>());
			break;
		case TransportType.Post:
			break;
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<TransportStopData>());
		components.Add(ComponentType.ReadWrite<RouteConnectionData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		RouteConnectionData componentData = default(RouteConnectionData);
		componentData.m_AccessConnectionType = m_AccessConnectionType;
		componentData.m_RouteConnectionType = m_RouteConnectionType;
		componentData.m_AccessTrackType = m_AccessTrackType;
		componentData.m_RouteTrackType = m_RouteTrackType;
		componentData.m_AccessRoadType = m_AccessRoadType;
		componentData.m_RouteRoadType = m_RouteRoadType;
		componentData.m_RouteSizeClass = SizeClass.Undefined;
		componentData.m_StartLaneOffset = m_EnterDistance;
		componentData.m_EndMargin = m_ExitDistance;
		TransportStopData componentData2 = new TransportStopData
		{
			m_ComfortFactor = m_ComfortFactor,
			m_LoadingFactor = m_LoadingFactor,
			m_AccessDistance = m_AccessDistance,
			m_BoardingTime = m_BoardingTime,
			m_TransportType = m_TransportType,
			m_PassengerTransport = m_PassengerTransport,
			m_CargoTransport = m_CargoTransport
		};
		entityManager.SetComponentData(entity, componentData);
		entityManager.SetComponentData(entity, componentData2);
	}
```


