# Game.UI.InGame.PollutionInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.AirPollutionSystem m_AirPollutionSystem`  
- `private Game.Simulation.GroundPollutionSystem m_GroundPollutionSystem`  
- `private Game.Simulation.NoisePollutionSystem m_NoisePollutionSystem`  
- `protected Game.Simulation.CitySystem m_CitySystem`  
- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageGroundPollution`  
- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageWaterPollution`  
- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageAirPollution`  
- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_AverageNoisePollution`  
- `private Unity.Entities.EntityQuery m_HouseholdQuery`  
- `private Unity.Collections.NativeArray<System.Int32> m_Results`  
- `private Game.UI.InGame.PollutionInfoviewUISystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_374463591_0`  
- `private static const System.String kGroup`  

## Properties

- `public Game.GameMode gameMode { get }`  
- `protected System.Boolean Active { protected get }`  

## Constructors

- `public PollutionInfoviewUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  
- `private ResetResults() : System.Void`  

## Nested types

- `Game.UI.InGame.PollutionInfoviewUISystem+Result`  
- `Game.UI.InGame.PollutionInfoviewUISystem+CalculateAveragePollutionJob`  
- `Game.UI.InGame.PollutionInfoviewUISystem+TypeHandle`  

