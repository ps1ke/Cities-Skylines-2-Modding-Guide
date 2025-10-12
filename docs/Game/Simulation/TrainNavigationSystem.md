# Game.Simulation.TrainNavigationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Net.SearchSystem m_NetSearchSystem`  
- `private Unity.Entities.EntityQuery m_VehicleQuery`  
- `private Game.Net.LaneObjectUpdater m_LaneObjectUpdater`  
- `private Game.Simulation.TrainNavigationSystem+TypeHandle __TypeHandle`  

## Constructors

- `public TrainNavigationSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.TrainNavigationSystem+UpdateNavigationJob`  
- `Game.Simulation.TrainNavigationSystem+UpdateLaneSignalsJob`  
- `Game.Simulation.TrainNavigationSystem+UpdateLaneReservationsJob`  
- `Game.Simulation.TrainNavigationSystem+ApplyLaneEffectsJob`  
- `Game.Simulation.TrainNavigationSystem+TypeHandle`  

