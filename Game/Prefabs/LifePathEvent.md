# Game.Prefabs.LifePathEvent

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ComponentBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class LifePathEvent : Game.Prefabs.ComponentBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public Game.Prefabs.LifePathEventType m_EventType;
    public System.Boolean m_IsChirp;

    public LifePathEvent();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.LifePathEventType m_EventType`  

```csharp
public Game.Prefabs.LifePathEventType m_EventType;
```

- `public System.Boolean m_IsChirp`  

```csharp
public System.Boolean m_IsChirp;
```


## Constructors

- `public LifePathEvent()`  

```csharp
public LifePathEvent();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<Game.Triggers.LifePathEvent>());
		components.Add(ComponentType.ReadWrite<PrefabRef>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		components.Add(ComponentType.ReadWrite<LifePathEventData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		List<ComponentBase> list = new List<ComponentBase>();
		GetComponents(list);
		HashSet<ComponentType> hashSet = new HashSet<ComponentType>();
		for (int i = 0; i < list.Count; i++)
		{
			list[i].GetArchetypeComponents(hashSet);
		}
		hashSet.Add(ComponentType.ReadWrite<Created>());
		hashSet.Add(ComponentType.ReadWrite<Updated>());
		hashSet.Add(ComponentType.ReadWrite<Game.Triggers.Chirp>());
		hashSet.Add(ComponentType.ReadWrite<ChirpEntity>());
		hashSet.Add(ComponentType.ReadWrite<PrefabRef>());
		LifePathEventData componentData = default(LifePathEventData);
		componentData.m_ChirpArchetype = entityManager.CreateArchetype(PrefabUtils.ToArray(hashSet));
		componentData.m_IsChirp = m_IsChirp;
		componentData.m_EventType = m_EventType;
		entityManager.SetComponentData(entity, componentData);
	}
```


