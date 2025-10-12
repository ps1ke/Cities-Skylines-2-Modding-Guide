# Game.Simulation.WaterPipePollutionSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.WaterPipeFlowSystem m_WaterPipeFlowSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Unity.Entities.EntityQuery m_NodeQuery`  
- `private Unity.Entities.EntityQuery m_EdgeQuery`  
- `private Unity.Entities.EntityQuery m_ParameterQuery`  
- `private Game.Simulation.WaterPipePollutionSystem+TypeHandle __TypeHandle`  
- `private static const System.Int32 kUpdateInterval`  

## Constructors

- `public WaterPipePollutionSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.WaterPipePollutionSystem+NodePollutionJob`  
- `Game.Simulation.WaterPipePollutionSystem+EdgePollutionJob`  
- `Game.Simulation.WaterPipePollutionSystem+TypeHandle`  

