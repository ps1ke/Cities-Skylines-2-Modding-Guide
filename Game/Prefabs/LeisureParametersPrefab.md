# Game.Prefabs.LeisureParametersPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class LeisureParametersPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.EventPrefab m_TravelingEvent;
    public Game.Prefabs.EventPrefab m_AttractionPrefab;
    public Game.Prefabs.EventPrefab m_SightseeingPrefab;
    public System.Int32 m_LeisureRandomFactor;
    public System.Int32 m_TouristLodgingConsumePerDay;
    public System.Int32 m_TouristServiceConsumePerDay;

    public LeisureParametersPrefab();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.EventPrefab m_TravelingEvent`  

```csharp
public Game.Prefabs.EventPrefab m_TravelingEvent;
```

- `public Game.Prefabs.EventPrefab m_AttractionPrefab`  

```csharp
public Game.Prefabs.EventPrefab m_AttractionPrefab;
```

- `public Game.Prefabs.EventPrefab m_SightseeingPrefab`  

```csharp
public Game.Prefabs.EventPrefab m_SightseeingPrefab;
```

- `public System.Int32 m_LeisureRandomFactor`  

```csharp
public System.Int32 m_LeisureRandomFactor;
```

- `public System.Int32 m_TouristLodgingConsumePerDay`  

```csharp
public System.Int32 m_TouristLodgingConsumePerDay;
```

- `public System.Int32 m_TouristServiceConsumePerDay`  

```csharp
public System.Int32 m_TouristServiceConsumePerDay;
```


## Constructors

- `public LeisureParametersPrefab()`  

```csharp
public LeisureParametersPrefab();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
	}
```

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		prefabs.Add(m_TravelingEvent);
		prefabs.Add(m_AttractionPrefab);
		prefabs.Add(m_SightseeingPrefab);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<LeisureParametersData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		LeisureParametersData componentData = default(LeisureParametersData);
		componentData.m_TravelingPrefab = orCreateSystemManaged.GetEntity(m_TravelingEvent);
		componentData.m_AttractionPrefab = orCreateSystemManaged.GetEntity(m_AttractionPrefab);
		componentData.m_SightseeingPrefab = orCreateSystemManaged.GetEntity(m_SightseeingPrefab);
		componentData.m_LeisureRandomFactor = m_LeisureRandomFactor;
		componentData.m_TouristLodgingConsumePerDay = m_TouristLodgingConsumePerDay;
		componentData.m_TouristServiceConsumePerDay = m_TouristServiceConsumePerDay;
		entityManager.SetComponentData(entity, componentData);
	}
```


