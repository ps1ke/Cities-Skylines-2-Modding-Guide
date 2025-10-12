# Game.UI.InGame.PrefabUISystem+Int2PropertyBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

## Fields

- `public readonly System.String m_LabelId`  
- `public readonly System.String m_Unit`  
- `public readonly System.Boolean m_Signed`  
- `public readonly System.String m_Icon`  
- `public readonly System.String m_ValueIcon`  

## Constructors

- `protected Int2PropertyBinder(System.String labelId, System.String unit, System.Boolean signed = False, System.String icon = null, System.String valueIcon = null)`  

## Methods

- `public Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public abstract GetValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : Unity.Mathematics.int2`  
- `public abstract Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

