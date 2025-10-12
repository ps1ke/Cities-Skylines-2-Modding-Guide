# Game.UI.InGame.NaturalResourcesInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableOil`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableOre`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableForest`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableFertility`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_ForestRenewalRate`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_FertilityRenewalRate`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_FishRenewalRate`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AvailableFish`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_OilExtractionRate`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_OreExtractionRate`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_ForestExtractionRate`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_FertilityExtractionRate`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_FishExtractionRate`  
- `private Unity.Entities.EntityQuery m_MapTileQuery`  
- `private Unity.Entities.EntityQuery m_ExtractorQuery`  
- `private Unity.Collections.NativeArray<System.Single> m_Results`  
- `private Game.UI.InGame.NaturalResourcesInfoviewUISystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_1701516005_0`  
- `private static const System.String kGroup`  

## Properties

- `public Game.GameMode gameMode { get }`  
- `protected System.Boolean Active { protected get }`  

## Constructors

- `public NaturalResourcesInfoviewUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  

## Nested types

- `Game.UI.InGame.NaturalResourcesInfoviewUISystem+Result`  
- `Game.UI.InGame.NaturalResourcesInfoviewUISystem+UpdateResourcesJob`  
- `Game.UI.InGame.NaturalResourcesInfoviewUISystem+UpdateExtractionJob`  
- `Game.UI.InGame.NaturalResourcesInfoviewUISystem+TypeHandle`  

