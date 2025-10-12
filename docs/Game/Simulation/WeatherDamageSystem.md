# Game.Simulation.WeatherDamageSystem

**Assembly:** `Game`  
**Namespace:** `Game.Simulation`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Notifications.IconCommandSystem m_IconCommandSystem`  
- `private Game.Simulation.CitySystem m_CitySystem`  
- `private Game.EndFrameBarrier m_EndFrameBarrier`  
- `private Unity.Entities.EntityQuery m_FacingQuery`  
- `private Unity.Entities.EntityQuery m_FireConfigQuery`  
- `private Unity.Entities.EntityQuery m_DisasterConfigQuery`  
- `private Unity.Entities.EntityArchetype m_DamageEventArchetype`  
- `private Unity.Entities.EntityArchetype m_DestroyEventArchetype`  
- `private Game.Simulation.EventHelpers+StructuralIntegrityData m_StructuralIntegrityData`  
- `private Game.Simulation.WeatherDamageSystem+TypeHandle __TypeHandle`  
- `private static const System.UInt32 UPDATE_INTERVAL`  

## Constructors

- `public WeatherDamageSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Simulation.WeatherDamageSystem+WeatherDamageJob`  
- `Game.Simulation.WeatherDamageSystem+TypeHandle`  

