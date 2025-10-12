# Game.Simulation.WorkCarAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Unity.Entities.EntityQuery m_VehicleQuery`  
- `private Game.Simulation.WorkCarAISystem+TypeHandle __TypeHandle`  

## Constructors

- `public WorkCarAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.WorkCarAISystem+WorkAction`  
- `Game.Simulation.WorkCarAISystem+WorkCarTickJob`  
- `Game.Simulation.WorkCarAISystem+WorkCarWorkJob`  
- `Game.Simulation.WorkCarAISystem+TypeHandle`  

