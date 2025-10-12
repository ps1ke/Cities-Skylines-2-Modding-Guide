# Game.Achievements.EventAchievementTriggerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Achievements`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Common.ModificationEndBarrier m_ModifiactionEndBarrier`  
- `private Unity.Entities.EntityQuery m_TrackingQuery`  
- `private Unity.Entities.EntityQuery m_CreatedEventQuery`  
- `private Unity.Entities.EntityArchetype m_TrackingArchetype`  
- `private Game.Achievements.EventAchievementTriggerSystem+TypeHandle __TypeHandle`  

## Constructors

- `public EventAchievementTriggerSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private StartTracking(Colossal.PSI.Common.AchievementId id, System.UInt32 startFrame, Unity.Entities.EntityCommandBuffer buffer) : System.Void`  
- `private StopTracking(Game.Achievements.EventAchievementTrackingData data, Unity.Entities.Entity entity, Unity.Entities.EntityCommandBuffer buffer) : System.Void`  

## Nested types

- `Game.Achievements.EventAchievementTriggerSystem+TypeHandle`  

