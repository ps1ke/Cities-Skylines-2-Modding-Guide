# Game.UI.InGame.PrefabUISystem+UpkeepModifierBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.PrefabUISystem+IntPropertyBinder`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

## Code

```csharp
public class UpkeepModifierBinder : Game.UI.InGame.PrefabUISystem+IntPropertyBinder, Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder
{
    public UpkeepModifierBinder();

    public virtual System.Int32 GetValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Constructors

- `public UpkeepModifierBinder()`  

```csharp
public UpkeepModifierBinder();
```


## Methods

- `public virtual GetValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Int32`  

```csharp
public virtual System.Int32 GetValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public virtual Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public virtual System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```


