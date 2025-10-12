# Game.Simulation.SicknessCheckSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `public readonly System.Int32 kUpdatesPerDay`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.TaxSystem m_TaxSystem`  
- `private Unity.Entities.EntityArchetype m_AddProblemArchetype`  
- `private Unity.Entities.EntityQuery m_CitizenQuery`  
- `private Unity.Entities.EntityQuery m_EventQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Game.Simulation.SicknessCheckSystem+TypeHandle __TypeHandle`  

## Constructors

- `public SicknessCheckSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.SicknessCheckSystem+SicknessCheckJob`  
- `Game.Simulation.SicknessCheckSystem+TypeHandle`  

