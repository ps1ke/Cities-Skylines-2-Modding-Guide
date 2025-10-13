# Game.Prefabs.UIStatisticsGroupPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.UIGroupPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class UIStatisticsGroupPrefab : Game.Prefabs.UIGroupPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public UnityEngine.Color m_Color;
    public Game.Prefabs.UIStatisticsCategoryPrefab m_Category;
    public Game.City.StatisticUnitType m_UnitType;
    public System.Boolean m_Stacked;

    public UIStatisticsGroupPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public UnityEngine.Color m_Color`  

```csharp
public UnityEngine.Color m_Color;
```

- `public Game.Prefabs.UIStatisticsCategoryPrefab m_Category`  

```csharp
public Game.Prefabs.UIStatisticsCategoryPrefab m_Category;
```

- `public Game.City.StatisticUnitType m_UnitType`  

```csharp
public Game.City.StatisticUnitType m_UnitType;
```

- `public System.Boolean m_Stacked`  

```csharp
public System.Boolean m_Stacked;
```


## Constructors

- `public UIStatisticsGroupPrefab()`  

```csharp
public UIStatisticsGroupPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_Category != null)
		{
			prefabs.Add(m_Category);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<UIStatisticsGroupData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		Entity category = ((m_Category != null) ? existingSystemManaged.GetEntity(m_Category) : Entity.Null);
		entityManager.SetComponentData(entity, new UIStatisticsGroupData
		{
			m_Category = category,
			m_Color = m_Color,
			m_UnitType = m_UnitType,
			m_Stacked = m_Stacked
		});
	}
```


