# Game.UI.Editor.EditorAssetCategorySystem+ZoneTypeFilter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter`  

## Code

```csharp
public class ZoneTypeFilter : Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter
{
    private Unity.Entities.Entity m_Zone;

    public ZoneTypeFilter(Unity.Entities.Entity zone);

    public System.Boolean Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem _);
}
```


## Fields

- `private Unity.Entities.Entity m_Zone`  

```csharp
private Unity.Entities.Entity m_Zone;
```


## Constructors

- `public ZoneTypeFilter(Unity.Entities.Entity zone)`  

```csharp
public ZoneTypeFilter(Unity.Entities.Entity zone);
```


## Methods

- `public Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem _) : System.Boolean`  

```csharp
public System.Boolean Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem _);
```


