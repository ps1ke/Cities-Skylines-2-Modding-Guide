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
[Preserve]
	public ClimateRenderSystem()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		EntityQueryBuilder entityQueryBuilder = new EntityQueryBuilder(Allocator.Temp);
		EntityQueryBuilder entityQueryBuilder2 = entityQueryBuilder.WithAll<TimeSettingsData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_100321765_0 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder2 = entityQueryBuilder.WithAll<TimeData>();
		entityQueryBuilder2 = entityQueryBuilder2.WithOptions(EntityQueryOptions.IncludeSystems);
		__query_100321765_1 = entityQueryBuilder2.Build(ref state);
		entityQueryBuilder.Reset();
		entityQueryBuilder.Dispose();
	}
```

- `public AddLightningStrikeWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddLightningStrikeWriter(JobHandle jobHandle)
	{
		m_LightningStrikeDeps = jobHandle;
	}
```

- `public Clear() : System.Void`  

```csharp
public void Clear()
	{
		m_PropertiesChanged = true;
		m_FromWeatherPrefabs.Clear();
		m_ToWeatherPrefabs.Clear();
	}
```

- `private CreateDynamicVFXIfNeeded() : System.Void`  

```csharp
private void CreateDynamicVFXIfNeeded()
	{
		if (s_PrecipitationVFXAsset != null && m_PrecipitationVFX == null)
		{
			COSystemBase.baseLog.DebugFormat("Creating VFXs pool");
			m_PrecipitationVFX = new GameObject("PrecipitationVFX").AddComponent<VisualEffect>();
			m_PrecipitationVFX.visualEffectAsset = s_PrecipitationVFXAsset;
			m_LightningVFX = new GameObject("LightningVFX").AddComponent<VisualEffect>();
			m_LightningVFX.visualEffectAsset = s_LightningVFXAsset;
		}
	}
```

- `private GetEventName(Game.Rendering.ClimateRenderSystem+PrecipitationType type, System.Boolean start, System.String& name) : System.Boolean`  

```csharp
private bool GetEventName(PrecipitationType type, bool start, out string name)
	{
		switch (type)
		{
		case PrecipitationType.Rain:
			name = (start ? "OnRainStart" : "OnRainStop");
			return true;
		case PrecipitationType.Snow:
			name = (start ? "OnSnowStart" : "OnSnowStop");
			return true;
		case PrecipitationType.Hail:
			name = (start ? "OnHailStart" : "OnHailStop");
			return true;
		default:
			name = null;
			return false;
		}
	}
```

- `public GetLightningStrikeQueue(Unity.Jobs.JobHandle& dependencies) : Unity.Collections.NativeQueue<Game.Events.LightningStrike>`  

```csharp
public NativeQueue<LightningStrike> GetLightningStrikeQueue(out JobHandle dependencies)
	{
		dependencies = m_LightningStrikeDeps;
		return m_LightningStrikeQueue;
	}
```

- `private GetTimeOfYear() : System.Single`  

```csharp
private float GetTimeOfYear()
	{
		if (m_ClimateSystem.currentDate.overrideState)
		{
			return m_ClimateSystem.currentDate.overrideValue;
		}
		if (__query_100321765_0.TryGetSingleton<TimeSettingsData>(out var value) && __query_100321765_1.TryGetSingleton<TimeData>(out var value2))
		{
			double renderingFrame = (float)(m_RenderingSystem.frameIndex - value2.m_FirstFrame) + m_RenderingSystem.frameTime;
			return m_TimeSystem.GetTimeOfYear(value, value2, renderingFrame);
		}
		return 0.5f;
	}
