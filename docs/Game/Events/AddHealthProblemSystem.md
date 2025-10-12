# Game.Events.AddHealthProblemSystem

**Assembly:** `Game`  
**Namespace:** `Game.Events`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.Common.ModificationBarrier4 m_ModificationBarrier`  
- `private Unity.Entities.EntityQuery m_AddHealthProblemQuery`  
- `private Unity.Entities.EntityQuery m_HealthcareSettingsQuery`  
- `private Unity.Entities.EntityQuery m_CitizenQuery`  
- `private Unity.Entities.EntityArchetype m_JournalDataArchetype`  
- `private Game.Triggers.TriggerSystem m_TriggerSystem`  
- `private Game.Simulation.CityStatisticsSystem m_CityStatisticsSystem`  
- `private Game.Events.AddHealthProblemSystem+TypeHandle __TypeHandle`  

## Constructors

- `public AddHealthProblemSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Events.AddHealthProblemSystem+FindCitizensInBuildingJob`  
- `Game.Events.AddHealthProblemSystem+AddHealthProblemJob`  
- `Game.Events.AddHealthProblemSystem+TypeHandle`  

