# Game.Rendering.ClimateRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  
- `private Game.Simulation.ClimateSystem m_ClimateSystem`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Rendering.WindTextureSystem m_WindTextureSystem`  
- `private Game.Simulation.TerrainSystem m_TerrainSystem`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private Game.Audio.AudioManager m_AudioManager`  
- `private System.Single <precipitationVolumeScale>k__BackingField`  
- `public System.Boolean globalEffectTimeStepFromSimulation`  
- `public System.Boolean weatherEffectTimeStepFromSimulation`  
- `private UnityEngine.VFX.VisualEffect m_PrecipitationVFX`  
- `private UnityEngine.VFX.VisualEffect m_LightningVFX`  
- `private UnityEngine.Rendering.Volume m_ClimateControlVolume`  
- `private UnityEngine.Rendering.HighDefinition.VolumetricClouds m_VolumetricClouds`  
- `private Game.Rendering.WindVolumeComponent m_Wind`  
- `private Game.Rendering.WindControl m_WindControl`  
- `private System.Boolean m_IsRaining`  
- `private System.Boolean m_IsSnowing`  
- `private System.Boolean m_HailStorm`  
- `private Unity.Entities.EntityQuery m_EventQuery`  
- `private Unity.Collections.NativeQueue<Game.Events.LightningStrike> m_LightningStrikeQueue`  
- `private Unity.Jobs.JobHandle m_LightningStrikeDeps`  
- `private System.Boolean <editMode>k__BackingField`  
- `private System.Boolean <pauseSimulationOnLightning>k__BackingField`  
- `private Game.Rendering.Climate.WeatherPropertiesStack m_PropertiesStack`  
- `private readonly System.Collections.Generic.List<Game.Prefabs.Climate.WeatherPrefab> m_FromWeatherPrefabs`  
- `private readonly System.Collections.Generic.List<Game.Prefabs.Climate.WeatherPrefab> m_ToWeatherPrefabs`  
- `private System.Boolean m_PropertiesChanged`  
- `private System.Boolean <IsAsync>k__BackingField`  
- `private Game.Rendering.ClimateRenderSystem+TypeHandle __TypeHandle`  
- `private Unity.Entities.EntityQuery __query_100321765_0`  
- `private Unity.Entities.EntityQuery __query_100321765_1`  
- `private static UnityEngine.VFX.VisualEffectAsset s_PrecipitationVFXAsset`  
- `private static UnityEngine.VFX.VisualEffectAsset s_LightningVFXAsset`  

## Properties

- `public System.Single precipitationVolumeScale { get; set }`  
- `public System.Boolean editMode { get; set }`  
- `public System.Boolean pauseSimulationOnLightning { get; set }`  
- `internal Game.Rendering.Climate.WeatherPropertiesStack propertiesStack { internal get }`  
- `public System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> fromWeatherPrefabs { get }`  
- `public System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> toWeatherPrefabs { get }`  
- `public System.Boolean IsAsync { get; set }`  

## Constructors

- `public ClimateRenderSystem()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddLightningStrikeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `public Clear() : System.Void`  
- `private CreateDynamicVFXIfNeeded() : System.Void`  
- `private GetEventName(Game.Rendering.ClimateRenderSystem+PrecipitationType type, System.Boolean start, System.String& name) : System.Boolean`  
- `public GetLightningStrikeQueue(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeQueue<Game.Events.LightningStrike>`  
- `private GetTimeOfYear() : System.Single`  
- `public LightningStrike(Unity.Mathematics.float3 start, Unity.Mathematics.float3 target, System.Boolean useCloudsAltitude = True) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `private ResetOverrides() : System.Void`  
- `public ScheduleFrom(Game.Prefabs.Climate.WeatherPrefab prefab) : System.Void`  
- `public ScheduleTo(Game.Prefabs.Climate.WeatherPrefab prefab) : System.Void`  
- `private SetData(Game.Rendering.Climate.WeatherPropertiesStack stack, System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> fromPrefab, System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> toPrefab) : System.Void`  
- `private UpdateEffectsProperties() : System.Void`  
- `private UpdateEffectsState() : System.Void`  
- `private UpdateEffectState(Game.Rendering.ClimateRenderSystem+PrecipitationType type, System.Boolean start) : System.Void`  
- `private UpdateVFXSpeed() : System.Void`  
- `private UpdateVolumetricClouds() : System.Void`  
- `private UpdateWeather() : System.Void`  

## Nested types

- `Game.Rendering.ClimateRenderSystem+VFXIDs`  
- `Game.Rendering.ClimateRenderSystem+PrecipitationType`  
- `Game.Rendering.ClimateRenderSystem+TypeHandle`  

