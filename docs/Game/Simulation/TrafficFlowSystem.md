# Game.Simulation.TrafficFlowSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Pathfind.PathfindQueueSystem m_PathfindQueueSystem`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Unity.Entities.EntityQuery m_LaneQuery`  
- `private Unity.Entities.EntityQuery m_RoadQuery`  
- `private Game.Simulation.TrafficFlowSystem+TypeHandle __TypeHandle`  
- `public static const System.Int32 UPDATES_PER_DAY`  

## Constructors

- `public TrafficFlowSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.TrafficFlowSystem+UpdateLaneFlowJob`  
- `Game.Simulation.TrafficFlowSystem+UpdateRoadFlowJob`  
- `Game.Simulation.TrafficFlowSystem+TypeHandle`  

