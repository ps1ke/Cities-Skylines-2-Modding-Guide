# Game.Simulation.PostFacilityAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Unity.Entities.EntityQuery m_PostVanPrefabQuery`  
- `private Unity.Entities.EntityQuery m_PostConfigurationQuery`  
- `private Unity.Entities.EntityArchetype m_MailTransferRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_PostVanRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes`  
- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Prefabs.PostVanSelectData m_PostVanSelectData`  
- `private Game.Simulation.PostFacilityAISystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public PostFacilityAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.PostFacilityAISystem+PostFacilityAction`  
- `Game.Simulation.PostFacilityAISystem+PostFacilityTickJob`  
- `Game.Simulation.PostFacilityAISystem+PostFacilityActionJob`  
- `Game.Simulation.PostFacilityAISystem+TypeHandle`  

