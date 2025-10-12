# Game.Audio.WeatherAudioSystem

**Assembly:** `Game`  
**Namespace:** `Game.Audio`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Audio.AudioManager m_AudioManager`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.WaterSystem m_WaterSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Unity.Entities.EntityQuery m_WeatherAudioEntityQuery`  
- `private Unity.Entities.Entity m_SmallWaterAudioEntity`  
- `private System.Int32 m_WaterAudioEnabledZoom`  
- `private System.Int32 m_WaterAudioNearDistance`  
- `private Game.Audio.WeatherAudioSystem+TypeHandle __TypeHandle`  

## Constructors

- `public WeatherAudioSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public virtual GetUpdateInterval(Game.SystemUpdatePhase phase) : System.Int32`  
- `private Initialize() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Audio.WeatherAudioSystem+WeatherAudioJob`  
- `Game.Audio.WeatherAudioSystem+TypeHandle`  

