# Game.Simulation.WeatherHazardSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_PhenomenonQuery`  
- `private Game.Simulation.WeatherHazardSystem+TypeHandle __TypeHandle`  
- `private static const System.Int32 UPDATES_PER_DAY`  

## Constructors

- `public WeatherHazardSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.WeatherHazardSystem+WeatherHazardJob`  
- `Game.Simulation.WeatherHazardSystem+TypeHandle`  

