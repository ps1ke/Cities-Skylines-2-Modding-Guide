# Game.UI.InGame.PrefabUISystem+ConstructionCostBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.PrefabUISystem+ComponentIntRangePropertyBinder<Game.Prefabs.PlaceableObjectData>`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

## Code

```csharp
public class ConstructionCostBinder : Game.UI.InGame.PrefabUISystem+ComponentIntRangePropertyBinder<Game.Prefabs.PlaceableObjectData>, Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder
{
    public ConstructionCostBinder();

    public virtual System.Int32 GetMaxValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Int32 GetMinValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Constructors

- `public ConstructionCostBinder()`  

```csharp
public ConstructionCostBinder();
```


## Methods

- `public virtual GetMaxValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Int32`  

```csharp
public virtual System.Int32 GetMaxValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public virtual GetMinValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Int32`  

```csharp
public virtual System.Int32 GetMinValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


## Nested types

- `Game.UI.InGame.PrefabUISystem+ConstructionCostBinder+<>c`  

