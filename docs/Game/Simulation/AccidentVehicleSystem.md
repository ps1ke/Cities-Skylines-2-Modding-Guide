# Game.Simulation.AccidentVehicleSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_VehicleQuery`  
- `private Unity.Entities.EntityQuery m_ConfigQuery`  
- `private Unity.Entities.EntityArchetype m_AddAccidentSiteArchetype`  
- `private Unity.Entities.EntityArchetype m_EventIgniteArchetype`  
- `private Unity.Entities.EntityArchetype m_AddImpactArchetype`  
- `private Game.Simulation.AccidentVehicleSystem+TypeHandle __TypeHandle`  
- `private static const System.UInt32 UPDATE_INTERVAL`  

## Constructors

- `public AccidentVehicleSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.AccidentVehicleSystem+AccidentVehicleJob`  
- `Game.Simulation.AccidentVehicleSystem+TypeHandle`  

