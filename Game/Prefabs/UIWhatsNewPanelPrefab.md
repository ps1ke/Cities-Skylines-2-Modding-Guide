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
public virtual System.Void GetPrefabComponents(System.Collections.Generic.HashSet<Unity.Entities.ComponentType> prefabComponents);
```

- `public virtual LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  

```csharp
public virtual System.Void LateInitialize(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


## Nested types

- `Game.Prefabs.UIWhatsNewPanelPrefab+UIWhatsNewPanelPage`  
- `Game.Prefabs.UIWhatsNewPanelPrefab+UIWhatsNewPanelPageItem`  
- `Game.Prefabs.UIWhatsNewPanelPrefab+UIWhatsNewPanelImage`  

