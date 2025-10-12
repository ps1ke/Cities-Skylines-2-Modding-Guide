# Game.Simulation.EmergencyShelterAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Unity.Entities.EntityQuery m_VehiclePrefabQuery`  
- `private Unity.Entities.EntityArchetype m_EvacuationRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData`  
- `private Game.Simulation.EmergencyShelterAISystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_1553762682_0`  
- `private Unity.Entities.EntityQuery __query_1553762682_1`  

## Constructors

- `public EmergencyShelterAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.EmergencyShelterAISystem+EmergencyShelterAction`  
- `Game.Simulation.EmergencyShelterAISystem+EmergencyShelterTickJob`  
- `Game.Simulation.EmergencyShelterAISystem+EmergencyShelterActionJob`  
- `Game.Simulation.EmergencyShelterAISystem+TypeHandle`  