```

- `public LightningStrike(Unity.Mathematics.float3 start, Unity.Mathematics.float3 target, System.Boolean useCloudsAltitude = True) : System.Void`  

```csharp
public void LightningStrike(float3 start, float3 target, bool useCloudsAltitude = true)
	{
		if (pauseSimulationOnLightning)
		{
			m_SimulationSystem.selectedSpeed = 0f;
		}
		if (useCloudsAltitude)
		{
			start.y = m_VolumetricClouds.bottomAltitude.value + m_VolumetricClouds.altitudeRange.value * 0.1f;
		}
		COSystemBase.baseLog.DebugFormat("Lightning strike {0}->{1}", start, target);
		m_LightningVFX.SetVector3(VFXIDs.LightningOrigin, start);
		m_LightningVFX.SetVector3(VFXIDs.LightningTarget, target);
		m_LightningVFX.SendEvent("OnPlay");
		m_AudioManager.PlayLightningSFX((start - target) / 2f);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		m_ClimateSystem = base.World.GetOrCreateSystemManaged<ClimateSystem>();
		m_RenderingSystem = base.World.GetOrCreateSystemManaged<RenderingSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_WindTextureSystem = base.World.GetOrCreateSystemManaged<WindTextureSystem>();
		m_TerrainSystem = base.World.GetOrCreateSystemManaged<TerrainSystem>();
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_AudioManager = base.World.GetOrCreateSystemManaged<AudioManager>();
		m_ClimateControlVolume = VolumeHelper.CreateVolume("ClimateControlVolume", 50);
		m_PropertiesStack = new WeatherPropertiesStack(m_ClimateControlVolume);
		VolumeHelper.GetOrCreateVolumeComponent(m_ClimateControlVolume, ref m_VolumetricClouds);
		VolumeHelper.GetOrCreateVolumeComponent(m_ClimateControlVolume, ref m_Wind);
		m_WindControl = WindControl.instance;
		ResetOverrides();
		s_PrecipitationVFXAsset = Resources.Load<VisualEffectAsset>("Precipitation/PrecipitationVFX");
		s_LightningVFXAsset = Resources.Load<VisualEffectAsset>("Lightning/LightningBolt");
		m_EventQuery = GetEntityQuery(ComponentType.ReadOnly<Game.Events.WeatherPhenomenon>(), ComponentType.Exclude<Deleted>(), ComponentType.Exclude<Temp>());
		m_LightningStrikeQueue = new NativeQueue<LightningStrike>(Allocator.Persistent);
	}
```

- `protected virtual OnCreateForCompiler() : System.Void`  

```csharp
protected override void OnCreateForCompiler()
	{
		base.OnCreateForCompiler();
		__AssignQueries(ref base.CheckedStateRef);
		__TypeHandle.__AssignHandles(ref base.CheckedStateRef);
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		m_LightningStrikeDeps.Complete();
		m_LightningStrikeQueue.Dispose();
		m_WindControl.Dispose();
		m_PropertiesStack.Dispose();
		VolumeHelper.DestroyVolume(m_ClimateControlVolume);
		base.OnDestroy();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		if (m_CameraUpdateSystem.activeViewer != null)
		{
			UpdateWeather();
			UpdateVolumetricClouds();
			CreateDynamicVFXIfNeeded();
			UpdateEffectsState();
			UpdateEffectsProperties();
			UpdateVFXSpeed();
		}
		NativeArray<Entity> nativeArray = m_EventQuery.ToEntityArray(Allocator.TempJob);
		try
		{
			for (int i = 0; i < nativeArray.Length; i++)
			{
				Entity entity = nativeArray[i];
				if (base.EntityManager.GetComponentData<Game.Events.WeatherPhenomenon>(entity).m_Intensity != 0f)
				{
					base.EntityManager.GetComponentData<InterpolatedTransform>(entity);
					PrefabRef componentData = base.EntityManager.GetComponentData<PrefabRef>(entity);
					m_PrefabSystem.GetPrefab<EventPrefab>(componentData).GetComponent<Game.Prefabs.WeatherPhenomenon>();
				}
			}
		}
		finally
		{
			nativeArray.Dispose();
		}
		m_LightningStrikeDeps.Complete();
		LightningStrike item;
		while (m_LightningStrikeQueue.TryDequeue(out item))
		{
			LightningStrike(item.m_Position, item.m_Position);
		}
	}
```

- `private ResetOverrides() : System.Void`  

```csharp
private void ResetOverrides()
	{
		m_VolumetricClouds.SetAllOverridesTo(state: false);
	}
