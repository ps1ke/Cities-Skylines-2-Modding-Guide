# Game.UI.InGame.PrefabUISystem+RequiredResourceBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.PrefabUISystem+StringPropertyBinder`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

## Code

```csharp
public class RequiredResourceBinder : Game.UI.InGame.PrefabUISystem+StringPropertyBinder, Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder
{
    private Game.Prefabs.ResourceSystem m_ResourceSystem;

    public RequiredResourceBinder(Game.Prefabs.ResourceSystem resourceSystem);

    private Game.Areas.MapFeature GetExtractorType(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.String GetValueId(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    public virtual System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
    private System.Boolean RequiresWater(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.AllowedWaterTypes& types);
}
```


## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

```csharp
private Game.Prefabs.ResourceSystem m_ResourceSystem;
```


## Constructors

- `public RequiredResourceBinder(Game.Prefabs.ResourceSystem resourceSystem)`  

```csharp
public RequiredResourceBinder(Game.Prefabs.ResourceSystem resourceSystem);
```


## Methods

- `private GetExtractorType(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : Game.Areas.MapFeature`  

```csharp
private Game.Areas.MapFeature GetExtractorType(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public virtual GetValueId(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.String`  

```csharp
public virtual System.String GetValueId(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `public virtual Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

```csharp
public virtual System.Boolean Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity);
```

- `private RequiresWater(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.AllowedWaterTypes& types) : System.Boolean`  

```csharp
private System.Boolean RequiresWater(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.AllowedWaterTypes& types);
```


