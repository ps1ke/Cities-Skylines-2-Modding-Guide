# Game.UI.InGame.PrefabUISystem+RequiredResourceBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.PrefabUISystem+StringPropertyBinder`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  

## Constructors

- `public RequiredResourceBinder(Game.Prefabs.ResourceSystem resourceSystem)`  

## Methods

- `private GetExtractorType(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : Game.Areas.MapFeature`  
- `public virtual GetValueId(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.String`  
- `public virtual Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  
- `private RequiresWater(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, Game.Prefabs.AllowedWaterTypes& types) : System.Boolean`  

