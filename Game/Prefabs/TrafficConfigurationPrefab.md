# Game.Prefabs.TrafficConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TrafficConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.NotificationIconPrefab m_BottleneckNotification;
    public Game.Prefabs.NotificationIconPrefab m_DeadEndNotification;
    public Game.Prefabs.NotificationIconPrefab m_RoadConnectionNotification;
    public Game.Prefabs.NotificationIconPrefab m_TrackConnectionNotification;
    public Game.Prefabs.NotificationIconPrefab m_CarConnectionNotification;
    public Game.Prefabs.NotificationIconPrefab m_ShipConnectionNotification;
    public Game.Prefabs.NotificationIconPrefab m_TrainConnectionNotification;
    public Game.Prefabs.NotificationIconPrefab m_PedestrianConnectionNotification;

    public TrafficConfigurationPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.NotificationIconPrefab m_BottleneckNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_BottleneckNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_DeadEndNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_DeadEndNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_RoadConnectionNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_RoadConnectionNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_TrackConnectionNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_TrackConnectionNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_CarConnectionNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_CarConnectionNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_ShipConnectionNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_ShipConnectionNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_TrainConnectionNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_TrainConnectionNotification;
```

- `public Game.Prefabs.NotificationIconPrefab m_PedestrianConnectionNotification`  

```csharp
public Game.Prefabs.NotificationIconPrefab m_PedestrianConnectionNotification;
```


## Constructors

- `public TrafficConfigurationPrefab()`  

```csharp
public TrafficConfigurationPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		prefabs.Add(m_BottleneckNotification);
		prefabs.Add(m_DeadEndNotification);
		prefabs.Add(m_RoadConnectionNotification);
		prefabs.Add(m_TrackConnectionNotification);
		prefabs.Add(m_CarConnectionNotification);
		prefabs.Add(m_ShipConnectionNotification);
		prefabs.Add(m_TrainConnectionNotification);
		prefabs.Add(m_PedestrianConnectionNotification);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<TrafficConfigurationData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		entityManager.SetComponentData(entity, new TrafficConfigurationData
		{
			m_BottleneckNotification = orCreateSystemManaged.GetEntity(m_BottleneckNotification),
			m_DeadEndNotification = orCreateSystemManaged.GetEntity(m_DeadEndNotification),
			m_RoadConnectionNotification = orCreateSystemManaged.GetEntity(m_RoadConnectionNotification),
			m_TrackConnectionNotification = orCreateSystemManaged.GetEntity(m_TrackConnectionNotification),
			m_CarConnectionNotification = orCreateSystemManaged.GetEntity(m_CarConnectionNotification),
			m_ShipConnectionNotification = orCreateSystemManaged.GetEntity(m_ShipConnectionNotification),
			m_TrainConnectionNotification = orCreateSystemManaged.GetEntity(m_TrainConnectionNotification),
			m_PedestrianConnectionNotification = orCreateSystemManaged.GetEntity(m_PedestrianConnectionNotification)
		});
	}
```