```

- `public ScheduleFrom(Game.Prefabs.Climate.WeatherPrefab prefab) : System.Void`  

```csharp
public void ScheduleFrom(WeatherPrefab prefab)
	{
		m_FromWeatherPrefabs.Add(prefab);
	}
```

- `public ScheduleTo(Game.Prefabs.Climate.WeatherPrefab prefab) : System.Void`  

```csharp
public void ScheduleTo(WeatherPrefab prefab)
	{
		m_ToWeatherPrefabs.Add(prefab);
	}
```

- `private SetData(Game.Rendering.Climate.WeatherPropertiesStack stack, System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> fromPrefab, System.Collections.Generic.IReadOnlyList<Game.Prefabs.Climate.WeatherPrefab> toPrefab) : System.Void`  

```csharp
private void SetData(WeatherPropertiesStack stack, IReadOnlyList<WeatherPrefab> fromPrefab, IReadOnlyList<WeatherPrefab> toPrefab)
	{
		for (int i = 0; i < fromPrefab.Count; i++)
		{
			foreach (OverrideablePropertiesComponent overrideableProperty in fromPrefab[i].overrideableProperties)
			{
				if (overrideableProperty.active && !overrideableProperty.hasTimeBasedInterpolation)
				{
					stack.SetFrom(overrideableProperty.GetType(), overrideableProperty);
				}
			}
		}
		for (int j = 0; j < toPrefab.Count; j++)
		{
			WeatherPrefab weatherPrefab = toPrefab[j];
			foreach (OverrideablePropertiesComponent overrideableProperty2 in weatherPrefab.overrideableProperties)
			{
				if (overrideableProperty2.active)
				{
					if (overrideableProperty2.hasTimeBasedInterpolation)
					{
						stack.SetTarget(overrideableProperty2.GetType(), overrideableProperty2);
					}
					else
					{
						stack.SetTo(overrideableProperty2.GetType(), overrideableProperty2, j == 1, new Bounds1(weatherPrefab.m_CloudinessRange));
					}
				}
			}
		}
	}
```

- `private UpdateEffectsProperties() : System.Void`  

```csharp
private void UpdateEffectsProperties()
	{
		m_PrecipitationVFX.SetCheckedVector3(VFXIDs.CameraPosition, m_CameraUpdateSystem.position);
		m_PrecipitationVFX.SetCheckedVector3(VFXIDs.CameraDirection, m_CameraUpdateSystem.direction);
		m_PrecipitationVFX.SetCheckedVector3(VFXIDs.VolumeScale, new Vector3(precipitationVolumeScale, precipitationVolumeScale, precipitationVolumeScale));
		m_PrecipitationVFX.SetCheckedTexture(VFXIDs.WindTexture, m_WindTextureSystem.WindTexture);
		m_PrecipitationVFX.SetCheckedFloat(VFXIDs.CloudsAltitude, m_VolumetricClouds.bottomAltitude.value);
		m_PrecipitationVFX.SetCheckedVector4(VFXIDs.MapOffsetScale, m_TerrainSystem.mapOffsetScale);
		m_PrecipitationVFX.SetCheckedFloat(VFXIDs.RainStrength, m_ClimateSystem.precipitation);
		m_PrecipitationVFX.SetCheckedFloat(VFXIDs.SnowStrength, m_ClimateSystem.precipitation);
	}
```

- `private UpdateEffectsState() : System.Void`  

```csharp
private void UpdateEffectsState()
	{
		if (m_ClimateSystem.isPrecipitating && m_ClimateSystem.hail < 0.001f)
		{
			if ((float)m_ClimateSystem.temperature > 0f)
			{
				if (m_IsSnowing)
				{
					UpdateEffectState(PrecipitationType.Snow, start: false);
					m_IsSnowing = false;
				}
				if (!m_IsRaining)
				{
					UpdateEffectState(PrecipitationType.Rain, start: true);
					m_IsRaining = true;
				}
			}
			else
			{
				if (!m_IsSnowing)
				{
					UpdateEffectState(PrecipitationType.Snow, start: true);
					m_IsSnowing = true;
				}
				if (m_IsRaining)
				{
					UpdateEffectState(PrecipitationType.Rain, start: false);
					m_IsRaining = false;
				}
			}
		}
		else
		{
			if (m_IsRaining)
			{
				UpdateEffectState(PrecipitationType.Rain, start: false);
				m_IsRaining = false;
			}
			if (m_IsSnowing)
			{
				UpdateEffectState(PrecipitationType.Snow, start: false);
				m_IsSnowing = false;
			}
		}
		if (m_HailStorm && m_ClimateSystem.hail <= 0.001f)
		{
			UpdateEffectState(PrecipitationType.Hail, start: false);
			m_HailStorm = false;
		}
		else if (!m_HailStorm && m_ClimateSystem.hail > 0.001f)
		{
			UpdateEffectState(PrecipitationType.Hail, start: true);
			m_HailStorm = true;
		}
	}
