# Game.Simulation.PolicePatrolDispatchSystem

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
- `private Unity.Entities.EntityQuery m_PoliceConfigurationQuery`  
- `private Game.Simulation.PolicePatrolDispatchSystem+TypeHandle __TypeHandle`  

## Constructors

- `public PolicePatrolDispatchSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.PolicePatrolDispatchSystem+VehicleDispatch`  
- `Game.Simulation.PolicePatrolDispatchSystem+PoliceDispatchJob`  
- `Game.Simulation.PolicePatrolDispatchSystem+DispatchVehiclesJob`  
- `Game.Simulation.PolicePatrolDispatchSystem+TypeHandle`  

