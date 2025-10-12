# Game.Simulation.CalendarEventLaunchSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Unity.Entities.EntityQuery m_CalendarEventQuery`  
- `private Game.Simulation.CalendarEventLaunchSystem+TypeHandle __TypeHandle`  
- `private static const System.Int32 UPDATES_PER_DAY`  

## Constructors

- `public CalendarEventLaunchSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.CalendarEventLaunchSystem+CheckEventLaunchJob`  
- `Game.Simulation.CalendarEventLaunchSystem+TypeHandle`  

