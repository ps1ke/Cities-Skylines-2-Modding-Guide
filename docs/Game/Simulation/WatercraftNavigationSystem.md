# Game.Simulation.WatercraftNavigationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Game.Areas.SearchSystem m_AreaSearchSystem`  
- `private Game.Objects.SearchSystem m_ObjectSearchSystem`  
- `private Unity.Entities.EntityQuery m_VehicleQuery`  
- `private Game.Net.LaneObjectUpdater m_LaneObjectUpdater`  
- `private Game.Simulation.WatercraftNavigationSystem+TypeHandle __TypeHandle`  

## Constructors

- `public WatercraftNavigationSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.WatercraftNavigationSystem+UpdateNavigationJob`  
- `Game.Simulation.WatercraftNavigationSystem+GroupLaneReservationsJob`  
- `Game.Simulation.WatercraftNavigationSystem+UpdateLaneSignalsJob`  
- `Game.Simulation.WatercraftNavigationSystem+UpdateLaneReservationsJob`  
- `Game.Simulation.WatercraftNavigationSystem+ApplyLaneEffectsJob`  
- `Game.Simulation.WatercraftNavigationSystem+TypeHandle`  

