# Game.Prefabs.TakeoffLocation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TakeoffLocation : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.RouteConnectionType m_ConnectionType1;
    public Game.Prefabs.RouteConnectionType m_ConnectionType2;
    public Game.Net.RoadTypes m_RoadType;

    public TakeoffLocation();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.RouteConnectionType m_ConnectionType1`  

```csharp
public Game.Prefabs.RouteConnectionType m_ConnectionType1;
```

- `public Game.Prefabs.RouteConnectionType m_ConnectionType2`  

```csharp
public Game.Prefabs.RouteConnectionType m_ConnectionType2;
```

- `public Game.Net.RoadTypes m_RoadType`  

```csharp
public Game.Net.RoadTypes m_RoadType;
```


## Constructors

- `public TakeoffLocation()`  

```csharp
public TakeoffLocation();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Routes.TakeoffLocation>());
		components.Add(ComponentType.ReadWrite<AccessLane>());
		components.Add(ComponentType.ReadWrite<RouteLane>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<RouteConnectionData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		RouteConnectionData componentData = default(RouteConnectionData);
		componentData.m_AccessConnectionType = m_ConnectionType1;
		componentData.m_RouteConnectionType = m_ConnectionType2;
		componentData.m_AccessTrackType = TrackTypes.None;
		componentData.m_RouteTrackType = TrackTypes.None;
		componentData.m_AccessRoadType = m_RoadType;
		componentData.m_RouteRoadType = m_RoadType;
		componentData.m_RouteSizeClass = SizeClass.Undefined;
		componentData.m_StartLaneOffset = 0f;
		componentData.m_EndMargin = 0f;
		entityManager.SetComponentData(entity, componentData);
	}
```


