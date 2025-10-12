# Game.UI.InGame.ClimateUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Fields

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Unity.Entities.EntityQuery m_ClimateQuery`  
- `private Unity.Entities.EntityQuery m_ClimateSeasonQuery`  
- `private Unity.Entities.EntityQuery m_SeasonChangedQuery`  
- `private Colossal.UI.Binding.GetterValueBinding<System.Single> m_TemperatureBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.UI.InGame.WeatherType> m_WeatherBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<System.String> m_SeasonBinding`  
- `private Unity.Entities.Entity m_CurrentSeason`  
- `public static const System.String kGroup`  

## Properties

- `private System.Single m_TemperatureBindingValue { private get }`  

## Constructors

- `public ClimateUISystem()`  

## Methods

- `private <OnCreate>b__11_0() : System.Single`  
- `private static FromWeatherClassification(Game.Simulation.ClimateSystem+WeatherClassification classification) : Game.UI.InGame.WeatherType`  
- `private GetCurrentSeasonNameID() : System.String`  
- `public GetWeather() : Game.UI.InGame.WeatherType`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private static WriteWeatherType(Colossal.UI.Binding.IJsonWriter writer, Game.UI.InGame.WeatherType type) : System.Void`  

