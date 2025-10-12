# Game.UI.InGame.TourismInfoviewUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.InGame.InfoviewUISystemBase`  
**Implements:** `Game.Serialization.IPreDeserialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.IndicatorValue> m_Attractiveness`  
- `private Colossal.UI.Binding.ValueBinding<System.Int32> m_TourismRate`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_AverageHotelPrice`  
- `private Colossal.UI.Binding.ValueBinding<System.Single> m_WeatherEffect`  
- `private Unity.Entities.EntityQuery m_HotelQuery`  
- `private Unity.Entities.EntityQuery m_HotelModifiedQuery`  
- `private Unity.Collections.NativeArray<System.Int32> m_Results`  
- `private Game.UI.InGame.TourismInfoviewUISystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_1647950437_0`  
- `private static const System.String kGroup`  

## Properties

- `protected System.Boolean Active { protected get }`  
- `protected System.Boolean Modified { protected get }`  

## Constructors

- `public TourismInfoviewUISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual PerformUpdate() : System.Void`  
- `private UpdateAttractiveness() : System.Void`  
- `private UpdateAverageHotelPrice() : System.Void`  
- `private UpdateTourismRate() : System.Void`  
- `private UpdateWeatherEffect() : System.Void`  

## Nested types

- `Game.UI.InGame.TourismInfoviewUISystem+Result`  
- `Game.UI.InGame.TourismInfoviewUISystem+CalculateAverageHotelPriceJob`  
- `Game.UI.InGame.TourismInfoviewUISystem+TypeHandle`  

