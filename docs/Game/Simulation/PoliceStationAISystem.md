# Game.Simulation.PoliceStationAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Unity.Entities.EntityQuery m_VehiclePrefabQuery`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Prefabs.PoliceCarSelectData m_PoliceCarSelectData`  
- `private Unity.Entities.EntityArchetype m_PrisonerTransportRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_PolicePatrolRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_PoliceEmergencyRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingAircraftAddTypes`  
- `private Game.Simulation.PoliceStationAISystem+TypeHandle __TypeHandle`  

## Constructors

- `public PoliceStationAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.PoliceStationAISystem+PoliceStationAction`  
- `Game.Simulation.PoliceStationAISystem+PoliceStationTickJob`  
- `Game.Simulation.PoliceStationAISystem+PoliceStationActionJob`  
- `Game.Simulation.PoliceStationAISystem+TypeHandle`  

