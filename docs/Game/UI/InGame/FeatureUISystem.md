# Game.UI.InGame.FeatureUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  
- `private Unity.Entities.EntityQuery m_UnlockedFeatureQuery`  
- `private Unity.Entities.EntityQuery m_UnlocksQuery`  
- `private Colossal.UI.Binding.RawValueBinding m_FeaturesBinding`  
- `private static const System.String kGroup`  

## Constructors

- `public FeatureUISystem()`  

## Methods

- `private BindLockedFeatures(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

