# Game.UI.InGame.PrefabUISystem+CityModifierBinder

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  
**Implements:** `Game.UI.InGame.PrefabUISystem+IPrefabEffectBinder`  

## Constructors

- `public CityModifierBinder()`  

## Methods

- `public Bind(Colossal.UI.Binding.IJsonWriter binder, Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Void`  
- `public static Bind<T>(Colossal.UI.Binding.IJsonWriter binder, T cityModifiers) : System.Void`  
- `public static GetModifierUnit(Game.Prefabs.CityModifierData data) : System.String`  
- `private static IsValidModifierType(Game.City.CityModifierType type) : System.Boolean`  
- `public Matches(Unity.Entities.EntityManager entityManager, Unity.Entities.Entity entity) : System.Boolean`  

