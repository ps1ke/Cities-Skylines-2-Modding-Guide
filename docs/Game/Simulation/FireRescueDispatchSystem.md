# Game.Simulation.FireRescueDispatchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Unity.Entities.EntityQuery m_RequestQuery`  
- `private Game.Simulation.FireRescueDispatchSystem+TypeHandle __TypeHandle`  

## Constructors

- `public FireRescueDispatchSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.FireRescueDispatchSystem+VehicleDispatch`  
- `Game.Simulation.FireRescueDispatchSystem+FireRescueDispatchJob`  
- `Game.Simulation.FireRescueDispatchSystem+DispatchVehiclesJob`  
- `Game.Simulation.FireRescueDispatchSystem+TypeHandle`  

