# Game.UI.InGame.PrefabUISystem+StringPropertyBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

## Fields

- `public readonly System.String m_LabelId`  
- `public readonly System.String m_Icon`  
- `public readonly System.String m_ValueIcon`  

## Constructors

- `protected StringPropertyBinder(System.String labelId, System.String icon = null, System.String valueIcon = null)`  

## Methods

- `public Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public abstract GetValueId(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.String`  
- `public abstract Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

