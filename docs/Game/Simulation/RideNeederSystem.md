# Game.Simulation.RideNeederSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_NeederQuery`  
- `private Unity.Entities.EntityArchetype m_VehicleRequestArchetype`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.RideNeederSystem+TypeHandle __TypeHandle`  
- `private static const System.UInt32 UPDATE_INTERVAL`  

## Constructors

- `public RideNeederSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.RideNeederSystem+RideNeederTickJob`  
- `Game.Simulation.RideNeederSystem+TypeHandle`  

