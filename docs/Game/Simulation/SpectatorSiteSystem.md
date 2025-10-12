# Game.Simulation.SpectatorSiteSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_SiteQuery`  
- `private Game.Simulation.SpectatorSiteSystem+TypeHandle __TypeHandle`  
- `private static const System.UInt32 UPDATE_INTERVAL`  

## Constructors

- `public SpectatorSiteSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.SpectatorSiteSystem+SpectatorSiteJob`  
- `Game.Simulation.SpectatorSiteSystem+TypeHandle`  

