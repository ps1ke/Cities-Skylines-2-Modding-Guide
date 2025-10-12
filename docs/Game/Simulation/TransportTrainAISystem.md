# Game.Simulation.TransportTrainAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Achievements.AchievementTriggerSystem m_AchievementTriggerSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Unity.Entities.EntityQuery m_VehicleQuery`  
- `private Unity.Entities.EntityQuery m_CarriagePrefabQuery`  
- `private Unity.Entities.EntityArchetype m_TransportVehicleRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  
- `private Unity.Entities.ComponentTypeSet m_MovingToParkedTrainRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_MovingToParkedTrainAddTypes`  
- `private Game.Prefabs.TransportTrainCarriageSelectData m_TransportTrainCarriageSelectData`  
- `private Game.Simulation.TransportBoardingHelpers+BoardingLookupData m_BoardingLookupData`  
- `private Game.Simulation.TransportTrainAISystem+TypeHandle __TypeHandle`  

## Constructors

- `public TransportTrainAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.TransportTrainAISystem+TransportTrainTickJob`  
- `Game.Simulation.TransportTrainAISystem+TypeHandle`  

