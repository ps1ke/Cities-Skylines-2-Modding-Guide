# Game.Simulation.WaitingPassengersSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_StopQuery`  
- `private Unity.Entities.EntityQuery m_ResidentQuery`  
- `private Game.Simulation.WaitingPassengersSystem+TypeHandle __TypeHandle`  

## Constructors

- `public WaitingPassengersSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.WaitingPassengersSystem+ClearWaitingPassengersJob`  
- `Game.Simulation.WaitingPassengersSystem+CountWaitingPassengersJob`  
- `Game.Simulation.WaitingPassengersSystem+TickWaitingPassengersJob`  
- `Game.Simulation.WaitingPassengersSystem+TypeHandle`  

