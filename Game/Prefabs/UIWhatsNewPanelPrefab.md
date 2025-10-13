# Game.Prefabs.UIWhatsNewPanelPrefab

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.Prefabs.PrefabBase`  
**Implements:** `Colossal.IO.AssetDatabase.IComponentBase`, `System.IComparable`, `UnityEngine.ISerializationCallbackReceiver`, `Colossal.IO.AssetDatabase.IPrefabBase`  

**Attributes:** `ComponentMenu`  

## Code

```csharp
public class UIWhatsNewPanelPrefab : Game.Prefabs.PrefabBase, Colossal.IO.AssetDatabase.IComponentBase, System.IComparable, UnityEngine.ISerializationCallbackReceiver, Colossal.IO.AssetDatabase.IPrefabBase
{
    public Game.Prefabs.UIWhatsNewPanelPrefab+UIWhatsNewPanelPage[] m_Pages;

    public UIWhatsNewPanelPrefab();

    public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> prefabComponents);
    public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Fields

- `public Game.Prefabs.UIWhatsNewPanelPrefab+UIWhatsNewPanelPage[] m_Pages`  

```csharp
public Game.Prefabs.UIWhatsNewPanelPrefab+UIWhatsNewPanelPage[] m_Pages;
```


## Constructors

- `public UIWhatsNewPanelPrefab()`  

```csharp
public UIWhatsNewPanelPrefab();
```


## Methods

- `public virtual GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> prefabComponents) : System.Void`  

```csharp
public override void GetPrefabComponents(HashSet<ComponentType> prefabComponents)
	{
		base.GetPrefabComponents(prefabComponents);
		prefabComponents.Add(ComponentType.ReadWrite<UIWhatsNewPanelPrefabData>());
	}
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public override void LateInitialize(EntityManager entityManager, Entity entity)
	{
		base.LateInitialize(entityManager, entity);
		UIWhatsNewPanelPrefabData componentData = entityManager.GetComponentData<UIWhatsNewPanelPrefabData>(entity);
		DlcRequirement component = base.prefab.GetComponent<DlcRequirement>();
		componentData.m_Id = component.m_Dlc.id;
		entityManager.SetComponentData(entity, componentData);
	}
```


## Nested types

- `Game.Prefabs.UIWhatsNewPanelPrefab+UIWhatsNewPanelPage`  
- `Game.Prefabs.UIWhatsNewPanelPrefab+UIWhatsNewPanelPageItem`  
- `Game.Prefabs.UIWhatsNewPanelPrefab+UIWhatsNewPanelImage`  

