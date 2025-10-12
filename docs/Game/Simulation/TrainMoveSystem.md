# Game.Simulation.TrainMoveSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Rendering.LightingSystem m_LightingSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_TrainQuery`  
- `private Unity.Entities.EntityQuery m_LayoutQuery`  
- `private Game.Simulation.TrainMoveSystem+TypeHandle __TypeHandle`  

## Constructors

- `public TrainMoveSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.TrainMoveSystem+UpdateTransformDataJob`  
- `Game.Simulation.TrainMoveSystem+UpdateLayoutDataJob`  
- `Game.Simulation.TrainMoveSystem+TypeHandle`  

