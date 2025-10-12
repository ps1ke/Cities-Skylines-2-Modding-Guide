# Game.UI.InGame.FireAndRescueInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Buildings.LocalEffectSystem m_LocalEffectSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Simulation.FireHazardSystem m_FireHazardSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Unity.Entities.EntityQuery m_FlammableQuery`  
- `private Unity.Entities.EntityQuery m_FireStationsModifiedQuery`  
- `private Unity.Entities.EntityQuery m_FireConfigQuery`  
- `private Unity.Collections.NativeArray<System.Single> m_Results`  
- `private Game.Simulation.EventHelpers+FireHazardData m_FireHazardData`  
- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageFireHazard`  
- `private Game.UI.InGame.FireAndRescueInfoviewUISystem+TypeHandle __TypeHandle`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  
- `protected System.Boolean Modified { protected get }`  

## Constructors

- `public FireAndRescueInfoviewUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  

## Nested types

- `Game.UI.InGame.FireAndRescueInfoviewUISystem+FireHazardJob`  
- `Game.UI.InGame.FireAndRescueInfoviewUISystem+TypeHandle`  

