# Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** interface abstract public  


## Code

```csharp
public abstract interface IEditorAssetCategoryFilter
{
    public abstract System.Boolean Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Methods

- `public abstract Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Boolean`  

```csharp
public abstract System.Boolean Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
```


