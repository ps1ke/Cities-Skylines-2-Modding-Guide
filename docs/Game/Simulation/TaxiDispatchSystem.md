# Game.Simulation.TaxiDispatchSystem

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
- `private Game.Simulation.TaxiDispatchSystem+TypeHandle __TypeHandle`  

## Constructors

- `public TaxiDispatchSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.TaxiDispatchSystem+VehicleDispatch`  
- `Game.Simulation.TaxiDispatchSystem+TaxiDispatchJob`  
- `Game.Simulation.TaxiDispatchSystem+DispatchVehiclesJob`  
- `Game.Simulation.TaxiDispatchSystem+TypeHandle`  

