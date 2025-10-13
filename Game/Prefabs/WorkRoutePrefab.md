# Game.Prefabs.WorkRoutePrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.RoutePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`, `Game.Prefabs.IColored`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class WorkRoutePrefab : Game.Prefabs.RoutePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase, Game.Prefabs.IColored
{
    public Game.Net.RoadTypes m_RouteRoadType;
    public Game.Vehicles.SizeClass m_SizeClass;

    public WorkRoutePrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Net.RoadTypes m_RouteRoadType`  

```csharp
public Game.Net.RoadTypes m_RouteRoadType;
```

- `public Game.Vehicles.SizeClass m_SizeClass`  

```csharp
public Game.Vehicles.SizeClass m_SizeClass;
```


## Constructors

- `public WorkRoutePrefab()`  

```csharp
public WorkRoutePrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		if (components.Contains(ComponentType.ReadWrite<Route>()))
		{
			components.Add(ComponentType.ReadWrite<WorkRoute>());
		}
		else if (components.Contains(ComponentType.ReadWrite<Waypoint>()))
		{
			components.Add(ComponentType.ReadWrite<AccessLane>());
			components.Add(ComponentType.ReadWrite<RouteLane>());
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
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<RouteConnectionData>());
		components.Add(ComponentType.ReadWrite<WorkRouteData>());
		components.Add(ComponentType.ReadWrite<PlaceableInfoviewItem>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		entityManager.SetComponentData(entity, new RouteConnectionData
		{
			m_AccessConnectionType = RouteConnectionType.Pedestrian,
			m_RouteConnectionType = RouteConnectionType.Road,
			m_AccessTrackType = TrackTypes.None,
			m_RouteTrackType = TrackTypes.None,
			m_AccessRoadType = RoadTypes.None,
			m_RouteRoadType = m_RouteRoadType,
			m_RouteSizeClass = m_SizeClass,
			m_StartLaneOffset = 0f,
			m_EndMargin = 0f
		});
		entityManager.SetComponentData(entity, new WorkRouteData
		{
			m_SizeClass = m_SizeClass
		});
	}
```


