# Game.Prefabs.SpectatorEvent

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class SpectatorEvent : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.EventTargetType m_RandomSiteType;
    public System.Single m_PreparationDuration;
    public System.Single m_ActiveDuration;
    public System.Single m_TerminationDuration;

    public SpectatorEvent();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.EventTargetType m_RandomSiteType`  

```csharp
public Game.Prefabs.EventTargetType m_RandomSiteType;
```

- `public System.Single m_PreparationDuration`  

```csharp
public System.Single m_PreparationDuration;
```

- `public System.Single m_ActiveDuration`  

```csharp
public System.Single m_ActiveDuration;
```

- `public System.Single m_TerminationDuration`  

```csharp
public System.Single m_TerminationDuration;
```


## Constructors

- `public SpectatorEvent()`  

```csharp
public SpectatorEvent();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Events.SpectatorEvent>());
		components.Add(ComponentType.ReadWrite<Duration>());
		components.Add(ComponentType.ReadWrite<TargetElement>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<SpectatorEventData>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		SpectatorEventData componentData = default(SpectatorEventData);
		componentData.m_RandomSiteType = m_RandomSiteType;
		componentData.m_PreparationDuration = m_PreparationDuration;
		componentData.m_ActiveDuration = m_ActiveDuration;
		componentData.m_TerminationDuration = m_TerminationDuration;
		entityManager.SetComponentData(entity, componentData);
	}
```


