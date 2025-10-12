# Game.Simulation.PostVanDispatchSystem

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
- `private Unity.Entities.EntityQuery m_PostConfigurationQuery`  
- `private Game.Simulation.PostVanDispatchSystem+TypeHandle __TypeHandle`  

## Constructors

- `public PostVanDispatchSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.PostVanDispatchSystem+VehicleDispatch`  
- `Game.Simulation.PostVanDispatchSystem+PostVanDispatchJob`  
- `Game.Simulation.PostVanDispatchSystem+DispatchVehiclesJob`  
- `Game.Simulation.PostVanDispatchSystem+TypeHandle`  

