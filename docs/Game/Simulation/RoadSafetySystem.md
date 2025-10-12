# Game.Simulation.RoadSafetySystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.Rendering.LightingSystem m_LightingSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_RoadQuery`  
- `private Unity.Entities.EntityQuery m_AccidentPrefabQuery`  
- `private Game.Simulation.RoadSafetySystem+TypeHandle __TypeHandle`  
- `private static const System.Int32 UPDATES_PER_DAY`  

## Constructors

- `public RoadSafetySystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.RoadSafetySystem+RoadSafetyJob`  
- `Game.Simulation.RoadSafetySystem+TypeHandle`  

