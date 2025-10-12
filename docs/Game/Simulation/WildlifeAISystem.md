# Game.Simulation.WildlifeAISystem

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
- `private Game.Simulation.WildlifeAISystem+TypeHandle __TypeHandle`  

## Constructors

- `public WildlifeAISystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `public virtual GetUpdateOffset(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.WildlifeAISystem+WildlifeGroupTickJob`  
- `Game.Simulation.WildlifeAISystem+WildlifeTickJob`  
- `Game.Simulation.WildlifeAISystem+TypeHandle`  

