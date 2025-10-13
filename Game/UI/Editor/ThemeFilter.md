# Game.UI.Editor.EditorAssetCategorySystem+ThemeFilter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter`  

## Code

```csharp
public class ThemeFilter : Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter
{
    public Unity.Entities.Entity m_Theme;
    public System.Boolean m_DefaultResult;

    public ThemeFilter();

    public System.Boolean Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Unity.Entities.Entity m_Theme`  

```csharp
public Unity.Entities.Entity m_Theme;
```

- `public System.Boolean m_DefaultResult`  

```csharp
public System.Boolean m_DefaultResult;
```


## Constructors

- `public ThemeFilter()`  

```csharp
public ThemeFilter();
```


## Methods

- `public Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Boolean`  

```csharp
public System.Boolean Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
```


