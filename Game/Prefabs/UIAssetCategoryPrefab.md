# Game.Prefabs.UIAssetCategoryPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.UIGroupPrefab`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class UIAssetCategoryPrefab : Game.Prefabs.UIGroupPrefab, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.UIAssetMenuPrefab m_Menu;

    public UIAssetCategoryPrefab();

    public virtual System.Void GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs);
    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.UIAssetMenuPrefab m_Menu`  

```csharp
public Game.Prefabs.UIAssetMenuPrefab m_Menu;
```


## Constructors

- `public UIAssetCategoryPrefab()`  

```csharp
public UIAssetCategoryPrefab();
```


## Methods

- `public virtual GetDependencies(System.Collections.Generic.List<Game.Prefabs.PrefabBase> prefabs) : System.Void`  

```csharp
public override void GetDependencies(List<PrefabBase> prefabs)
	{
		base.GetDependencies(prefabs);
		if (m_Menu != null)
		{
			prefabs.Add(m_Menu);
		}
	}
```

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> components) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> components)
	{
		base.GetPrefabComponents(components);
		if (m_Menu != null)
		{
			components.Add(ComponentType.ReadWrite<UIAssetCategoryData>());
		}
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		if (m_Menu != null)
		{
			Entity entity2 = entityManager.World.GetExistingSystemManaged<PrefabSystem>().GetEntity(m_Menu);
			entityManager.SetComponentData(entity, new UIAssetCategoryData(entity2));
			m_Menu.AddElement(entityManager, entity);
		}
	}
```


