# Game.UI.Editor.EditorAssetCategorySystem+MaintenanceTypeFilter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter`  

## Code

```csharp
public class MaintenanceTypeFilter : Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter
{
    public Game.Simulation.MaintenanceType m_Type;

    public MaintenanceTypeFilter();

    public System.Boolean Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Game.Simulation.MaintenanceType m_Type`  

```csharp
public Game.Simulation.MaintenanceType m_Type;
```


## Constructors

- `public MaintenanceTypeFilter()`  

```csharp
public MaintenanceTypeFilter();
```


## Methods

- `public Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Boolean`  

```csharp
public System.Boolean Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
```


