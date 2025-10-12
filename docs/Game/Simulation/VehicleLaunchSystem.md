# Game.Simulation.VehicleLaunchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_LaunchQuery`  
- `private Game.Simulation.VehicleLaunchSystem+TypeHandle __TypeHandle`  
- `private static const System.UInt32 UPDATE_INTERVAL`  

## Constructors

- `public VehicleLaunchSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.VehicleLaunchSystem+VehicleLaunchJob`  
- `Game.Simulation.VehicleLaunchSystem+TypeHandle`  

