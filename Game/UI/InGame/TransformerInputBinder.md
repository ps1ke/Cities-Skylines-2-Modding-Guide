# Game.UI.InGame.PrefabUISystem+TransformerInputBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.PrefabUISystem+StringPropertyBinder`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

## Code

```csharp
public class TransformerInputBinder : Game.UI.InGame.PrefabUISystem+StringPropertyBinder, Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder
{
    public TransformerInputBinder();

    public virtual System.String GetValueId(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
}
```


## Constructors

- `public TransformerInputBinder()`  

```csharp
public TransformerInputBinder();
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


