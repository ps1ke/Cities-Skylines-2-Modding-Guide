# Game.UI.InGame.PrefabUISystem+ElectricityPropertyBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class abstract public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

## Fields

- `public readonly System.String m_LabelId`  

## Constructors

- `protected ElectricityPropertyBinder(System.String labelId)`  

## Methods

- `public Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public abstract GetValue(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity, System.Int32& minCapacity, System.Int32& maxCapacity, Game.Net.Layer& voltageLayers) : System.Void`  
- `public abstract Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

