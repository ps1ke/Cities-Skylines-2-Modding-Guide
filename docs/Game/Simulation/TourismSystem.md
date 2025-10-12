# Game.Simulation.TourismSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Mathematics.int2 m_CachedLodging`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Simulation.CountHouseholdDataSystem m_CountHouseholdDataSystem`  
- `private Unity.Entities.EntityQuery m_AttractivenessProviderGroup`  
- `private Unity.Entities.EntityQuery m_HotelGroup`  
- `private Unity.Entities.EntityQuery m_ParameterQuery`  
- `private Game.Simulation.TourismSystem+TypeHandle __TypeHandle`  

## Constructors

- `public TourismSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetRawTouristProbability(System.Int32 attractiveness) : System.Single`  
- `public static GetTouristProbability(Game.Prefabs.AttractivenessParameterData parameterData, System.Int32 attractiveness, Game.Simulation.ClimateSystem+WeatherClassification weatherClassification, System.Single temperature, System.Single precipitation, System.Boolean isRaining, System.Boolean isSnowing) : System.Single`  
- `public static GetTouristRandomStay() : System.Int32`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public static GetWeatherEffect(Game.Prefabs.AttractivenessParameterData parameterData, Game.Simulation.ClimateSystem+WeatherClassification weatherClassification, System.Single temperature, System.Single precipitation, System.Boolean isRaining, System.Boolean isSnowing) : System.Single`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.TourismSystem+TourismJob`  
- `Game.Simulation.TourismSystem+TypeHandle`  

