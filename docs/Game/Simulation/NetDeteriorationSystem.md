# Game.Simulation.NetDeteriorationSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_LaneQuery`  
- `private Unity.Entities.EntityQuery m_EdgeQuery`  
- `private Unity.Entities.EntityArchetype m_MaintenanceRequestArchetype`  
- `private Game.Simulation.NetDeteriorationSystem+TypeHandle __TypeHandle`  
- `public static readonly System.Int32 kUpdatesPerDay`  

## Constructors

- `public NetDeteriorationSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public static GetMaintenancePriority(Game.Net.NetCondition condition) : System.Int32`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.NetDeteriorationSystem+UpdateLaneConditionJob`  
- `Game.Simulation.NetDeteriorationSystem+UpdateNetConditionJob`  
- `Game.Simulation.NetDeteriorationSystem+TypeHandle`  

