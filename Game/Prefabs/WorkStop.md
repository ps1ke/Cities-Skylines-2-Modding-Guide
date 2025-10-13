# Game.Prefabs.WorkStop

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WorkStop : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Net.RoadTypes m_RouteRoadType;
    public System.Boolean m_WorkLocation;

    public WorkStop();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Net.RoadTypes m_RouteRoadType`  

```csharp
public Game.Net.RoadTypes m_RouteRoadType;
```

- `public System.Boolean m_WorkLocation`  

```csharp
public System.Boolean m_WorkLocation;
```


## Constructors

- `public WorkStop()`  

```csharp
public WorkStop();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Objects.Color>());
		components.Add(ComponentType.ReadWrite<Game.Routes.TransportStop>());
		components.Add(ComponentType.ReadWrite<Game.Routes.WorkStop>());
		components.Add(ComponentType.ReadWrite<ConnectedRoute>());
		components.Add(ComponentType.ReadWrite<BoardingVehicle>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<WorkStopData>());
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
		componentData.m_AccessConnectionType = RouteConnectionType.Pedestrian;
		componentData.m_RouteConnectionType = RouteConnectionType.Road;
		componentData.m_AccessTrackType = TrackTypes.None;
		componentData.m_RouteTrackType = TrackTypes.None;
		componentData.m_AccessRoadType = RoadTypes.None;
		componentData.m_RouteRoadType = m_RouteRoadType;
		componentData.m_RouteSizeClass = SizeClass.Undefined;
		componentData.m_StartLaneOffset = 0f;
		componentData.m_EndMargin = 0f;
		TransportStopData componentData2 = default(TransportStopData);
		componentData2.m_ComfortFactor = 0f;
		componentData2.m_LoadingFactor = 0f;
		componentData2.m_AccessDistance = 0f;
		componentData2.m_BoardingTime = 0f;
		componentData2.m_TransportType = TransportType.Work;
		componentData2.m_PassengerTransport = false;
		componentData2.m_CargoTransport = true;
		WorkStopData componentData3 = default(WorkStopData);
		componentData3.m_WorkLocation = m_WorkLocation;
		entityManager.SetComponentData(entity, componentData);
		entityManager.SetComponentData(entity, componentData2);
		entityManager.SetComponentData(entity, componentData3);
	}
```


