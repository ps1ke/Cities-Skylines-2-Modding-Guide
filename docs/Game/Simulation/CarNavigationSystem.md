# Game.Simulation.CarNavigationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Simulation.CarNavigationSystem+Actions m_Actions`  
- `private Unity.Entities.EntityQuery m_VehicleQuery`  
- `private Game.Simulation.CarNavigationSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CarNavigationSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CarNavigationSystem+Actions`  
- `Game.Simulation.CarNavigationSystem+UpdateNavigationJob`  
- `Game.Simulation.CarNavigationSystem+UpdateLaneSignalsJob`  
- `Game.Simulation.CarNavigationSystem+UpdateLaneReservationsJob`  
- `Game.Simulation.CarNavigationSystem+TrafficAmbienceEffect`  
- `Game.Simulation.CarNavigationSystem+ApplyTrafficAmbienceJob`  
- `Game.Simulation.CarNavigationSystem+ApplyLaneEffectsJob`  
- `Game.Simulation.CarNavigationSystem+TypeHandle`  

