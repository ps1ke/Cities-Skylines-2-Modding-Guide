# Game.Simulation.CriminalSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Unity.Entities.EntityQuery m_CriminalQuery`  
- `private Unity.Entities.EntityQuery m_PoliceConfigQuery`  
- `private Unity.Entities.EntityArchetype m_AddAccidentSiteArchetype`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Simulation.CriminalSystem+TypeHandle __TypeHandle`  
- `public static const System.UInt32 SYSTEM_UPDATE_INTERVAL`  

## Constructors

- `public CriminalSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CriminalSystem+CrimeData`  
- `Game.Simulation.CriminalSystem+CriminalJob`  
- `Game.Simulation.CriminalSystem+CrimeJob`  
- `Game.Simulation.CriminalSystem+TypeHandle`  

