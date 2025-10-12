# Game.Tools.RecentClearSystem

**Assembly:** `Game`  
**Namespace:** `Game.Tools`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_RecentQuery`  
- `private Game.Tools.RecentClearSystem+TypeHandle __TypeHandle`  

## Constructors

- `public RecentClearSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Tools.RecentClearSystem+ClearRecentJob`  
- `Game.Tools.RecentClearSystem+TypeHandle`  

