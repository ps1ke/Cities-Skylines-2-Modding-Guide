# Game.UI.InGame.PrefabUISystem+WaterConnectionBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.PrefabUISystem+StringPropertyBinder`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

## Code

```csharp
public class WaterConnectionBinder : Game.UI.InGame.PrefabUISystem+StringPropertyBinder, Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder
{
    public WaterConnectionBinder();

    public virtual System.String GetValueId(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Constructors

- `public WaterConnectionBinder()`  

```csharp
public WaterConnectionBinder();
```


## Methods

- `public virtual GetValueId(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.String`  

```csharp
public virtual System.String GetValueId(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public virtual Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public virtual System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


