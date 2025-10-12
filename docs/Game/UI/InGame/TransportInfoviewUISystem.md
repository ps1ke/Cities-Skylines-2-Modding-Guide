# Game.UI.InGame.TransportInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

## Fields

- `private Game.Prefabs.UnlockSystem m_UnlockSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.UI.InGame.PrefabUISystem m_PrefabUISystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Unity.Entities.EntityQuery m_ConfigQuery`  
- `private Unity.Entities.EntityQuery m_LineQuery`  
- `private Unity.Entities.EntityQuery m_ModifiedLineQuery`  
- `private Colossal.UI.Binding.RawValueBinding m_Summaries`  
- `private Game.Prefabs.UITransportConfigurationPrefab m_Config`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  
- `protected System.Boolean Modified { protected get }`  

## Constructors

- `public TransportInfoviewUISystem()`  

## Methods

- `private BindSummaries(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  

## Nested types

- `Game.UI.InGame.TransportInfoviewUISystem+PassengerSummary`  
- `Game.UI.InGame.TransportInfoviewUISystem+CargoSummary`  

