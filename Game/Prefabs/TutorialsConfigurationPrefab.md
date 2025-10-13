# Game.Prefabs.TutorialsConfigurationPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class TutorialsConfigurationPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.TutorialListPrefab m_TutorialsIntroList;
    public Game.Prefabs.FeaturePrefab m_MapTilesPrefab;

    public TutorialsConfigurationPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.TutorialListPrefab m_TutorialsIntroList`  

```csharp
public Game.Prefabs.TutorialListPrefab m_TutorialsIntroList;
```

- `public Game.Prefabs.FeaturePrefab m_MapTilesPrefab`  

```csharp
public Game.Prefabs.FeaturePrefab m_MapTilesPrefab;
```


## Constructors

- `public TutorialsConfigurationPrefab()`  

```csharp
public TutorialsConfigurationPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		prefabs.Add(m_TutorialsIntroList);
		prefabs.Add(m_MapTilesPrefab);
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		components.Add(ComponentType.ReadWrite<TutorialsConfigurationData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		PrefabSystem existingSystemManaged = entityManager.World.GetExistingSystemManaged<PrefabSystem>();
		Entity entity2 = existingSystemManaged.GetEntity(m_TutorialsIntroList);
		Entity entity3 = existingSystemManaged.GetEntity(m_MapTilesPrefab);
		entityManager.SetComponentData(entity, new TutorialsConfigurationData
		{
			m_TutorialsIntroList = entity2,
			m_MapTilesFeature = entity3
		});
	}
```


