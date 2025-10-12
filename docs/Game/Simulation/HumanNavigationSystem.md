# Game.Simulation.HumanNavigationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Game.Simulation.HumanNavigationSystem+Actions m_Actions`  
- `private Unity.Entities.EntityQuery m_CreatureQuery`  
- `private Game.Simulation.HumanNavigationSystem+TypeHandle __TypeHandle`  

## Constructors

- `public HumanNavigationSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.HumanNavigationSystem+Groups`  
- `Game.Simulation.HumanNavigationSystem+Actions`  
- `Game.Simulation.HumanNavigationSystem+GroupNavigationJob`  
- `Game.Simulation.HumanNavigationSystem+UpdateNavigationJob`  
- `Game.Simulation.HumanNavigationSystem+UpdateLaneSignalsJob`  
- `Game.Simulation.HumanNavigationSystem+TypeHandle`  

