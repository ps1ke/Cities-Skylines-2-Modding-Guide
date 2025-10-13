# Game.Prefabs.RandomLocalization

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.Localization`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class RandomLocalization : Game.Prefabs.Localization, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable
{
    public RandomLocalization();

    public virtual System.Void GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    protected virtual System.Int32 GetLocalizationCount();
    public static System.Int32 GetLocalizationIndexCount(Game.Prefabs.PrefabBase prefab, System.String id);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Constructors

- `public RandomLocalization()`  

```csharp
public RandomLocalization();
```


## Methods

- `public virtual GetArchetypeComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetArchetypeComponents(HashSet<ComponentType> components)
	{
		base.GetArchetypeComponents(components);
		components.Add(ComponentType.ReadWrite<RandomLocalizationIndex>());
	}
```

- `protected virtual GetLocalizationCount() : System.Int32`  

```csharp
protected virtual int GetLocalizationCount()
	{
		return GetLocalizationIndexCount(base.prefab, m_LocalizationID);
	}
```

- `public static GetLocalizationIndexCount(Game.Prefabs.PrefabBase prefab, System.String id) : System.Int32`  

```csharp
public static int GetLocalizationIndexCount(PrefabBase prefab, string id)
	{
		int num = -1;
		if (id != null && GameManager.instance.localizationManager.activeDictionary.indexCounts.TryGetValue(id, out var value))
		{
			num = value;
		}
		if (num < 1)
		{
			ComponentBase.baseLog.WarnFormat(prefab, "Warning: localizationID {0} not found for {1}", id, prefab.name);
		}
		return num;
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<LocalizationCount>());
	}
```

- `public virtual Initialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void Initialize(EntityManager entityManager, Entity entity)
	{
		base.Initialize(entityManager, entity);
		int localizationCount = GetLocalizationCount();
		entityManager.GetBuffer<LocalizationCount>(entity).Add(new LocalizationCount
		{
			m_Count = localizationCount
		});
	}
```


