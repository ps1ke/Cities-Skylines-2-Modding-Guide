# Game.UI.Editor.EditorAssetCategorySystem+SignatureBuildingFilter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter`  

## Code

```csharp
public class SignatureBuildingFilter : Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter
{
    public Game.Zones.AreaType m_AreaType;
    public System.Boolean m_Office;
    public Unity.Entities.Entity m_Theme;

    public SignatureBuildingFilter();

    public System.Boolean Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Game.Zones.AreaType m_AreaType`  

```csharp
public Game.Zones.AreaType m_AreaType;
```

- `public System.Boolean m_Office`  

```csharp
public System.Boolean m_Office;
```

- `public Unity.Entities.Entity m_Theme`  

```csharp
public Unity.Entities.Entity m_Theme;
```


## Constructors

- `public SignatureBuildingFilter()`  

```csharp
public SignatureBuildingFilter();
```


## Methods

- `public Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Boolean`  

```csharp
public System.Boolean Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
```


