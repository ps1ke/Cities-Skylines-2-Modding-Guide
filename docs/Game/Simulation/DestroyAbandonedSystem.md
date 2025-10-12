# Game.Simulation.DestroyAbandonedSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_AbandonedQuery`  
- `private Unity.Entities.EntityArchetype m_DamageEventArchetype`  
- `private Unity.Entities.EntityArchetype m_DestroyEventArchetype`  
- `private Unity.Entities.EntityQuery m_BuildingSettingsQuery`  
- `private Game.Simulation.DestroyAbandonedSystem+TypeHandle __TypeHandle`  

## Constructors

- `public DestroyAbandonedSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.DestroyAbandonedSystem+DestroyAbandonedJob`  
- `Game.Simulation.DestroyAbandonedSystem+TypeHandle`  

