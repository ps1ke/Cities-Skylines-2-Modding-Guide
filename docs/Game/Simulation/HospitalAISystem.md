# Game.Simulation.HospitalAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Unity.Entities.EntityQuery m_HospitalQuery`  
- `private Unity.Entities.EntityQuery m_HealthcareVehiclePrefabQuery`  
- `private Unity.Entities.EntityQuery m_HealthcareParameterQuery`  
- `private Unity.Entities.EntityArchetype m_HealthcareRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_ResetTripArchetype`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingRemoveTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingCarAddTypes`  
- `private Unity.Entities.ComponentTypeSet m_ParkedToMovingAircraftAddTypes`  
- `private Game.City.CityConfigurationSystem m_CityConfigurationSystem`  
- `private Game.Prefabs.HealthcareVehicleSelectData m_HealthcareVehicleSelectData`  
- `private Game.Simulation.HospitalAISystem+TypeHandle __TypeHandle`  

## Constructors

- `public HospitalAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.HospitalAISystem+HospitalAction`  
- `Game.Simulation.HospitalAISystem+HospitalTickJob`  
- `Game.Simulation.HospitalAISystem+HospitalActionJob`  
- `Game.Simulation.HospitalAISystem+TypeHandle`  

