# Game.Simulation.AircraftMoveSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Rendering.LightingSystem m_LightingSystem`  
- `private Unity.Entities.EntityQuery m_AircraftQuery`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.AircraftMoveSystem+TypeHandle __TypeHandle`  

## Constructors

- `public AircraftMoveSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.AircraftMoveSystem+AircraftMoveJob`  
- `Game.Simulation.AircraftMoveSystem+TypeHandle`  

