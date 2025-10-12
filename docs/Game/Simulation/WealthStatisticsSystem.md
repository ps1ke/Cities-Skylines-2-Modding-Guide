# Game.Simulation.WealthStatisticsSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `protected Unity.Entities.EntityQuery m_HouseholdGroup`  
- `protected Unity.Entities.EntityQuery m_ServiceCompanyGroup`  
- `protected Unity.Entities.EntityQuery m_ProcessingCompanyGroup`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Game.Simulation.WealthStatisticsSystem+TypeHandle __TypeHandle`  

## Constructors

- `public WealthStatisticsSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.WealthStatisticsSystem+ResidentialWealthStatJob`  
- `Game.Simulation.WealthStatisticsSystem+ServiceWealthStatJob`  
- `Game.Simulation.WealthStatisticsSystem+ProcessingWealthStatJob`  
- `Game.Simulation.WealthStatisticsSystem+TypeHandle`  

