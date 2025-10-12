# Game.Simulation.TrafficSpawnerAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Unity.Entities.EntityQuery m_PersonalCarQuery`  
- `private Unity.Entities.EntityQuery m_TransportVehicleQuery`  
- `private Unity.Entities.EntityQuery m_CreaturePrefabQuery`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Prefabs.VehicleCapacitySystem m_VehicleCapacitySystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityArchetype m_TrafficRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  
- `private Unity.Entities.ComponentTypeSet m_CurrentLaneTypesRelative`  
- `private Game.Prefabs.PersonalCarSelectData m_PersonalCarSelectData`  
- `private Game.Prefabs.TransportVehicleSelectData m_TransportVehicleSelectData`  
- `private Game.Simulation.TrafficSpawnerAISystem+TypeHandle __TypeHandle`  

## Constructors

- `public TrafficSpawnerAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.TrafficSpawnerAISystem+TrafficSpawnerTickJob`  
- `Game.Simulation.TrafficSpawnerAISystem+TypeHandle`  

