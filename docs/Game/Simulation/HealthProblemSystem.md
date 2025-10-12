# Game.Simulation.HealthProblemSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Unity.Entities.EntityArchetype m_HealthcareRequestArchetype`  
- `private Unity.Entities.EntityArchetype m_JournalDataArchetype`  
- `private Unity.Entities.EntityArchetype m_ResetTripArchetype`  
- `private Unity.Entities.EntityArchetype m_HandleRequestArchetype`  
- `private Unity.Entities.EntityQuery m_HealthProblemQuery`  
- `private Unity.Entities.EntityQuery m_HealthcareSettingsQuery`  
- `private Unity.Entities.EntityQuery m_FireSettingsQuery`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Simulation.HealthProblemSystem+TypeHandle __TypeHandle`  
- `private static const System.UInt32 SYSTEM_UPDATE_INTERVAL`  

## Constructors

- `public HealthProblemSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.HealthProblemSystem+HealthProblemJob`  
- `Game.Simulation.HealthProblemSystem+TypeHandle`  

