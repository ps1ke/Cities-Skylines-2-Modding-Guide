# Game.UI.InGame.PrefabUISystem+UpkeepPropertyBinderSystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabPropertyBinder`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Unity.Entities.EntityQuery m_BudgetDataQuery`  

## Constructors

- `public UpkeepPropertyBinderSystem()`  

## Methods

- `public Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `private GetValue(Unity.Entities.Entity entity) : Unity.Mathematics.int2`  
- `public Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

