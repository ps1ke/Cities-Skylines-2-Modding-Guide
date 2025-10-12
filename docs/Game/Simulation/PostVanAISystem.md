# Game.Simulation.PostVanAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Unity.Entities.EntityQuery m_VehicleQuery`  
- `private Unity.Entities.EntityQuery m_PostConfigurationQuery`  
- `private Unity.Entities.EntityArchetype m_PostVanRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  
- `private Unity.Entities.ComponentTypeSet m_MovingToParkedCarRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_MovingToParkedAddTypes`  
- `private Game.Simulation.PostVanAISystem+TypeHandle __TypeHandle`  

## Constructors

- `public PostVanAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.PostVanAISystem+MailActionType`  
- `Game.Simulation.PostVanAISystem+MailAction`  
- `Game.Simulation.PostVanAISystem+PostVanTickJob`  
- `Game.Simulation.PostVanAISystem+MailActionJob`  
- `Game.Simulation.PostVanAISystem+TypeHandle`  

