# Game.Simulation.GarbageFacilityAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Prefabs.GarbageTruckSelectData m_GarbageTruckSelectData`  
- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Unity.Entities.EntityQuery m_GarbageTruckPrefabQuery`  
- `private Unity.Entities.EntityQuery m_GarbageSettingsQuery`  
- `private Unity.Entities.EntityArchetype m_GarbageTransferRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_GarbageCollectionRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes`  
- `private Game.Simulation.GarbageFacilityAISystem+TypeHandle __TypeHandle`  
- `private static const System.Int32 kUpdatesPerDay`  

## Constructors

- `public GarbageFacilityAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private static CalculateGarbageAmountFactor(System.Int32 garbageAmount, System.Int32 garbageCapacity) : System.Single`  
- `private static CalculateProcessingRate(System.Single maxProcessingRate, System.Single efficiency, System.Int32 garbageAmount, System.Int32 garbageCapacity) : System.Single`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.GarbageFacilityAISystem+GarbageFacilityAction`  
- `Game.Simulation.GarbageFacilityAISystem+GarbageFacilityTickJob`  
- `Game.Simulation.GarbageFacilityAISystem+GarbageFacilityActionJob`  
- `Game.Simulation.GarbageFacilityAISystem+TypeHandle`  

