# Game.Simulation.CompanyMoveAwaySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_CompanyQuery`  
- `private Unity.Entities.EntityQuery m_MovingAwayQuery`  
- `private Unity.Entities.EntityQuery m_EconomyParameterQuery`  
- `private Unity.Entities.EntityArchetype m_RentEventArchetype`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Prefabs.ResourceSystem m_ResourceSystem`  
- `private Game.Simulation.TaxSystem m_TaxSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.Simulation.CompanyMoveAwaySystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_731167828_0`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public CompanyMoveAwaySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CompanyMoveAwaySystem+CheckMoveAwayJob`  
- `Game.Simulation.CompanyMoveAwaySystem+MovingAwayJob`  
- `Game.Simulation.CompanyMoveAwaySystem+TypeHandle`  

