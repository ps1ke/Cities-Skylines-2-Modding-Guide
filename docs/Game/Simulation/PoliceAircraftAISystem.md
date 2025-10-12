# Game.Simulation.PoliceAircraftAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Unity.Entities.EntityQuery m_VehicleQuery`  
- `private Unity.Entities.EntityArchetype m_PolicePatrolRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_PoliceEmergencyRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  
- `private Unity.Entities.ComponentTypeSet m_MovingToParkedAircraftRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_MovingToParkedAddTypes`  
- `private Game.Simulation.PoliceAircraftAISystem+TypeHandle __TypeHandle`  
- `private static const System.Single MAX_WORK_DISTANCE`  

## Constructors

- `public PoliceAircraftAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.PoliceAircraftAISystem+PoliceAction`  
- `Game.Simulation.PoliceAircraftAISystem+PoliceActionType`  
- `Game.Simulation.PoliceAircraftAISystem+PoliceAircraftTickJob`  
- `Game.Simulation.PoliceAircraftAISystem+PoliceActionJob`  
- `Game.Simulation.PoliceAircraftAISystem+TypeHandle`  

