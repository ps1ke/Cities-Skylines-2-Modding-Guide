# Game.Simulation.HouseholdMoveAwaySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_MoveAwayGroup`  
- `private Unity.Entities.EntityQuery m_OutsideConnectionQuery`  
- `private Unity.Entities.EntityArchetype m_RentEventArchetype`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Simulation.HouseholdMoveAwaySystem+TypeHandle __TypeHandle`  

## Constructors

- `public HouseholdMoveAwaySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.HouseholdMoveAwaySystem+MoveAwayJob`  
- `Game.Simulation.HouseholdMoveAwaySystem+TypeHandle`  

