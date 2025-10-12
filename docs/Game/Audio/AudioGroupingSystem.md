# Game.Audio.AudioGroupingSystem

**Assembly:** `Game`  
**Namespace:** `Game.Audio`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Simulation.TrafficAmbienceSystem m_TrafficAmbienceSystem`  
- `private Game.Simulation.ZoneAmbienceSystem m_ZoneAmbienceSystem`  
- `private Game.Effects.EffectFlagSystem m_EffectFlagSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private Unity.Entities.EntityQuery m_AudioGroupingConfigurationQuery`  
- `private Unity.Entities.EntityQuery m_AudioGroupingMiscSettingQuery`  
- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_AmbienceEntities`  
- `private Unity.Collections.NativeArray<Unity.Entities.Entity> m_NearAmbienceEntities`  
- `private Unity.Collections.NativeArray<Game.Prefabs.AudioGroupingSettingsData> m_Settings`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Unity.Entities.EntityQuery m_OnFireTreeQuery`  
- `private Unity.Collections.NativeArray<System.Single> m_CurrentValues`  
- `private Game.Audio.AudioGroupingSystem+TypeHandle __TypeHandle`  

## Constructors

- `public AudioGroupingSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `private CreateEffect(Unity.Entities.Entity sfx) : Unity.Entities.Entity`  
- `private Initialize() : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  

## Nested types

- `Game.Audio.AudioGroupingSystem+AudioGroupingJob`  
- `Game.Audio.AudioGroupingSystem+TypeHandle`  

