# Game.Simulation.ResidentAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Simulation.ResidentAISystem+Actions m_Actions`  
- `private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData`  
- `private Unity.Entities.EntityQuery m_CreatureQuery`  
- `private Unity.Entities.EntityQuery m_GroupCreatureQuery`  
- `private Unity.Entities.EntityQuery m_CarPrefabQuery`  
- `private Unity.Entities.EntityArchetype m_ResetTripArchetype`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrailerAddTypes`  
- `private Unity.Collections.NativeArray<System.Int32> m_DeletedResidents`  
- `private Game.Simulation.ResidentAISystem+TypeHandle __TypeHandle`  

## Constructors

- `public ResidentAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.ResidentAISystem+Actions`  
- `Game.Simulation.ResidentAISystem+Boarding`  
- `Game.Simulation.ResidentAISystem+ResidentAction`  
- `Game.Simulation.ResidentAISystem+BoardingType`  
- `Game.Simulation.ResidentAISystem+ResidentActionType`  
- `Game.Simulation.ResidentAISystem+DeletedResidentType`  
- `Game.Simulation.ResidentAISystem+ResidentTickJob`  
- `Game.Simulation.ResidentAISystem+BoardingJob`  
- `Game.Simulation.ResidentAISystem+ResidentActionJob`  
- `Game.Simulation.ResidentAISystem+TypeHandle`  

