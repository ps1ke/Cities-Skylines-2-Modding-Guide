# Game.Prefabs.HangaroundArea

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class HangaroundArea : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.ActivityType[] m_Activities;

    public HangaroundArea();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.ActivityType[] m_Activities`  

```csharp
public Game.Prefabs.ActivityType[] m_Activities;
```


## Constructors

- `public HangaroundArea()`  

```csharp
public HangaroundArea();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<HangaroundLocation>());
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
		NavigationArea component = GetComponent<NavigationArea>();
		SpawnLocationData componentData = default(SpawnLocationData);
		componentData.m_ConnectionType = component.m_ConnectionType;
		componentData.m_TrackTypes = component.m_TrackTypes;
		componentData.m_RoadTypes = component.m_RoadTypes;
		componentData.m_RequireAuthorization = false;
		componentData.m_HangaroundOnLane = false;
		if (m_Activities != null && m_Activities.Length != 0)
		{
			componentData.m_ActivityMask = default(ActivityMask);
			for (int i = 0; i < m_Activities.Length; i++)
			{
				componentData.m_ActivityMask.m_Mask |= new ActivityMask(m_Activities[i]).m_Mask;
			}
		}
		else
		{
			componentData.m_ActivityMask = new ActivityMask(ActivityType.Standing);
		}
		entityManager.SetComponentData(entity, componentData);
	}
```


