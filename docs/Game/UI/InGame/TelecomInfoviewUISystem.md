# Game.UI.InGame.TelecomInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Fields

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Unity.Entities.EntityQuery m_TelecomQuery`  
- `private Unity.Entities.EntityQuery m_TelecomModifiedQuery`  
- `private Unity.Entities.EntityQuery m_DensityQuery`  
- `private Unity.Collections.NativeArray<Game.Simulation.TelecomCoverage> m_Coverage`  
- `private Unity.Collections.NativeArray<Game.Simulation.TelecomStatus> m_Status`  
- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_NetworkAvailability`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  
- `protected System.Boolean Modified { protected get }`  

## Constructors

- `public TelecomInfoviewUISystem()`  

## Methods

- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  

