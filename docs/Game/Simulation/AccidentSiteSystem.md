# Game.Simulation.AccidentSiteSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_AccidentQuery`  
- `private Unity.Entities.EntityQuery m_ConfigQuery`  
- `private Unity.Entities.EntityArchetype m_PoliceRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_EventImpactArchetype`  
- `private Game.Simulation.AccidentSiteSystem+TypeHandle __TypeHandle`  
- `private static const System.UInt32 UPDATE_INTERVAL`  

## Constructors

- `public AccidentSiteSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.AccidentSiteSystem+AccidentSiteJob`  
- `Game.Simulation.AccidentSiteSystem+TypeHandle`  

