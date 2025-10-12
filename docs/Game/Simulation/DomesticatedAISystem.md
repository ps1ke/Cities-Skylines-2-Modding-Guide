# Game.Simulation.DomesticatedAISystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Unity.Entities.EntityQuery m_CreatureQuery`  
- `private Unity.Entities.EntityQuery m_GroupCreatureQuery`  
- `private Game.Simulation.DomesticatedAISystem+TypeHandle __TypeHandle`  

## Constructors

- `public DomesticatedAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.DomesticatedAISystem+DomesticatedGroupTickJob`  
- `Game.Simulation.DomesticatedAISystem+DomesticatedTickJob`  
- `Game.Simulation.DomesticatedAISystem+TypeHandle`  

