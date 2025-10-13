# Game.Prefabs.TransportLinePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.RoutePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IColored`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TransportLinePrefab : Game.Prefabs.RoutePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase, Game.Prefabs.IColored
{
    public Game.Prefabs.RouteConnectionType m_AccessConnectionType;
    public Game.Prefabs.RouteConnectionType m_RouteConnectionType;
    public Game.Net.TrackTypes m_AccessTrackType;
    public Game.Net.TrackTypes m_RouteTrackType;
    public Game.Net.RoadTypes m_AccessRoadType;
    public Game.Net.RoadTypes m_RouteRoadType;
    public Game.Prefabs.TransportType m_TransportType;
    public System.Single m_DefaultVehicleInterval;
    public System.Single m_DefaultUnbunchingFactor;
    public System.Single m_StopDuration;
    public Game.Vehicles.SizeClass m_SizeClass;
    public System.Boolean m_PassengerTransport;
    public System.Boolean m_CargoTransport;
    public Game.Prefabs.PathfindPrefab m_PathfindPrefab;
    public Game.Prefabs.NotificationIconPrefab m_VehicleNotification;

    public TransportLinePrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

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

- `public Game.Prefabs.TransportType m_TransportType`  

```csharp
public Game.Prefabs.TransportType m_TransportType;
```

- `public System.Single m_DefaultVehicleInterval`  

```csharp
public System.Single m_DefaultVehicleInterval;
```

- `public System.Single m_DefaultUnbunchingFactor`  

```csharp
public System.Single m_DefaultUnbunchingFactor;
```

- `public System.Single m_StopDuration`  

```csharp
public System.Single m_StopDuration;
```

- `public Game.Vehicles.SizeClass m_SizeClass`  

```csharp
public Game.Vehicles.SizeClass m_SizeClass;
```

- `public System.Boolean m_PassengerTransport`  

```csharp
public System.Boolean m_PassengerTransport;
```

- `public System.Boolean m_CargoTransport`  

```csharp
public System.Boolean m_CargoTransport;
```

- `public Game.Prefabs.PathfindPrefab m_PathfindPrefab`  

```csharp
public Game.Prefabs.PathfindPrefab m_PathfindPrefab;
```

- `public Game.Prefabs.NotificationIconPrefab m_VehicleNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_VehicleNotification;
```


## Constructors

- `public TransportLinePrefab()`  

```csharp
public TransportLinePrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		if (components.Contains(ComponentType.ReadWrite<Route>()))
		{
			components.Add(ComponentType.ReadWrite<TransportLine>());
			components.Add(ComponentType.ReadWrite<VehicleModel>());
			components.Add(ComponentType.ReadWrite<DispatchedRequest>());
			components.Add(ComponentType.ReadWrite<RouteNumber>());
			components.Add(ComponentType.ReadWrite<RouteVehicle>());
			components.Add(ComponentType.ReadWrite<RouteModifier>());
			components.Add(ComponentType.ReadWrite<Policy>());
		}
		else if (components.Contains(ComponentType.ReadWrite<Waypoint>()))
		{
			if (m_AccessConnectionType != RouteConnectionType.None)
			{
				components.Add(ComponentType.ReadWrite<AccessLane>());
			}
			if (m_RouteConnectionType != RouteConnectionType.None)
			{
				components.Add(ComponentType.ReadWrite<RouteLane>());
			}
			if (components.Contains(ComponentType.ReadWrite<Connected>()))
			{
				components.Add(ComponentType.ReadWrite<VehicleTiming>());
			}
			if (m_PassengerTransport)
			{
				components.Add(ComponentType.ReadWrite<WaitingPassengers>());
			}
		}
		else if (components.Contains(ComponentType.ReadWrite<Game.Routes.Segment>()))
		{
			components.Add(ComponentType.ReadWrite<PathTargets>());
			components.Add(ComponentType.ReadWrite<RouteInfo>());
			components.Add(ComponentType.ReadWrite<PathElement>());
			components.Add(ComponentType.ReadWrite<PathInformation>());
		}
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		prefabs.Add(m_PathfindPrefab);
		prefabs.Add(m_VehicleNotification);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<RouteConnectionData>());
		components.Add(ComponentType.ReadWrite<TransportLineData>());
		components.Add(ComponentType.ReadWrite<PlaceableInfoviewItem>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		entityManager.SetComponentData(entity, new RouteConnectionData
		{
			m_AccessConnectionType = m_AccessConnectionType,
			m_RouteConnectionType = m_RouteConnectionType,
			m_AccessTrackType = m_AccessTrackType,
			m_RouteTrackType = m_RouteTrackType,
			m_AccessRoadType = m_AccessRoadType,
			m_RouteRoadType = m_RouteRoadType,
			m_RouteSizeClass = m_SizeClass,
			m_StartLaneOffset = 0f,
			m_EndMargin = 0f
		});
		entityManager.SetComponentData(entity, new TransportLineData
		{
			m_PathfindPrefab = existingSystemManaged.GetEntity(m_PathfindPrefab),
			m_TransportType = m_TransportType,
			m_DefaultVehicleInterval = m_DefaultVehicleInterval,
			m_DefaultUnbunchingFactor = m_DefaultUnbunchingFactor,
			m_StopDuration = m_StopDuration,
			m_SizeClass = m_SizeClass,
			m_PassengerTransport = m_PassengerTransport,
			m_CargoTransport = m_CargoTransport,
			m_VehicleNotification = existingSystemManaged.GetEntity(m_VehicleNotification)
		});
	}
```


