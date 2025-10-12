# Game.Simulation.InDangerSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_InDangerQuery`  
- `private Unity.Entities.EntityArchetype m_EvacuationRequestArchetype`  
- `private Game.Simulation.InDangerSystem+TypeHandle __TypeHandle`  
- `public static const System.UInt32 UPDATE_INTERVAL`  

## Constructors

- `public InDangerSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.InDangerSystem+InDangerJob`  
- `Game.Simulation.InDangerSystem+TypeHandle`  

