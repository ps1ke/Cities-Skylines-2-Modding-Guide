# Game.Simulation.WeatherPhenomenonSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.WindSystem m_WindSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Rendering.ClimateRenderSystem m_ClimateRenderSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_PhenomenonQuery`  
- `private Unity.Entities.EntityArchetype m_FaceWeatherArchetype`  
- `private Unity.Entities.EntityArchetype m_ImpactArchetype`  
- `private Unity.Entities.EntityArchetype m_EndangerArchetype`  
- `private Unity.Entities.EntityArchetype m_EventIgniteArchetype`  
- `private Unity.Entities.EntityQuery m_EDWSBuildingQuery`  
- `private Game.Simulation.WeatherPhenomenonSystem+TypeHandle __TypeHandle`  

## Constructors

- `public WeatherPhenomenonSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.WeatherPhenomenonSystem+WeatherPhenomenonJob`  
- `Game.Simulation.WeatherPhenomenonSystem+TypeHandle`  