```

- `private UpdateEffectState(Game.Rendering.ClimateRenderSystem+PrecipitationType type, System.Boolean start) : System.Void`  

```csharp
private void UpdateEffectState(PrecipitationType type, bool start)
	{
		if (GetEventName(type, start, out var name))
		{
			COSystemBase.baseLog.DebugFormat("PrecipitationVFX event {0}", name);
			m_PrecipitationVFX.SendEvent(name);
		}
	}
```

- `private UpdateVFXSpeed() : System.Void`  

```csharp
private void UpdateVFXSpeed()
	{
		if (globalEffectTimeStepFromSimulation)
		{
			float num = m_RenderingSystem.frameDelta / 60f;
			float smoothSpeed = m_SimulationSystem.smoothSpeed;
			VFXManager.fixedTimeStep = num * smoothSpeed;
			UnityEngine.Debug.Log("smoothedRenderTimeStep: " + num + " simulationSpeedMultiplier: " + smoothSpeed);
		}
		else
		{
			float num2 = m_RenderingSystem.frameDelta / math.max(1E-06f, base.CheckedStateRef.WorldUnmanaged.Time.DeltaTime * 60f);
			m_PrecipitationVFX.playRate = (weatherEffectTimeStepFromSimulation ? num2 : 1f);
			m_LightningVFX.playRate = (weatherEffectTimeStepFromSimulation ? num2 : 1f);
		}
	}
```

- `private UpdateVolumetricClouds() : System.Void`  

```csharp
private void UpdateVolumetricClouds()
	{
		float num = 1f + (1f - math.abs(math.dot(m_CameraUpdateSystem.direction, new float3(0f, 1f, 0f))));
		m_VolumetricClouds.fadeInMode.Override(VolumetricClouds.CloudFadeInMode.Manual);
		m_VolumetricClouds.fadeInStart.Override(math.max((m_CameraUpdateSystem.position.y - m_VolumetricClouds.bottomAltitude.value) * num, m_CameraUpdateSystem.nearClipPlane));
		m_VolumetricClouds.fadeInDistance.Override(m_VolumetricClouds.altitudeRange.value * 0.3f);
		m_VolumetricClouds.renderHook.Override((!(m_CameraUpdateSystem.position.y < m_VolumetricClouds.bottomAltitude.value)) ? VolumetricClouds.CloudHook.PostTransparent : VolumetricClouds.CloudHook.PreTransparent);
	}
```

- `private UpdateWeather() : System.Void`  

```csharp
private void UpdateWeather()
	{
		float timeOfYear = GetTimeOfYear();
		ClimateSystem.ClimateSample sample = m_ClimateSystem.SampleClimate(timeOfYear);
		if (m_PropertiesChanged)
		{
			SetData(m_PropertiesStack, m_FromWeatherPrefabs, m_ToWeatherPrefabs);
			m_PropertiesChanged = false;
		}
		float renderingDeltaTime = m_RenderingSystem.frameDelta / 60f;
		float deltaTime = base.CheckedStateRef.WorldUnmanaged.Time.DeltaTime;
		m_PropertiesStack.InterpolateOverrideData(deltaTime, renderingDeltaTime, sample, editMode);
	}
```


## Nested types

- `Game.Rendering.ClimateRenderSystem+VFXIDs`  
- `Game.Rendering.ClimateRenderSystem+PrecipitationType`  
- `Game.Rendering.ClimateRenderSystem+TypeHandle`  

