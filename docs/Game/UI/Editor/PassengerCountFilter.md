# Game.UI.Editor.EditorAssetCategorySystem+PassengerCountFilter

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter`  

## Code

```csharp
public class PassengerCountFilter : Game.UI.Editor.EditorAssetCategorySystem+IEditorAssetCategoryFilter
{
    public Game.UI.Editor.EditorAssetCategorySystem+PassengerCountFilter+FilterType m_Type;
    public System.Int32 m_Count;

    public PassengerCountFilter();

    private System.Boolean Check(Game.Prefabs.PersonalCarData data);
    public System.Boolean Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem _);
}
```


## Fields

- `public Game.UI.Editor.EditorAssetCategorySystem+PassengerCountFilter+FilterType m_Type`  

```csharp
public Game.UI.Editor.EditorAssetCategorySystem+PassengerCountFilter+FilterType m_Type;
```

- `public System.Int32 m_Count`  

```csharp
public System.Int32 m_Count;
```


## Constructors

- `public PassengerCountFilter()`  

```csharp
public PassengerCountFilter();
```


## Methods

- `private Check(Game.Prefabs.PersonalCarData data) : System.Boolean`  

```csharp
private System.Boolean Check(Game.Prefabs.PersonalCarData data);
```

- `public Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem _) : System.Boolean`  

```csharp
public System.Boolean Contains(Unity.Entities.Entity prefab, Unity.Entities.EntityManager entityManager, Game.Prefabs.PrefabSystem _);
```


## Nested types

- `Game.UI.Editor.EditorAssetCategorySystem+PassengerCountFilter+FilterType`  

