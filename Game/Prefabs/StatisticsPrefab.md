# Game.Prefabs.StatisticsPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.ArchetypePrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class StatisticsPrefab : Game.Prefabs.ArchetypePrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.UIStatisticsCategoryPrefab m_Category;
    public Game.Prefabs.UIStatisticsGroupPrefab m_Group;
    public Game.City.StatisticType m_StatisticsType;
    public Game.City.StatisticCollectionType m_CollectionType;
    public Game.City.StatisticUnitType m_UnitType;
    public UnityEngine.Color m_Color;
    public System.Boolean m_Stacked;

    public StatisticsPrefab();

    public static Unity.Entities.Entity CreateInstance(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.ArchetypeData archetypeData, System.Int32 parameter);
    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.UIStatisticsCategoryPrefab m_Category`  

```csharp
public Game.Prefabs.UIStatisticsCategoryPrefab m_Category;
```

- `public Game.Prefabs.UIStatisticsGroupPrefab m_Group`  

```csharp
public Game.Prefabs.UIStatisticsGroupPrefab m_Group;
```

- `public Game.City.StatisticType m_StatisticsType`  

```csharp
public Game.City.StatisticType m_StatisticsType;
```

- `public Game.City.StatisticCollectionType m_CollectionType`  

```csharp
public Game.City.StatisticCollectionType m_CollectionType;
```

- `public Game.City.StatisticUnitType m_UnitType`  

```csharp
public Game.City.StatisticUnitType m_UnitType;
```

- `public UnityEngine.Color m_Color`  

```csharp
public UnityEngine.Color m_Color;
```

- `public System.Boolean m_Stacked`  

```csharp
public System.Boolean m_Stacked;
```


## Constructors

- `public StatisticsPrefab()`  

```csharp
public StatisticsPrefab();
```


## Methods

- `public static CreateInstance(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.ArchetypeData archetypeData, System.Int32 parameter = 0) : Unity.Entities.Entity`  

```csharp
public static Entity CreateInstance(EntityManager entityManager, Entity entity, ArchetypeData archetypeData, int parameter = 0)
	{
		Entity entity2 = entityManager.CreateEntity(archetypeData.m_Archetype);
		PrefabRef componentData = new PrefabRef
		{
			m_Prefab = entity
		};
		entityManager.AddComponentData(entity2, componentData);
		if (entityManager.HasComponent<StatisticParameter>(entity2))
		{
			entityManager.SetComponentData(entity2, new StatisticParameter
			{
				m_Value = parameter
			});
		}
		return entity2;
	}
```

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		components.Add(ComponentType.ReadWrite<CityStatistic>());
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<StatisticsData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		Entity category = ((m_Category != null) ? existingSystemManaged.GetEntity(m_Category) : Entity.Null);
		Entity entity2 = ((m_Group != null) ? existingSystemManaged.GetEntity(m_Group) : Entity.Null);
		StatisticsData componentData = new StatisticsData
		{
			m_Group = entity2,
			m_Category = category,
			m_CollectionType = m_CollectionType,
			m_StatisticType = m_StatisticsType,
			m_UnitType = m_UnitType,
			m_Color = m_Color,
			m_Stacked = m_Stacked
		};
		entityManager.SetComponentData(entity, componentData);
	}
```


