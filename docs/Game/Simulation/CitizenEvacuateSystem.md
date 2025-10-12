# Game.Simulation.CitizenEvacuateSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_InDangerQuery`  
- `private Unity.Entities.EntityQuery m_CitizenQuery`  
- `private Game.Simulation.CitizenEvacuateSystem+TypeHandle __TypeHandle`  

## Constructors

- `public CitizenEvacuateSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CitizenEvacuateSystem+CitizenEvacuateJob`  
- `Game.Simulation.CitizenEvacuateSystem+TypeHandle`  

