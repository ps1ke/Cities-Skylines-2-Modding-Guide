# Game.Simulation.FireStationAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Unity.Entities.EntityQuery m_VehiclePrefabQuery`  
- `private Unity.Entities.EntityArchetype m_FireRescueRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingAircraftAddTypes`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Prefabs.FireEngineSelectData m_FireEngineSelectData`  
- `private Game.Simulation.FireStationAISystem+TypeHandle __TypeHandle`  

## Constructors

- `public FireStationAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.FireStationAISystem+FireStationAction`  
- `Game.Simulation.FireStationAISystem+FireStationTickJob`  
- `Game.Simulation.FireStationAISystem+FireStationActionJob`  
- `Game.Simulation.FireStationAISystem+TypeHandle`  

