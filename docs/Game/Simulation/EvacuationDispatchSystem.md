# Game.Simulation.EvacuationDispatchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Unity.Entities.EntityQuery m_RequestQuery`  
- `private Game.Simulation.EvacuationDispatchSystem+TypeHandle __TypeHandle`  

## Constructors

- `public EvacuationDispatchSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.EvacuationDispatchSystem+VehicleDispatch`  
- `Game.Simulation.EvacuationDispatchSystem+EvacuationDispatchJob`  
- `Game.Simulation.EvacuationDispatchSystem+DispatchVehiclesJob`  
- `Game.Simulation.EvacuationDispatchSystem+TypeHandle`  

