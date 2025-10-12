# Game.Simulation.MaintenanceDepotAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_BuildingQuery`  
- `private Unity.Entities.EntityQuery m_VehiclePrefabQuery`  
- `private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Prefabs.MaintenanceVehicleSelectData m_MaintenanceVehicleSelectData`  
- `private Game.Simulation.MaintenanceDepotAISystem+TypeHandle __TypeHandle`  

## Constructors

- `public MaintenanceDepotAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.MaintenanceDepotAISystem+MaintenanceDepotAction`  
- `Game.Simulation.MaintenanceDepotAISystem+MaintenanceDepotTickJob`  
- `Game.Simulation.MaintenanceDepotAISystem+MaintenanceDepotActionJob`  
- `Game.Simulation.MaintenanceDepotAISystem+TypeHandle`  

