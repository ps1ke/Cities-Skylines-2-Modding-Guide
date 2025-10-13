# Game.Prefabs.RouteConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RouteConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.NotificationIconPrefab m_PathfindNotification;
    public Game.Prefabs.RoutePrefab m_CarPathVisualization;
    public Game.Prefabs.RoutePrefab m_WatercraftPathVisualization;
    public Game.Prefabs.RoutePrefab m_AircraftPathVisualization;
    public Game.Prefabs.RoutePrefab m_TrainPathVisualization;
    public Game.Prefabs.RoutePrefab m_HumanPathVisualization;
    public Game.Prefabs.RoutePrefab m_MissingRoutePrefab;

    public RouteConfigurationPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.NotificationIconPrefab m_PathfindNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_PathfindNotification;
```

- `public Game.Prefabs.RoutePrefab m_CarPathVisualization`  

```csharp
public Game.Prefabs.RoutePrefab m_CarPathVisualization;
```

- `public Game.Prefabs.RoutePrefab m_WatercraftPathVisualization`  

```csharp
public Game.Prefabs.RoutePrefab m_WatercraftPathVisualization;
```

- `public Game.Prefabs.RoutePrefab m_AircraftPathVisualization`  

```csharp
public Game.Prefabs.RoutePrefab m_AircraftPathVisualization;
```

- `public Game.Prefabs.RoutePrefab m_TrainPathVisualization`  

```csharp
public Game.Prefabs.RoutePrefab m_TrainPathVisualization;
```

- `public Game.Prefabs.RoutePrefab m_HumanPathVisualization`  

```csharp
public Game.Prefabs.RoutePrefab m_HumanPathVisualization;
```

- `public Game.Prefabs.RoutePrefab m_MissingRoutePrefab`  

```csharp
public Game.Prefabs.RoutePrefab m_MissingRoutePrefab;
```


## Constructors

- `public RouteConfigurationPrefab()`  

```csharp
public RouteConfigurationPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		prefabs.Add(m_PathfindNotification);
		prefabs.Add(m_CarPathVisualization);
		prefabs.Add(m_WatercraftPathVisualization);
		prefabs.Add(m_AircraftPathVisualization);
		prefabs.Add(m_TrainPathVisualization);
		prefabs.Add(m_HumanPathVisualization);
		prefabs.Add(m_MissingRoutePrefab);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<RouteConfigurationData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		entityManager.SetComponentData(entity, new RouteConfigurationData
		{
			m_PathfindNotification = orCreateSystemManaged.GetEntity(m_PathfindNotification),
			m_CarPathVisualization = orCreateSystemManaged.GetEntity(m_CarPathVisualization),
			m_WatercraftPathVisualization = orCreateSystemManaged.GetEntity(m_WatercraftPathVisualization),
			m_AircraftPathVisualization = orCreateSystemManaged.GetEntity(m_AircraftPathVisualization),
			m_TrainPathVisualization = orCreateSystemManaged.GetEntity(m_TrainPathVisualization),
			m_HumanPathVisualization = orCreateSystemManaged.GetEntity(m_HumanPathVisualization),
			m_MissingRoutePrefab = orCreateSystemManaged.GetEntity(m_MissingRoutePrefab)
		});
	}
```


