# Game.Prefabs.MailBox

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class MailBox : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public System.Int32 m_MailCapacity;
    public System.Single m_ComfortFactor;

    public MailBox();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public System.Int32 m_MailCapacity`  

```csharp
public System.Int32 m_MailCapacity;
```

- `public System.Single m_ComfortFactor`  

```csharp
public System.Single m_ComfortFactor;
```


## Constructors

- `public MailBox()`  

```csharp
public MailBox();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Objects.Color>());
		components.Add(ComponentType.ReadWrite<Game.Routes.TransportStop>());
		components.Add(ComponentType.ReadWrite<Game.Routes.MailBox>());
		components.Add(ComponentType.ReadWrite<AccessLane>());
		components.Add(ComponentType.ReadWrite<RouteLane>());
		components.Add(ComponentType.ReadWrite<CurrentDistrict>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<MailBoxData>());
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
		componentData.m_RouteRoadType = RoadTypes.Car;
		componentData.m_RouteSizeClass = SizeClass.Undefined;
		componentData.m_StartLaneOffset = 0f;
		componentData.m_EndMargin = 0f;
		TransportStopData componentData2 = default(TransportStopData);
		componentData2.m_ComfortFactor = m_ComfortFactor;
		componentData2.m_LoadingFactor = 0f;
		componentData2.m_AccessDistance = 0f;
		componentData2.m_BoardingTime = 0f;
		componentData2.m_TransportType = TransportType.Post;
		componentData2.m_PassengerTransport = false;
		componentData2.m_CargoTransport = true;
		MailBoxData componentData3 = default(MailBoxData);
		componentData3.m_MailCapacity = m_MailCapacity;
		entityManager.SetComponentData(entity, componentData);
		entityManager.SetComponentData(entity, componentData2);
		entityManager.SetComponentData(entity, componentData3);
	}
```


