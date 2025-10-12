# Game.Simulation.WetnessSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_SurfaceQuery`  
- `private Unity.Entities.EntityArchetype m_SubObjectEventArchetype`  
- `private Game.Simulation.WetnessSystem+TypeHandle __TypeHandle`  
- `public static const System.Int32 SNOW_REQUIREMENT_LIMIT`  

## Constructors

- `public WetnessSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.WetnessSystem+WetnessJob`  
- `Game.Simulation.WetnessSystem+TypeHandle`  

