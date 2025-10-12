# Game.Simulation.TouristFindTargetSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Unity.Entities.EntityQuery m_SeekerQuery`  
- `private Unity.Entities.ComponentTypeSet m_PathfindTypes`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.PathfindSetupSystem m_PathfindSetupSystem`  
- `private Game.Events.AddMeetingSystem m_AddMeetingSystem`  
- `private Unity.Collections.NativeQueue<Game.Simulation.TouristFindTargetSystem+HotelReserveAction> m_HotelReserveQueue`  
- `private Game.Simulation.TouristFindTargetSystem+TypeHandle __TypeHandle`  

## Constructors

- `public TouristFindTargetSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.TouristFindTargetSystem+HotelReserveAction`  
- `Game.Simulation.TouristFindTargetSystem+TouristFindTargetJob`  
- `Game.Simulation.TouristFindTargetSystem+HotelReserveJob`  
- `Game.Simulation.TouristFindTargetSystem+TypeHandle`  

