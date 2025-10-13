# Game.UI.Editor.EditorAssetCategorySystem+PublicTransportTypeFilter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter`  

## Code

```csharp
public class PublicTransportTypeFilter : Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter
{
    public Game.Prefabs.TransportType m_TransportType;
    public Game.Prefabs.PublicTransportPurpose m_Purpose;

    public PublicTransportTypeFilter();

    public System.Boolean Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
}
```


## Fields

- `public Game.Prefabs.TransportType m_TransportType`  

```csharp
public Game.Prefabs.TransportType m_TransportType;
```

- `public Game.Prefabs.PublicTransportPurpose m_Purpose`  

```csharp
public Game.Prefabs.PublicTransportPurpose m_Purpose;
```


## Constructors

- `public PublicTransportTypeFilter()`  

```csharp
public PublicTransportTypeFilter();
```


## Methods

- `public Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem) : System.Boolean`  

```csharp
public System.Boolean Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem prefabSystem);
```


