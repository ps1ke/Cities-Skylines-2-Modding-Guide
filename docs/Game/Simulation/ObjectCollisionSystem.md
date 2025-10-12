# Game.Simulation.ObjectCollisionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_ObjectQuery`  
- `private Unity.Entities.EntityQuery m_ConfigQuery`  
- `private Unity.Entities.EntityArchetype m_EventImpactArchetype`  
- `private Unity.Entities.EntityArchetype m_DamageEventArchetype`  
- `private Unity.Entities.EntityArchetype m_DestroyEventArchetype`  
- `private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData`  
- `private Game.Simulation.ObjectCollisionSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ObjectCollisionSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.ObjectCollisionSystem+Collision`  
- `Game.Simulation.ObjectCollisionSystem+FindCollisionsJob`  
- `Game.Simulation.ObjectCollisionSystem+ResolveCollisionsJob`  
- `Game.Simulation.ObjectCollisionSystem+TypeHandle`  

