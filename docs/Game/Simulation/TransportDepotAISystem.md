# Game.Simulation.TransportDepotAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Unity.Entities.EntityQuery m_VehiclePrefabQuery`  
- `private Unity.Entities.EntityQuery m_EventPrefabQuery`  
- `private Unity.Entities.EntityArchetype m_TransportVehicleRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_TaxiRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingTaxiAddTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingBusAddTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrainAddTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingTrainControllerAddTypes`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData`  
- `private Game.Simulation.TransportDepotAISystem+TypeHandle __TypeHandle`  

## Constructors

- `public TransportDepotAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.TransportDepotAISystem+DepotActionType`  
- `Game.Simulation.TransportDepotAISystem+DepotAction`  
- `Game.Simulation.TransportDepotAISystem+TransportDepotTickJob`  
- `Game.Simulation.TransportDepotAISystem+TransportDepotActionJob`  
- `Game.Simulation.TransportDepotAISystem+TypeHandle`  

