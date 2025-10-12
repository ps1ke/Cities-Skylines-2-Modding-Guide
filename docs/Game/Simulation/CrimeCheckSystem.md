# Game.Simulation.CrimeCheckSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `public readonly System.Int32 kUpdatesPerDay`  
- `public System.Boolean debugFullCrimeMode`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Unity.Entities.EntityQuery m_CitizenQuery`  
- `private Unity.Entities.EntityQuery m_EventQuery`  
- `private Unity.Entities.EntityQuery m_PoliceConfigurationQuery`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Simulation.CrimeCheckSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CrimeCheckSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CrimeCheckSystem+CrimeCheckJob`  
- `Game.Simulation.CrimeCheckSystem+TypeHandle`  

