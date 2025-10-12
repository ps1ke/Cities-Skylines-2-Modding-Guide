# Game.Prefabs.ProcessingRequirementSystem

**Assembly:** `Game`  
**Namespace:** `Game.Prefabs`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.ProcessingCompanySystem m_ProcessingCompanySystem`  
- `private Unity.Entities.EntityQuery m_RequirementQuery`  
- `private Unity.Entities.EntityArchetype m_UnlockEventArchetype`  
- `private Game.Prefabs.ProcessingRequirementSystem+TypeHandle __TypeHandle`  

## Constructors

- `public ProcessingRequirementSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Prefabs.ProcessingRequirementSystem+ProcessingRequirementJob`  
- `Game.Prefabs.ProcessingRequirementSystem+TypeHandle`  

