# Game.Simulation.OutsideConnectionDelaySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  
- `private Unity.Entities.EntityQuery m_NodeQuery`  
- `private Game.Simulation.OutsideConnectionDelaySystem+TypeHandle __TypeHandle`  
- `public static const System.Int32 UPDATES_PER_DAY`  

## Constructors

- `public OutsideConnectionDelaySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.OutsideConnectionDelaySystem+AccumulationData`  
- `Game.Simulation.OutsideConnectionDelaySystem+OutsideConnectionDelayJob`  
- `Game.Simulation.OutsideConnectionDelaySystem+TypeHandle`  

