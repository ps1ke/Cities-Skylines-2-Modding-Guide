# Game.Rendering.ClimateRenderSystem

**Assembly:** `Game`  
**Namespace:** `Game.Rendering`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class ClimateRenderSystem : Game.GameSystemBase
{
    private Game.Rendering.RenderingSystem m_RenderingSystem;
    private Game.Simulation.ClimateSystem m_ClimateSystem;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Rendering.WindTextureSystem m_WindTextureSystem;
    private Game.Simulation.TerrainSystem m_TerrainSystem;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private Game.Audio.AudioManager m_AudioManager;
    private System.Single <precipitationVolumeScale>k__BackingField;
    public System.Boolean globalEffectTimeStepFromSimulation;
    public System.Boolean weatherEffectTimeStepFromSimulation;
    private UnityEngine.VFX.VisualEffect m_PrecipitationVFX;
    private UnityEngine.VFX.VisualEffect m_LightningVFX;
    private UnityEngine.Rendering.Volume m_ClimateControlVolume;
    private UnityEngine.Rendering.HighDefinition.VolumetricClouds m_VolumetricClouds;
    private Game.Rendering.WindVolumeComponent m_Wind;
    private Game.Rendering.WindControl m_WindControl;
    private System.Boolean m_IsRaining;
    private System.Boolean m_IsSnowing;
    private System.Boolean m_HailStorm;
    private Unity.Entities.EntityQuery m_EventQuery;
    private Unity.Collections.NativeQueue<Game.Events.LightningStrike> m_LightningStrikeQueue;
    private Unity.Jobs.JobHandle m_LightningStrikeDeps;
    private System.Boolean <editMode>k__BackingField;
    private System.Boolean <pauseSimulationOnLightning>k__BackingField;
    private Game.Rendering.Climate.WeatherPropertiesStack m_PropertiesStack;
    private readonly System.Collections.Generic.List<Game.Prefabs.Climate.WeatherPrefab> m_FromWeatherPrefabs;
    private readonly System.Collections.Generic.List<Game.Prefabs.Climate.WeatherPrefab> m_ToWeatherPrefabs;
    private System.Boolean m_PropertiesChanged;
    private System.Boolean <IsAsync>k__BackingField;
    private Game.Rendering.ClimateRenderSystem+TypeHandle __TypeHandle;
    private Unity.Entities.EntityQuery __query_100321765_0;
    private Unity.Entities.EntityQuery __query_100321765_1;
    private static UnityEngine.VFX.VisualEffectAsset s_PrecipitationVFXAsset;
    private static UnityEngine.VFX.VisualEffectAsset s_LightningVFXAsset;

    public System.Single precipitationVolumeScale { get; set; }
    public System.Boolean editMode { get; set; }
    public System.Boolean pauseSimulationOnLightning { get; set; }
    internal Game.Rendering.Climate.WeatherPropertiesStack propertiesStack { internal get; }
    public System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> fromWeatherPrefabs { get; }
    public System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> toWeatherPrefabs { get; }
    public System.Boolean IsAsync { get; set; }

    public ClimateRenderSystem();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddLightningStrikeWriter(Unity.Jobs.JobHandle jobHandle);
    public System.Void Clear();
    private System.Void CreateDynamicVFXIfNeeded();
    private System.Boolean GetEventName(Game.Rendering.ClimateRenderSystem+PrecipitationType type, System.Boolean start, System.String& name);
    public Unity.Collections.NativeQueue<Game.Events.LightningStrike> GetLightningStrikeQueue(Unity.Jobs.JobHandle& dependencies);
    private System.Single GetTimeOfYear();
    public System.Void LightningStrike(Unity.Mathematics.float3 start, Unity.Mathematics.float3 target, System.Boolean useCloudsAltitude);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnUpdate();
    private System.Void ResetOverrides();
    public System.Void ScheduleFrom(Game.Prefabs.Climate.WeatherPrefab prefab);
    public System.Void ScheduleTo(Game.Prefabs.Climate.WeatherPrefab prefab);
    private System.Void SetData(Game.Rendering.Climate.WeatherPropertiesStack stack, System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> fromPrefab, System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> toPrefab);
    private System.Void UpdateEffectsProperties();
    private System.Void UpdateEffectsState();
    private System.Void UpdateEffectState(Game.Rendering.ClimateRenderSystem+PrecipitationType type, System.Boolean start);
    private System.Void UpdateVFXSpeed();
    private System.Void UpdateVolumetricClouds();
    private System.Void UpdateWeather();
}
```


## Fields

- `private Game.Rendering.RenderingSystem m_RenderingSystem`  

```csharp
private Game.Rendering.RenderingSystem m_RenderingSystem;
```

- `private Game.Simulation.ClimateSystem m_ClimateSystem`  

```csharp
private Game.Simulation.ClimateSystem m_ClimateSystem;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Rendering.WindTextureSystem m_WindTextureSystem`  

```csharp
private Game.Rendering.WindTextureSystem m_WindTextureSystem;
```

- `private Game.Simulation.TerrainSystem m_TerrainSystem`  

```csharp
private Game.Simulation.TerrainSystem m_TerrainSystem;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private Game.Audio.AudioManager m_AudioManager`  

```csharp
private Game.Audio.AudioManager m_AudioManager;
```

- `private System.Single <precipitationVolumeScale>k__BackingField`  

```csharp
private System.Single <precipitationVolumeScale>k__BackingField;
```

- `public System.Boolean globalEffectTimeStepFromSimulation`  

```csharp
public System.Boolean globalEffectTimeStepFromSimulation;
```

- `public System.Boolean weatherEffectTimeStepFromSimulation`  

```csharp
public System.Boolean weatherEffectTimeStepFromSimulation;
```

- `private UnityEngine.VFX.VisualEffect m_PrecipitationVFX`  

```csharp
private UnityEngine.VFX.VisualEffect m_PrecipitationVFX;
```

- `private UnityEngine.VFX.VisualEffect m_LightningVFX`  

```csharp
private UnityEngine.VFX.VisualEffect m_LightningVFX;
```

- `private UnityEngine.Rendering.Volume m_ClimateControlVolume`  

```csharp
private UnityEngine.Rendering.Volume m_ClimateControlVolume;
```

- `private UnityEngine.Rendering.HighDefinition.VolumetricClouds m_VolumetricClouds`  

```csharp
private UnityEngine.Rendering.HighDefinition.VolumetricClouds m_VolumetricClouds;
```

- `private Game.Rendering.WindVolumeComponent m_Wind`  

```csharp
private Game.Rendering.WindVolumeComponent m_Wind;
```

- `private Game.Rendering.WindControl m_WindControl`  

```csharp
private Game.Rendering.WindControl m_WindControl;
```

- `private System.Boolean m_IsRaining`  

```csharp
private System.Boolean m_IsRaining;
```

- `private System.Boolean m_IsSnowing`  

```csharp
private System.Boolean m_IsSnowing;
```

- `private System.Boolean m_HailStorm`  

```csharp
private System.Boolean m_HailStorm;
```

- `private Unity.Entities.EntityQuery m_EventQuery`  

```csharp
private Unity.Entities.EntityQuery m_EventQuery;
```

- `private Unity.Collections.NativeQueue<Game.Events.LightningStrike> m_LightningStrikeQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Events.LightningStrike> m_LightningStrikeQueue;
```

- `private Unity.Jobs.JobHandle m_LightningStrikeDeps`  

```csharp
private Unity.Jobs.JobHandle m_LightningStrikeDeps;
```

- `private System.Boolean <editMode>k__BackingField`  

```csharp
private System.Boolean <editMode>k__BackingField;
```

- `private System.Boolean <pauseSimulationOnLightning>k__BackingField`  

```csharp
private System.Boolean <pauseSimulationOnLightning>k__BackingField;
```

- `private Game.Rendering.Climate.WeatherPropertiesStack m_PropertiesStack`  

```csharp
private Game.Rendering.Climate.WeatherPropertiesStack m_PropertiesStack;
```

- `private readonly System.Collections.Generic.List<Game.Prefabs.Climate.WeatherPrefab> m_FromWeatherPrefabs`  

```csharp
private readonly System.Collections.Generic.List<Game.Prefabs.Climate.WeatherPrefab> m_FromWeatherPrefabs;
```

- `private readonly System.Collections.Generic.List<Game.Prefabs.Climate.WeatherPrefab> m_ToWeatherPrefabs`  

```csharp
private readonly System.Collections.Generic.List<Game.Prefabs.Climate.WeatherPrefab> m_ToWeatherPrefabs;
```

- `private System.Boolean m_PropertiesChanged`  

```csharp
private System.Boolean m_PropertiesChanged;
```

- `private System.Boolean <IsAsync>k__BackingField`  

```csharp
private System.Boolean <IsAsync>k__BackingField;
```

- `private Game.Rendering.ClimateRenderSystem+TypeHandle __TypeHandle`  

```csharp
private Game.Rendering.ClimateRenderSystem+TypeHandle __TypeHandle;
```

- `private Unity.Entities.EntityQuery __query_100321765_0`  

```csharp
private Unity.Entities.EntityQuery __query_100321765_0;
```

- `private Unity.Entities.EntityQuery __query_100321765_1`  

```csharp
private Unity.Entities.EntityQuery __query_100321765_1;
```

- `private static UnityEngine.VFX.VisualEffectAsset s_PrecipitationVFXAsset`  

```csharp
private static UnityEngine.VFX.VisualEffectAsset s_PrecipitationVFXAsset;
```

- `private static UnityEngine.VFX.VisualEffectAsset s_LightningVFXAsset`  

```csharp
private static UnityEngine.VFX.VisualEffectAsset s_LightningVFXAsset;
```


## Properties

- `public System.Single precipitationVolumeScale { get; set }`  

```csharp
public System.Single precipitationVolumeScale { get; set; }
```

- `public System.Boolean editMode { get; set }`  

```csharp
public System.Boolean editMode { get; set; }
```

- `public System.Boolean pauseSimulationOnLightning { get; set }`  

```csharp
public System.Boolean pauseSimulationOnLightning { get; set; }
```

- `internal Game.Rendering.Climate.WeatherPropertiesStack propertiesStack { internal get }`  

```csharp
internal Game.Rendering.Climate.WeatherPropertiesStack propertiesStack { internal get; }
```

- `public System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> fromWeatherPrefabs { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> fromWeatherPrefabs { get; }
```

- `public System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> toWeatherPrefabs { get }`  

```csharp
public System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> toWeatherPrefabs { get; }
```

- `public System.Boolean IsAsync { get; set }`  

```csharp
public System.Boolean IsAsync { get; set; }
```


## Constructors

- `public ClimateRenderSystem()`  

```csharp
public ClimateRenderSystem();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddLightningStrikeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddLightningStrikeWriter(Unity.Jobs.JobHandle jobHandle);
```

- `public Clear() : System.Void`  

```csharp
public System.Void Clear();
```

- `private CreateDynamicVFXIfNeeded() : System.Void`  

```csharp
private System.Void CreateDynamicVFXIfNeeded();
```

- `private GetEventName(Game.Rendering.ClimateRenderSystem+PrecipitationType type, System.Boolean start, System.String& name) : System.Boolean`  

```csharp
private System.Boolean GetEventName(Game.Rendering.ClimateRenderSystem+PrecipitationType type, System.Boolean start, System.String& name);
```

- `public GetLightningStrikeQueue(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeQueue<Game.Events.LightningStrike>`  

```csharp
public Unity.Collections.NativeQueue<Game.Events.LightningStrike> GetLightningStrikeQueue(Unity.Jobs.JobHandle& dependencies);
```

- `private GetTimeOfYear() : System.Single`  

```csharp
private System.Single GetTimeOfYear();
```

- `public LightningStrike(Unity.Mathematics.float3 start, Unity.Mathematics.float3 target, System.Boolean useCloudsAltitude = True) : System.Void`  

```csharp
public System.Void LightningStrike(Unity.Mathematics.float3 start, Unity.Mathematics.float3 target, System.Boolean useCloudsAltitude);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected virtual System.Void OnCreateForCompiler();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `private ResetOverrides() : System.Void`  

```csharp
private System.Void ResetOverrides();
```

- `public ScheduleFrom(Game.Prefabs.Climate.WeatherPrefab prefab) : System.Void`  

```csharp
public System.Void ScheduleFrom(Game.Prefabs.Climate.WeatherPrefab prefab);
```

- `public ScheduleTo(Game.Prefabs.Climate.WeatherPrefab prefab) : System.Void`  

```csharp
public System.Void ScheduleTo(Game.Prefabs.Climate.WeatherPrefab prefab);
```

- `private SetData(Game.Rendering.Climate.WeatherPropertiesStack stack, System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> fromPrefab, System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> toPrefab) : System.Void`  

```csharp
private System.Void SetData(Game.Rendering.Climate.WeatherPropertiesStack stack, System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> fromPrefab, System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> toPrefab);
```

- `private UpdateEffectsProperties() : System.Void`  

```csharp
private System.Void UpdateEffectsProperties();
```

- `private UpdateEffectsState() : System.Void`  

```csharp
private System.Void UpdateEffectsState();
```

- `private UpdateEffectState(Game.Rendering.ClimateRenderSystem+PrecipitationType type, System.Boolean start) : System.Void`  

```csharp
private System.Void UpdateEffectState(Game.Rendering.ClimateRenderSystem+PrecipitationType type, System.Boolean start);
```

- `private UpdateVFXSpeed() : System.Void`  

```csharp
private System.Void UpdateVFXSpeed();
```

- `private UpdateVolumetricClouds() : System.Void`  

```csharp
private System.Void UpdateVolumetricClouds();
```

- `private UpdateWeather() : System.Void`  

```csharp
private System.Void UpdateWeather();
```


## Nested types

- `Game.Rendering.ClimateRenderSystem+VFXIDs`  
- `Game.Rendering.ClimateRenderSystem+PrecipitationType`  
- `Game.Rendering.ClimateRenderSystem+TypeHandle`  

