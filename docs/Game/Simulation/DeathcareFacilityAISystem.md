# Game.Simulation.DeathcareFacilityAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_FacilityQuery`  
- `private Unity.Entities.EntityQuery m_HealthcareVehiclePrefabQuery`  
- `private Unity.Entities.EntityQuery m_HealthcareSettingsQuery`  
- `private Unity.Entities.EntityArchetype m_HealthcareRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.BudgetSystem m_BudgetSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Prefabs.HealthcareVehicleSelectData m_HealthcareVehicleSelectData`  
- `private Game.Simulation.DeathcareFacilityAISystem+TypeHandle __TypeHandle`  

## Constructors

- `public DeathcareFacilityAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.DeathcareFacilityAISystem+DeathcareFacilityAction`  
- `Game.Simulation.DeathcareFacilityAISystem+DeathcareFacilityTickJob`  
- `Game.Simulation.DeathcareFacilityAISystem+DeathcareFacilityActionJob`  
- `Game.Simulation.DeathcareFacilityAISystem+TypeHandle`  

