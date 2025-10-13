# Game.Prefabs.SpawnLocation

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class SpawnLocation : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.RouteConnectionType m_ConnectionType;
    public Game.Net.TrackTypes m_TrackTypes;
    public Game.Net.RoadTypes m_RoadTypes;
    public System.Boolean m_RequireAuthorization;
    public System.Boolean m_HangaroundOnLane;

    public SpawnLocation();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.RouteConnectionType m_ConnectionType`  

```csharp
public Game.Prefabs.RouteConnectionType m_ConnectionType;
```

- `public Game.Net.TrackTypes m_TrackTypes`  

```csharp
public Game.Net.TrackTypes m_TrackTypes;
```

- `public Game.Net.RoadTypes m_RoadTypes`  

```csharp
public Game.Net.RoadTypes m_RoadTypes;
```

- `public System.Boolean m_RequireAuthorization`  

```csharp
public System.Boolean m_RequireAuthorization;
```

- `public System.Boolean m_HangaroundOnLane`  

```csharp
public System.Boolean m_HangaroundOnLane;
```


## Constructors

- `public SpawnLocation()`  

```csharp
public SpawnLocation();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Objects.SpawnLocation>());
		if (m_ConnectionType == RouteConnectionType.Air)
		{
			components.Add(ComponentType.ReadWrite<Game.Routes.TakeoffLocation>());
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<SpawnLocationData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		SpawnLocationData componentData = default(SpawnLocationData);
		componentData.m_ConnectionType = m_ConnectionType;
		componentData.m_ActivityMask = default(ActivityMask);
		componentData.m_TrackTypes = m_TrackTypes;
		componentData.m_RoadTypes = m_RoadTypes;
		componentData.m_RequireAuthorization = m_RequireAuthorization;
		componentData.m_HangaroundOnLane = m_HangaroundOnLane;
		entityManager.SetComponentData(entity, componentData);
	}
```


