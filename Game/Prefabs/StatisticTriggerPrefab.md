# Game.Prefabs.StatisticTriggerPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class StatisticTriggerPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.StatisticTriggerType m_Type;
    public Game.Prefabs.StatisticsPrefab m_StatisticPrefab;
    public System.Int32 m_StatisticParameter;
    public Game.Prefabs.StatisticsPrefab m_NormalizeWithPrefab;
    public System.Int32 m_NormalizeWithParameter;
    public System.Int32 m_TimeFrame;
    public System.Int32 m_MinSamples;

    public StatisticTriggerPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.StatisticTriggerType m_Type`  

```csharp
public Game.Prefabs.StatisticTriggerType m_Type;
```

- `public Game.Prefabs.StatisticsPrefab m_StatisticPrefab`  

```csharp
public Game.Prefabs.StatisticsPrefab m_StatisticPrefab;
```

- `public System.Int32 m_StatisticParameter`  

```csharp
public System.Int32 m_StatisticParameter;
```

- `public Game.Prefabs.StatisticsPrefab m_NormalizeWithPrefab`  

```csharp
public Game.Prefabs.StatisticsPrefab m_NormalizeWithPrefab;
```

- `public System.Int32 m_NormalizeWithParameter`  

```csharp
public System.Int32 m_NormalizeWithParameter;
```

- `public System.Int32 m_TimeFrame`  

```csharp
public System.Int32 m_TimeFrame;
```

- `public System.Int32 m_MinSamples`  

```csharp
public System.Int32 m_MinSamples;
```


## Constructors

- `public StatisticTriggerPrefab()`  

```csharp
public StatisticTriggerPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_StatisticPrefab != null)
		{
			prefabs.Add(m_StatisticPrefab);
		}
		if (m_NormalizeWithPrefab != null)
		{
			prefabs.Add(m_NormalizeWithPrefab);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<TriggerData>());
		components.Add(ComponentType.ReadWrite<StatisticTriggerData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem orCreateSystemManaged = entityManager.World.GetOrCreateSystemManaged<PrefabSystem>();
		StatisticTriggerData componentData = new StatisticTriggerData
		{
			m_Type = m_Type
		};
		if (m_StatisticPrefab != null)
		{
			componentData.m_StatisticEntity = orCreateSystemManaged.GetEntity(m_StatisticPrefab);
		}
		componentData.m_StatisticParameter = m_StatisticParameter;
		if (m_NormalizeWithPrefab != null)
		{
			componentData.m_NormalizeWithPrefab = orCreateSystemManaged.GetEntity(m_NormalizeWithPrefab);
		}
		componentData.m_NormalizeWithParameter = m_NormalizeWithParameter;
		componentData.m_TimeFrame = m_TimeFrame;
		componentData.m_MinSamples = m_MinSamples;
		if ((m_StatisticPrefab != null && m_StatisticPrefab.m_CollectionType == StatisticCollectionType.Daily) || (m_NormalizeWithPrefab != null && m_NormalizeWithPrefab.m_CollectionType == StatisticCollectionType.Daily))
		{
			componentData.m_MinSamples = math.max(componentData.m_MinSamples, 32 + math.max(0, m_TimeFrame - 1));
		}
		entityManager.SetComponentData(entity, componentData);
		entityManager.GetBuffer<TriggerData>(entity).Add(new TriggerData
		{
			m_TriggerType = TriggerType.StatisticsValue,
			m_TargetTypes = TargetType.Nothing,
			m_TriggerPrefab = entity
		});
	}
```


