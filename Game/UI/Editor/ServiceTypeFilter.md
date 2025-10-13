# Game.UI.Editor.EditorAssetCategorySystem+ServiceTypeFilter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter`  

## Code

```csharp
public class ServiceTypeFilter : Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter
{
    private Unity.Entities.Entity m_Service;

    public ServiceTypeFilter(Unity.Entities.Entity service);

    public System.Boolean Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem _);
}
```


## Fields

- `private Unity.Entities.Entity m_Service`  

```csharp
private Unity.Entities.Entity m_Service;
```


## Constructors

- `public ServiceTypeFilter(Unity.Entities.Entity service)`  

```csharp
public ServiceTypeFilter(Unity.Entities.Entity service);
```


## Methods

- `public Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem _) : System.Boolean`  

```csharp
public System.Boolean Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem _);
```


