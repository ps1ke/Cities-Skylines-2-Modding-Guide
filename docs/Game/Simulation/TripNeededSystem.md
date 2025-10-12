# Game.Simulation.TripNeededSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Boolean <debugDisableSpawning>k__BackingField`  
- `private Unity.Entities.EntityQuery m_CitizenGroup`  
- `private Unity.Entities.EntityQuery m_ResidentPrefabGroup`  
- `private Unity.Entities.EntityQuery m_CompanyGroup`  
- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_ResetTripArchetype`  
- `private Unity.Entities.ComponentTypeSet m_HumanSpawnTypes`  
- `private Unity.Entities.ComponentTypeSet m_PathfindTypes`  
- `private Unity.Entities.ComponentTypeSet m_CurrentLaneTypesRelative`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  
- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsCar`  
- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsPublic`  
- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsPedestrian`  
- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsCarShort`  
- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsPublicShort`  
- `private Game.Debug.DebugWatchDistribution m_DebugPathCostsPedestrianShort`  
- `private Game.Debug.DebugWatchDistribution m_DebugPublicTransportDuration`  
- `private Game.Debug.DebugWatchDistribution m_DebugTaxiDuration`  
- `private Game.Debug.DebugWatchDistribution m_DebugPedestrianDuration`  
- `private Game.Debug.DebugWatchDistribution m_DebugCarDuration`  
- `private Game.Debug.DebugWatchDistribution m_DebugPedestrianDurationShort`  
- `private Game.Simulation.TripNeededSystem+TypeHandle __TypeHandle`  
- `private static const System.Int32 UPDATE_INTERVAL`  

## Properties

- `public System.Boolean debugDisableSpawning { get; set }`  

## Constructors

- `public TripNeededSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.TripNeededSystem+CompanyJob`  
- `Game.Simulation.TripNeededSystem+AnimalTargetInfo`  
- `Game.Simulation.TripNeededSystem+PetTargetJob`  
- `Game.Simulation.TripNeededSystem+CitizeLeaveJob`  
- `Game.Simulation.TripNeededSystem+CitizenJob`  
- `Game.Simulation.TripNeededSystem+TypeHandle`  

