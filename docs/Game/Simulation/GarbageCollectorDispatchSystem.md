# Game.Simulation.GarbageCollectorDispatchSystem

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
- `private Unity.Entities.EntityQuery m_GarbageSettingsQuery`  
- `private Game.Simulation.GarbageCollectorDispatchSystem+TypeHandle __TypeHandle`  

## Constructors

- `public GarbageCollectorDispatchSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.GarbageCollectorDispatchSystem+VehicleDispatch`  
- `Game.Simulation.GarbageCollectorDispatchSystem+GarbageDispatchJob`  
- `Game.Simulation.GarbageCollectorDispatchSystem+DispatchVehiclesJob`  
- `Game.Simulation.GarbageCollectorDispatchSystem+TypeHandle`  

