# Game.Simulation.TouristLeaveSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_TouristHouseholdGroup`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.Simulation.TouristLeaveSystem+TypeHandle __TypeHandle`  

## Constructors

- `public TouristLeaveSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.TouristLeaveSystem+TouristLeaveJob`  
- `Game.Simulation.TouristLeaveSystem+TypeHandle`  

