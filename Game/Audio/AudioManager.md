# Game.Audio.AudioManager

**Assembly:** `Game`  
**Namespace:** `Game.Audio`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPreDeserialize`, `Game.Serialization.IPreSerialize`  

**Attributes:** `CompilerGenerated`  

## Code

```csharp
public class AudioManager : Game.GameSystemBase, Colossal.Serialization.Entities.IDefaultSerializable, Colossal.Serialization.Entities.ISerializable, Game.Serialization.IPreDeserialize, Game.Serialization.IPreSerialize
{
    private System.Collections.Generic.List<Game.Audio.AudioManager+AudioInfo> m_AudioInfos;
    private System.Threading.SynchronizationContext m_MainThreadContext;
    private UnityEngine.Audio.AudioMixer m_Mixer;
    private UnityEngine.Audio.AudioMixerGroup m_AmbientGroup;
    private UnityEngine.Audio.AudioMixerGroup m_InGameGroup;
    private UnityEngine.Audio.AudioMixerGroup m_RadioGroup;
    private UnityEngine.Audio.AudioMixerGroup m_UIGroup;
    private UnityEngine.Audio.AudioMixerGroup m_MenuGroup;
    private UnityEngine.Audio.AudioMixerGroup m_WorldGroup;
    private UnityEngine.Audio.AudioMixerGroup m_ServiceBuildingGroup;
    private UnityEngine.Audio.AudioMixerGroup m_AudioGroupGroup;
    private UnityEngine.Audio.AudioMixerGroup m_DisasterGroup;
    private Game.Audio.AudioLoop m_MainMenuMusic;
    private UnityEngine.AudioSource m_UIAudioSource;
    private UnityEngine.AudioSource m_UIHtmlAudioSource;
    private UnityEngine.AudioListener m_AudioListener;
    private Unity.Collections.NativeQueue<Game.Effects.SourceUpdateInfo> m_SourceUpdateQueue;
    private Game.Effects.SourceUpdateData m_SourceUpdateData;
    private Unity.Jobs.JobHandle m_SourceUpdateWriter;
    private Game.Simulation.SimulationSystem m_SimulationSystem;
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem;
    private Game.Effects.EffectControlSystem m_EffectControlSystem;
    private Game.Common.RandomSeed m_RandomSeed;
    private System.Single m_FadeOutMenu;
    private System.Single m_DeltaTime;
    private System.Boolean m_IsGamePausedLastUpdate;
    private System.Boolean m_IsMenuActivatedLastUpdate;
    private System.Boolean m_ShouldUnpauseRadioAfterGameUnpaused;
    private System.String m_LastSaveRadioChannel;
    private System.Boolean m_LastSaveRadioSkipAds;
    private Game.Audio.AudioManager+FadeStatus m_AudioFadeStatus;
    private Game.Simulation.TimeSystem m_TimeSystem;
    private System.Collections.Generic.List<Game.Prefabs.Effects.SFX> m_Clips;
    private Unity.Collections.NativeParallelHashMap<Game.Effects.SourceInfo, System.Int32> m_CurrentEffects;
    private Unity.Entities.EntityQuery m_AmbientSettingsQuery;
    private Unity.Entities.EntityQuery m_SoundQuery;
    private Unity.Entities.EntityQuery m_WeatherAudioEntitiyQuery;
    private System.Collections.Generic.List<Game.Audio.AudioManager+CameraAmbientAudioInfo> m_CameraAmbientSources;
    private System.Collections.Generic.List<UnityEngine.AudioSource> m_TempAudioSources;
    private Game.Audio.Radio.Radio m_Radio;
    private Unity.Entities.Entity <followed>k__BackingField;
    private System.Int32 m_PlayCount;
    private Game.Audio.AudioManager+TypeHandle __TypeHandle;
    private static readonly Colossal.Logging.ILog log;
    private static Game.Audio.AudioManager <instance>k__BackingField;
    private static const System.Single kDopplerLevelReduceFactor;
    private static const System.String kMasterVolumeProperty;
    private static const System.String kRadioVolumeProperty;
    private static const System.String kUIVolumeProperty;
    private static const System.String kMenuVolumeProperty;
    private static const System.String kInGameVolumeProperty;
    private static const System.String kAmbienceVolumeProperty;
    private static const System.String kDisastersVolumeProperty;
    private static const System.String kWorldVolumeProperty;
    private static const System.String kAudioGroupsVolumeProperty;
    private static const System.String kServiceBuildingsVolumeProperty;

    public static Game.Audio.AudioManager instance { get; private set; }
    public UnityEngine.AudioSource UIHtmlAudioSource { get; }
    public Game.Audio.Radio.Radio radio { get; }
    private Unity.Entities.Entity followed { private get; set; }
    public System.Single masterVolume { get; set; }
    public System.Single radioVolume { get; set; }
    public System.Single uiVolume { get; set; }
    public System.Single menuVolume { get; set; }
    public System.Single ingameVolume { get; set; }
    public System.Single ambienceVolume { get; set; }
    public System.Single disastersVolume { get; set; }
    public System.Single worldVolume { get; set; }
    public System.Single audioGroupsVolume { get; set; }
    public System.Single serviceBuildingsVolume { get; set; }

    public AudioManager();

    private System.Void __AssignQueries(Unity.Entities.SystemState& state);
    public System.Void AddSourceUpdateWriter(Unity.Jobs.JobHandle jobHandle);
    private System.Void ClearCameraAmbientSources();
    public System.Void Deserialize<TReader>(TReader reader);
    private System.Void Fadeout(Game.Effects.SourceInfo sourceInfo, System.Int32 index);
    private UnityEngine.Audio.AudioMixerGroup GetAudioMixerGroup(Game.Effects.MixerGroup group);
    public static Unity.Mathematics.float3 GetClosestSourcePosition(Unity.Mathematics.float3 targetPosition, Game.Objects.Transform sourceTransform, Unity.Mathematics.float3 sourceOffset, Unity.Mathematics.float3 sourceSize);
    private System.Boolean GetEffect(Unity.Entities.DynamicBuffer<Game.Effects.EnabledEffect> effects, System.Int32 effectIndex, Game.Effects.EnabledEffect& effect);
    private System.Single GetFadedVolume(Game.Audio.AudioManager+FadeStatus status, Unity.Mathematics.float2 sfxFades, System.Single currentVolume, System.Single targetVolume);
    public System.Boolean GetRandomizeAudio(Unity.Entities.Entity sfxEntity, Game.Prefabs.Effects.SFX& sfx);
    public Game.Effects.SourceUpdateData GetSourceUpdateData(Unity.Jobs.JobHandle& deps);
    private System.Single GetVolume(System.String volumeProperty);
    public System.Void MoveAudioListenerForDoppler(Unity.Mathematics.float3 m_FollowOffset);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnCreateForCompiler();
    protected virtual System.Void OnDestroy();
    protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
    protected virtual System.Void OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
    protected virtual System.Void OnUpdate();
    public UnityEngine.AudioSource PlayExclusiveUISound(Unity.Entities.Entity clipEntity);
    public System.Void PlayLightningSFX(Unity.Mathematics.float3 targetPos);
    public System.Threading.Tasks.Task PlayMenuMusic(System.String tag);
    public System.Void PlayUISound(Unity.Entities.Entity clipEntity, System.Single volume);
    public System.Void PlayUISound(UnityEngine.AudioClip clip, System.Single volume);
    public System.Boolean PlayUISoundIfNotPlaying(Unity.Entities.Entity clipEntity, System.Single volume);
    public System.Boolean PlayUISoundIfNotPlaying(UnityEngine.AudioClip clipEntity, System.Single volume);
    public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
    public System.Void PreSerialize(Colossal.Serialization.Entities.Context context);
    public System.Int32 RegisterSFX(Game.Prefabs.Effects.SFX sfx);
    private System.Void RemoveAudio(Game.Effects.SourceInfo sourceInfo, System.Int32 index);
    public System.Void Reset();
    public System.Threading.Tasks.Task ResetAudioOnMainThread();
    public System.Void Serialize<TWriter>(TWriter writer);
    private System.Void SetAudioSourceData(UnityEngine.AudioSource audioSource, Game.Prefabs.Effects.SFX sfx, System.Single volume);
    public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
    public System.Void SetGlobalAudioSettings();
    private System.Void SetGlobalAudioSourcePosition(Game.Audio.AudioManager+CameraAmbientAudioInfo info, Unity.Mathematics.float3 position);
    private System.Void SetVolume(System.String volumeProperty, System.Single value);
    public System.Void StopExclusiveUISound(UnityEngine.AudioSource audioSource);
    public System.Void StopMenuMusic();
    private System.Void SyncAudioSources();
    public System.Void UpdateAudioListener(UnityEngine.Vector3 position, UnityEngine.Quaternion rotation);
    private System.Boolean UpdateAudioSource(UnityEngine.AudioSource audioSource, Game.Prefabs.Effects.SFX sfx, Game.Objects.Transform transform, System.Single intensity, System.Boolean disableDoppler, System.Int32 i, Game.Audio.AudioManager+FadeStatus status, Game.Effects.SourceInfo sourceInfo);
    private System.Void UpdateAudioSourceByVelocity(UnityEngine.AudioSource audioSource, System.Single velocity, Game.Prefabs.VehicleAudioEffectData vehicleData, Game.Audio.AudioManager+FadeStatus status);
    private System.Void UpdateGameAudioSetting();
    public System.Void UpdateGlobalAudioSources(UnityEngine.Transform cameraTransform);
    private System.Void UpdateMenuMusic();
    private System.Void UpdateTempAudioSources();
}
```


## Fields

- `private System.Collections.Generic.List<Game.Audio.AudioManager+AudioInfo> m_AudioInfos`  

```csharp
private System.Collections.Generic.List<Game.Audio.AudioManager+AudioInfo> m_AudioInfos;
```

- `private System.Threading.SynchronizationContext m_MainThreadContext`  

```csharp
private System.Threading.SynchronizationContext m_MainThreadContext;
```

- `private UnityEngine.Audio.AudioMixer m_Mixer`  

```csharp
private UnityEngine.Audio.AudioMixer m_Mixer;
```

- `private UnityEngine.Audio.AudioMixerGroup m_AmbientGroup`  

```csharp
private UnityEngine.Audio.AudioMixerGroup m_AmbientGroup;
```

- `private UnityEngine.Audio.AudioMixerGroup m_InGameGroup`  

```csharp
private UnityEngine.Audio.AudioMixerGroup m_InGameGroup;
```

- `private UnityEngine.Audio.AudioMixerGroup m_RadioGroup`  

```csharp
private UnityEngine.Audio.AudioMixerGroup m_RadioGroup;
```

- `private UnityEngine.Audio.AudioMixerGroup m_UIGroup`  

```csharp
private UnityEngine.Audio.AudioMixerGroup m_UIGroup;
```

- `private UnityEngine.Audio.AudioMixerGroup m_MenuGroup`  

```csharp
private UnityEngine.Audio.AudioMixerGroup m_MenuGroup;
```

- `private UnityEngine.Audio.AudioMixerGroup m_WorldGroup`  

```csharp
private UnityEngine.Audio.AudioMixerGroup m_WorldGroup;
```

- `private UnityEngine.Audio.AudioMixerGroup m_ServiceBuildingGroup`  

```csharp
private UnityEngine.Audio.AudioMixerGroup m_ServiceBuildingGroup;
```

- `private UnityEngine.Audio.AudioMixerGroup m_AudioGroupGroup`  

```csharp
private UnityEngine.Audio.AudioMixerGroup m_AudioGroupGroup;
```

- `private UnityEngine.Audio.AudioMixerGroup m_DisasterGroup`  

```csharp
private UnityEngine.Audio.AudioMixerGroup m_DisasterGroup;
```

- `private Game.Audio.AudioLoop m_MainMenuMusic`  

```csharp
private Game.Audio.AudioLoop m_MainMenuMusic;
```

- `private UnityEngine.AudioSource m_UIAudioSource`  

```csharp
private UnityEngine.AudioSource m_UIAudioSource;
```

- `private UnityEngine.AudioSource m_UIHtmlAudioSource`  

```csharp
private UnityEngine.AudioSource m_UIHtmlAudioSource;
```

- `private UnityEngine.AudioListener m_AudioListener`  

```csharp
private UnityEngine.AudioListener m_AudioListener;
```

- `private Unity.Collections.NativeQueue<Game.Effects.SourceUpdateInfo> m_SourceUpdateQueue`  

```csharp
private Unity.Collections.NativeQueue<Game.Effects.SourceUpdateInfo> m_SourceUpdateQueue;
```

- `private Game.Effects.SourceUpdateData m_SourceUpdateData`  

```csharp
private Game.Effects.SourceUpdateData m_SourceUpdateData;
```

- `private Unity.Jobs.JobHandle m_SourceUpdateWriter`  

```csharp
private Unity.Jobs.JobHandle m_SourceUpdateWriter;
```

- `private Game.Simulation.SimulationSystem m_SimulationSystem`  

```csharp
private Game.Simulation.SimulationSystem m_SimulationSystem;
```

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem`  

```csharp
private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem;
```

- `private Game.Effects.EffectControlSystem m_EffectControlSystem`  

```csharp
private Game.Effects.EffectControlSystem m_EffectControlSystem;
```

- `private Game.Common.RandomSeed m_RandomSeed`  

```csharp
private Game.Common.RandomSeed m_RandomSeed;
```

- `private System.Single m_FadeOutMenu`  

```csharp
private System.Single m_FadeOutMenu;
```

- `private System.Single m_DeltaTime`  

```csharp
private System.Single m_DeltaTime;
```

- `private System.Boolean m_IsGamePausedLastUpdate`  

```csharp
private System.Boolean m_IsGamePausedLastUpdate;
```

- `private System.Boolean m_IsMenuActivatedLastUpdate`  

```csharp
private System.Boolean m_IsMenuActivatedLastUpdate;
```

- `private System.Boolean m_ShouldUnpauseRadioAfterGameUnpaused`  

```csharp
private System.Boolean m_ShouldUnpauseRadioAfterGameUnpaused;
```

- `private System.String m_LastSaveRadioChannel`  

```csharp
private System.String m_LastSaveRadioChannel;
```

- `private System.Boolean m_LastSaveRadioSkipAds`  

```csharp
private System.Boolean m_LastSaveRadioSkipAds;
```

- `private Game.Audio.AudioManager+FadeStatus m_AudioFadeStatus`  

```csharp
private Game.Audio.AudioManager+FadeStatus m_AudioFadeStatus;
```

- `private Game.Simulation.TimeSystem m_TimeSystem`  

```csharp
private Game.Simulation.TimeSystem m_TimeSystem;
```

- `private System.Collections.Generic.List<Game.Prefabs.Effects.SFX> m_Clips`  

```csharp
private System.Collections.Generic.List<Game.Prefabs.Effects.SFX> m_Clips;
```

- `private Unity.Collections.NativeParallelHashMap<Game.Effects.SourceInfo, System.Int32> m_CurrentEffects`  

```csharp
private Unity.Collections.NativeParallelHashMap<Game.Effects.SourceInfo, System.Int32> m_CurrentEffects;
```

- `private Unity.Entities.EntityQuery m_AmbientSettingsQuery`  

```csharp
private Unity.Entities.EntityQuery m_AmbientSettingsQuery;
```

- `private Unity.Entities.EntityQuery m_SoundQuery`  

```csharp
private Unity.Entities.EntityQuery m_SoundQuery;
```

- `private Unity.Entities.EntityQuery m_WeatherAudioEntitiyQuery`  

```csharp
private Unity.Entities.EntityQuery m_WeatherAudioEntitiyQuery;
```

- `private System.Collections.Generic.List<Game.Audio.AudioManager+CameraAmbientAudioInfo> m_CameraAmbientSources`  

```csharp
private System.Collections.Generic.List<Game.Audio.AudioManager+CameraAmbientAudioInfo> m_CameraAmbientSources;
```

- `private System.Collections.Generic.List<UnityEngine.AudioSource> m_TempAudioSources`  

```csharp
private System.Collections.Generic.List<UnityEngine.AudioSource> m_TempAudioSources;
```

- `private Game.Audio.Radio.Radio m_Radio`  

```csharp
private Game.Audio.Radio.Radio m_Radio;
```

- `private Unity.Entities.Entity <followed>k__BackingField`  

```csharp
private Unity.Entities.Entity <followed>k__BackingField;
```

- `private System.Int32 m_PlayCount`  

```csharp
private System.Int32 m_PlayCount;
```

- `private Game.Audio.AudioManager+TypeHandle __TypeHandle`  

```csharp
private Game.Audio.AudioManager+TypeHandle __TypeHandle;
```

- `private static readonly Colossal.Logging.ILog log`  

```csharp
private static readonly Colossal.Logging.ILog log;
```

- `private static Game.Audio.AudioManager <instance>k__BackingField`  

```csharp
private static Game.Audio.AudioManager <instance>k__BackingField;
```

- `private static const System.Single kDopplerLevelReduceFactor`  

```csharp
private static const System.Single kDopplerLevelReduceFactor;
```

- `private static const System.String kMasterVolumeProperty`  

```csharp
private static const System.String kMasterVolumeProperty;
```

- `private static const System.String kRadioVolumeProperty`  

```csharp
private static const System.String kRadioVolumeProperty;
```

- `private static const System.String kUIVolumeProperty`  

```csharp
private static const System.String kUIVolumeProperty;
```

- `private static const System.String kMenuVolumeProperty`  

```csharp
private static const System.String kMenuVolumeProperty;
```

- `private static const System.String kInGameVolumeProperty`  

```csharp
private static const System.String kInGameVolumeProperty;
```

- `private static const System.String kAmbienceVolumeProperty`  

```csharp
private static const System.String kAmbienceVolumeProperty;
```

- `private static const System.String kDisastersVolumeProperty`  

```csharp
private static const System.String kDisastersVolumeProperty;
```

- `private static const System.String kWorldVolumeProperty`  

```csharp
private static const System.String kWorldVolumeProperty;
```

- `private static const System.String kAudioGroupsVolumeProperty`  

```csharp
private static const System.String kAudioGroupsVolumeProperty;
```

- `private static const System.String kServiceBuildingsVolumeProperty`  

```csharp
private static const System.String kServiceBuildingsVolumeProperty;
```


## Properties

- `public static Game.Audio.AudioManager instance { get; private set }`  

```csharp
public static Game.Audio.AudioManager instance { get; private set; }
```

- `public UnityEngine.AudioSource UIHtmlAudioSource { get }`  

```csharp
public UnityEngine.AudioSource UIHtmlAudioSource { get; }
```

- `public Game.Audio.Radio.Radio radio { get }`  

```csharp
public Game.Audio.Radio.Radio radio { get; }
```

- `private Unity.Entities.Entity followed { private get; set }`  

```csharp
private Unity.Entities.Entity followed { private get; set; }
```

- `public System.Single masterVolume { get; set }`  

```csharp
public System.Single masterVolume { get; set; }
```

- `public System.Single radioVolume { get; set }`  

```csharp
public System.Single radioVolume { get; set; }
```

- `public System.Single uiVolume { get; set }`  

```csharp
public System.Single uiVolume { get; set; }
```

- `public System.Single menuVolume { get; set }`  

```csharp
public System.Single menuVolume { get; set; }
```

- `public System.Single ingameVolume { get; set }`  

```csharp
public System.Single ingameVolume { get; set; }
```

- `public System.Single ambienceVolume { get; set }`  

```csharp
public System.Single ambienceVolume { get; set; }
```

- `public System.Single disastersVolume { get; set }`  

```csharp
public System.Single disastersVolume { get; set; }
```

- `public System.Single worldVolume { get; set }`  

```csharp
public System.Single worldVolume { get; set; }
```

- `public System.Single audioGroupsVolume { get; set }`  

```csharp
public System.Single audioGroupsVolume { get; set; }
```

- `public System.Single serviceBuildingsVolume { get; set }`  

```csharp
public System.Single serviceBuildingsVolume { get; set; }
```


## Constructors

- `public AudioManager()`  

```csharp
[Preserve]
	public AudioManager()
	{
	}
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private void __AssignQueries(ref SystemState state)
	{
		new EntityQueryBuilder(Allocator.Temp).Dispose();
	}
```

- `public AddSourceUpdateWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public void AddSourceUpdateWriter(JobHandle jobHandle)
	{
		m_SourceUpdateWriter = JobHandle.CombineDependencies(m_SourceUpdateWriter, jobHandle);
	}
```

- `private ClearCameraAmbientSources() : System.Void`  

```csharp
private void ClearCameraAmbientSources()
	{
		foreach (CameraAmbientAudioInfo item in m_CameraAmbientSources)
		{
			AudioSourcePool.Release(item.source);
		}
		m_CameraAmbientSources.Clear();
	}
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private Fadeout(Game.Effects.SourceInfo sourceInfo, System.Int32 index) : System.Void`  

```csharp
private void Fadeout(SourceInfo sourceInfo, int index)
	{
		if (index < m_AudioInfos.Count && m_AudioInfos[index].m_AudioSource != null)
		{
			AudioInfo value = m_AudioInfos[index];
			value.m_SourceInfo = sourceInfo;
			value.m_Status = FadeStatus.FadeOut;
			m_AudioInfos[index] = value;
		}
	}
```

- `private GetAudioMixerGroup(Game.Effects.MixerGroup group) : UnityEngine.Audio.AudioMixerGroup`  

```csharp
private AudioMixerGroup GetAudioMixerGroup(MixerGroup group)
	{
		return group switch
		{
			MixerGroup.Ambient => m_AmbientGroup, 
			MixerGroup.Menu => m_MenuGroup, 
			MixerGroup.Radio => m_RadioGroup, 
			MixerGroup.UI => m_UIGroup, 
			MixerGroup.World => m_WorldGroup, 
			MixerGroup.ServiceBuildings => m_ServiceBuildingGroup, 
			MixerGroup.AudioGroups => m_AudioGroupGroup, 
			MixerGroup.Disasters => m_DisasterGroup, 
			_ => null, 
		};
	}
```

- `public static GetClosestSourcePosition(Unity.Mathematics.float3 targetPosition, Game.Objects.Transform sourceTransform, Unity.Mathematics.float3 sourceOffset, Unity.Mathematics.float3 sourceSize) : Unity.Mathematics.float3`  

```csharp
public static float3 GetClosestSourcePosition(float3 targetPosition, Game.Objects.Transform sourceTransform, float3 sourceOffset, float3 sourceSize)
	{
		float3 @float = ObjectUtils.WorldToLocal(ObjectUtils.InverseTransform(sourceTransform), targetPosition);
		sourceOffset.x = math.clamp(@float.x, sourceOffset.x - sourceSize.x, sourceOffset.x + sourceSize.x);
		sourceOffset.y = math.clamp(@float.y, sourceOffset.y - sourceSize.y, sourceOffset.y + sourceSize.y);
		sourceOffset.z = math.clamp(@float.z, sourceOffset.z - sourceSize.z, sourceOffset.z + sourceSize.z);
		return ObjectUtils.LocalToWorld(sourceTransform, sourceOffset);
	}
```

- `private GetEffect(Unity.Entities.DynamicBuffer<Game.Effects.EnabledEffect> effects, System.Int32 effectIndex, Game.Effects.EnabledEffect& effect) : System.Boolean`  

```csharp
private bool GetEffect(DynamicBuffer<EnabledEffect> effects, int effectIndex, out EnabledEffect effect)
	{
		for (int i = 0; i < effects.Length; i++)
		{
			effect = effects[i];
			if (effect.m_EffectIndex == effectIndex)
			{
				return true;
			}
		}
		effect = default(EnabledEffect);
		return false;
	}
```

- `private GetFadedVolume(Game.Audio.AudioManager+FadeStatus status, Unity.Mathematics.float2 sfxFades, System.Single currentVolume, System.Single targetVolume) : System.Single`  

```csharp
private float GetFadedVolume(FadeStatus status, float2 sfxFades, float currentVolume, float targetVolume)
	{
		if (sfxFades.x != 0f && status == FadeStatus.FadeIn && math.abs(currentVolume - targetVolume) > float.Epsilon)
		{
			if (currentVolume > targetVolume)
			{
				return math.saturate(currentVolume - m_DeltaTime / sfxFades.x * targetVolume);
			}
			return math.saturate(currentVolume + m_DeltaTime / sfxFades.x * targetVolume);
		}
		if (status == FadeStatus.FadeOut)
		{
			if (sfxFades.y != 0f && currentVolume - 0f > float.Epsilon)
			{
				return math.saturate(currentVolume - m_DeltaTime / sfxFades.y * targetVolume);
			}
			targetVolume = 0f;
		}
		return targetVolume;
	}
```

- `public GetRandomizeAudio(Unity.Entities.Entity sfxEntity, Game.Prefabs.Effects.SFX& sfx) : System.Boolean`  

```csharp
public bool GetRandomizeAudio(Entity sfxEntity, out SFX sfx)
	{
		sfx = null;
		if (base.EntityManager.HasComponent<AudioRandomizeData>(sfxEntity) && base.EntityManager.TryGetBuffer(sfxEntity, isReadOnly: true, out DynamicBuffer<AudioRandomizeData> buffer))
		{
			Unity.Mathematics.Random random = new Unity.Mathematics.Random((uint)DateTime.Now.Ticks);
			int index = random.NextInt(buffer.Length);
			Entity sFXEntity = buffer[index].m_SFXEntity;
			sfx = m_Clips[base.EntityManager.GetComponentData<AudioEffectData>(sFXEntity).m_AudioClipId];
			return true;
		}
		return false;
	}
```

- `public GetSourceUpdateData(Unity.Jobs.JobHandle& deps) : Game.Effects.SourceUpdateData`  

```csharp
public SourceUpdateData GetSourceUpdateData(out JobHandle deps)
	{
		deps = m_SourceUpdateWriter;
		return m_SourceUpdateData;
	}
```

- `private GetVolume(System.String volumeProperty) : System.Single`  

```csharp
private float GetVolume(string volumeProperty)
	{
		if (m_Mixer.GetFloat(volumeProperty, out var value))
		{
			return Mathf.Pow(10f, value / 20f);
		}
		return 1f;
	}
```

- `public MoveAudioListenerForDoppler(Unity.Mathematics.float3 m_FollowOffset) : System.Void`  

```csharp
public void MoveAudioListenerForDoppler(float3 m_FollowOffset)
	{
		m_AudioListener.transform.position += new Vector3(m_FollowOffset.x, m_FollowOffset.y, m_FollowOffset.z);
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		instance = this;
		AudioSourcePool.Reset();
		m_MainThreadContext = SynchronizationContext.Current;
		m_AmbientSettingsQuery = GetEntityQuery(ComponentType.ReadOnly<AmbientAudioSettingsData>(), ComponentType.ReadOnly<AmbientAudioEffect>());
		m_SoundQuery = GetEntityQuery(ComponentType.ReadOnly<ToolUXSoundSettingsData>());
		m_WeatherAudioEntitiyQuery = GetEntityQuery(ComponentType.ReadOnly<WeatherAudioData>());
		m_AudioListener = new GameObject("AudioListener").AddComponent<AudioListener>();
		UnityEngine.Object.DontDestroyOnLoad(m_AudioListener);
		m_Mixer = Resources.Load<AudioMixer>("Audio/MasterMixer");
		m_AmbientGroup = m_Mixer.FindMatchingGroups("Ambience")[0];
		m_RadioGroup = m_Mixer.FindMatchingGroups("Radio")[0];
		m_InGameGroup = m_Mixer.FindMatchingGroups("InGame")[0];
		m_UIGroup = m_Mixer.FindMatchingGroups("UI")[0];
		m_MenuGroup = m_Mixer.FindMatchingGroups("Menu")[0];
		m_WorldGroup = m_Mixer.FindMatchingGroups("World")[0];
		m_ServiceBuildingGroup = m_Mixer.FindMatchingGroups("ServiceBuildings")[0];
		m_AudioGroupGroup = m_Mixer.FindMatchingGroups("AudioGroups")[0];
		m_DisasterGroup = m_Mixer.FindMatchingGroups("Disasters")[0];
		m_TimeSystem = base.World.GetOrCreateSystemManaged<TimeSystem>();
		m_SimulationSystem = base.World.GetOrCreateSystemManaged<SimulationSystem>();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_GameScreenUISystem = base.World.GetOrCreateSystemManaged<GameScreenUISystem>();
		m_EffectControlSystem = base.World.GetOrCreateSystemManaged<EffectControlSystem>();
		m_Radio = new Game.Audio.Radio.Radio(m_RadioGroup);
		m_SourceUpdateQueue = new NativeQueue<SourceUpdateInfo>(Allocator.Persistent);
		m_SourceUpdateData = new SourceUpdateData(m_SourceUpdateQueue.AsParallelWriter());
		m_CurrentEffects = new NativeParallelHashMap<SourceInfo, int>(128, Allocator.Persistent);
		m_RandomSeed = default(RandomSeed);
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
		m_MainMenuMusic?.Dispose();
		m_Radio?.Disable();
		m_CurrentEffects.Dispose();
		if (m_SourceUpdateQueue.IsCreated)
		{
			m_SourceUpdateWriter.Complete();
			m_SourceUpdateQueue.Dispose();
		}
		m_TempAudioSources.Clear();
		base.OnDestroy();
		ClearCameraAmbientSources();
	}
```

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected override void OnGameLoaded(Context serializationContext)
	{
		base.OnGameLoaded(serializationContext);
		Purpose purpose = serializationContext.purpose;
		if (purpose == Purpose.NewGame || purpose == Purpose.LoadGame)
		{
			m_Radio.RestoreRadioSettings(m_LastSaveRadioChannel, m_LastSaveRadioSkipAds);
			m_Radio.Reload();
		}
	}
```

- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGameLoadingComplete(Purpose purpose, GameMode mode)
	{
		base.OnGameLoadingComplete(purpose, mode);
		if (mode.IsGameOrEditor())
		{
			StopMenuMusic();
		}
	}
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected override void OnGamePreload(Purpose purpose, GameMode mode)
	{
		base.OnGamePreload(purpose, mode);
		m_Radio.Disable();
		Reset();
	}
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
[Preserve]
	protected override void OnUpdate()
	{
		m_DeltaTime = UnityEngine.Time.deltaTime;
		UpdateMenuMusic();
		if (GameManager.instance.isGameLoading)
		{
			return;
		}
		if (GameManager.instance.gameMode != GameMode.Game)
		{
			m_SourceUpdateWriter.Complete();
			m_SourceUpdateQueue.Clear();
			return;
		}
		if (m_CameraAmbientSources.Count == 0)
		{
			SetGlobalAudioSettings();
		}
		if (m_TempAudioSources.Count > 0)
		{
			UpdateTempAudioSources();
		}
		UpdateGameAudioSetting();
		m_Radio.Update(m_TimeSystem.normalizedTime);
		Camera main = Camera.main;
		if (main == null)
		{
			return;
		}
		ComponentLookup<Game.Tools.EditorContainer> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<PrefabRef> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_PrefabRef_RO_ComponentLookup, ref base.CheckedStateRef);
		BufferLookup<AudioSourceData> bufferLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_AudioSourceData_RO_BufferLookup, ref base.CheckedStateRef);
		BufferLookup<Effect> bufferLookup2 = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_Effect_RO_BufferLookup, ref base.CheckedStateRef);
		BufferLookup<EnabledEffect> bufferLookup3 = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Effects_EnabledEffect_RO_BufferLookup, ref base.CheckedStateRef);
		ComponentLookup<AudioEffectData> componentLookup3 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AudioEffectData_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<EffectInstance> componentLookup4 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Effects_EffectInstance_RO_ComponentLookup, ref base.CheckedStateRef);
		m_SourceUpdateWriter.Complete();
		Unity.Mathematics.Random random = m_RandomSeed.GetRandom((int)m_SimulationSystem.frameIndex);
		JobHandle dependencies;
		NativeList<EnabledEffectData> enabledData = m_EffectControlSystem.GetEnabledData(readOnly: true, out dependencies);
		dependencies.Complete();
		SourceUpdateInfo item;
		while (m_SourceUpdateQueue.TryDequeue(out item))
		{
			SourceInfo sourceInfo = item.m_SourceInfo;
			bool flag = m_CurrentEffects.ContainsKey(sourceInfo);
			if (item.m_Type == SourceUpdateType.Add)
			{
				if (!flag)
				{
					if (!componentLookup2.HasComponent(sourceInfo.m_Entity))
					{
						continue;
					}
					Entity entity = componentLookup2[sourceInfo.m_Entity].m_Prefab;
					float num = 0f;
					bool flag2 = false;
					if (sourceInfo.m_EffectIndex != -1)
					{
						DynamicBuffer<EnabledEffect> effects = bufferLookup3[sourceInfo.m_Entity];
						Game.Tools.EditorContainer componentData;
						if (bufferLookup2.TryGetBuffer(entity, out var bufferData))
						{
							if (GetEffect(effects, sourceInfo.m_EffectIndex, out var effect))
							{
								Effect effect2 = bufferData[sourceInfo.m_EffectIndex];
								EnabledEffectData enabledEffectData = enabledData[effect.m_EnabledIndex];
								num = enabledEffectData.m_Intensity;
								flag2 = (enabledEffectData.m_Flags & EnabledEffectFlags.AudioDisabled) != 0;
								entity = effect2.m_Effect;
							}
						}
						else if (componentLookup.TryGetComponent(sourceInfo.m_Entity, out componentData) && effects.Length != 0)
						{
							EnabledEffectData enabledEffectData2 = enabledData[effects[0].m_EnabledIndex];
							num = enabledEffectData2.m_Intensity;
							flag2 = (enabledEffectData2.m_Flags & EnabledEffectFlags.AudioDisabled) != 0;
							entity = componentData.m_Prefab;
						}
					}
					else
					{
						num = componentLookup4[sourceInfo.m_Entity].m_Intensity;
					}
					if (bufferLookup.HasBuffer(entity))
					{
						DynamicBuffer<AudioSourceData> dynamicBuffer = bufferLookup[entity];
						int index = random.NextInt(dynamicBuffer.Length);
						Entity sFXEntity = dynamicBuffer[index].m_SFXEntity;
						int audioClipId = componentLookup3[sFXEntity].m_AudioClipId;
						SFX sFX = m_Clips[audioClipId];
						float num2 = sFX.m_Volume * num;
						if (num2 > 0.001f && !flag2)
						{
							num2 = GetFadedVolume(FadeStatus.FadeIn, sFX.m_FadeTimes, 0f, num2);
							AudioSource audioSource = AudioSourcePool.Get();
							SetAudioSourceData(audioSource, m_Clips[audioClipId], num2);
							m_CurrentEffects.Add(sourceInfo, m_AudioInfos.Count);
							AudioSourcePool.Play(audioSource);
							m_AudioInfos.Add(new AudioInfo
							{
								m_SourceInfo = sourceInfo,
								m_SFXEntity = sFXEntity,
								m_AudioSource = audioSource,
								m_Status = FadeStatus.FadeIn
							});
						}
					}
				}
				else
				{
					int index2 = m_CurrentEffects[sourceInfo];
					AudioInfo value = m_AudioInfos[index2];
					value.m_Status = FadeStatus.FadeIn;
					m_AudioInfos[index2] = value;
				}
			}
			else if (item.m_Type == SourceUpdateType.Remove)
			{
				if (flag)
				{
					int index3 = m_CurrentEffects[sourceInfo];
					Fadeout(sourceInfo, index3);
				}
			}
			else if (item.m_Type == SourceUpdateType.WrongPrefab)
			{
				if (flag)
				{
					int num3 = m_CurrentEffects[sourceInfo];
					m_CurrentEffects.Remove(sourceInfo);
					sourceInfo.m_EffectIndex = -2 - sourceInfo.m_EffectIndex;
					while (!m_CurrentEffects.TryAdd(sourceInfo, num3))
					{
						sourceInfo.m_EffectIndex--;
					}
					Fadeout(sourceInfo, num3);
				}
			}
			else if (item.m_Type == SourceUpdateType.Temp)
			{
				if (bufferLookup.HasBuffer(sourceInfo.m_Entity))
				{
					DynamicBuffer<AudioSourceData> dynamicBuffer2 = bufferLookup[sourceInfo.m_Entity];
					int index4 = random.NextInt(dynamicBuffer2.Length);
					Entity sFXEntity2 = dynamicBuffer2[index4].m_SFXEntity;
					int audioClipId2 = componentLookup3[sFXEntity2].m_AudioClipId;
					SFX sFX2 = m_Clips[audioClipId2];
					float volume = sFX2.m_Volume;
					float num4 = math.distance(main.transform.position, item.m_Transform.m_Position);
					if (volume > 0.001f && num4 < sFX2.m_MinMaxDistance.y)
					{
						volume = GetFadedVolume(FadeStatus.FadeIn, sFX2.m_FadeTimes, 0f, volume);
						AudioSource audioSource2 = AudioSourcePool.Get();
						SetAudioSourceData(audioSource2, m_Clips[audioClipId2], volume);
						audioSource2.transform.position = item.m_Transform.m_Position;
						AudioSourcePool.Play(audioSource2);
						m_TempAudioSources.Add(audioSource2);
					}
				}
			}
			else if (item.m_Type == SourceUpdateType.Snap)
			{
				Entity snapSound = m_SoundQuery.GetSingleton<ToolUXSoundSettingsData>().m_SnapSound;
				PlayUISound(snapSound);
			}
		}
		base.Dependency.Complete();
		SyncAudioSources();
	}
```

- `public PlayExclusiveUISound(Unity.Entities.Entity clipEntity) : UnityEngine.AudioSource`  

```csharp
public AudioSource PlayExclusiveUISound(Entity clipEntity)
	{
		AudioSource audioSource = null;
		if (base.EntityManager.HasComponent<AudioEffectData>(clipEntity))
		{
			SFX sFX = m_Clips[base.EntityManager.GetComponentData<AudioEffectData>(clipEntity).m_AudioClipId];
			if (sFX.m_AudioClip != null)
			{
				audioSource = AudioSourcePool.Get();
				audioSource.loop = sFX.m_Loop;
				audioSource.pitch = sFX.m_Pitch;
				audioSource.volume = sFX.m_Volume;
				audioSource.outputAudioMixerGroup = m_UIGroup;
				audioSource.dopplerLevel = 0f;
				audioSource.playOnAwake = false;
				audioSource.spatialBlend = 0f;
				audioSource.ignoreListenerPause = true;
				audioSource.clip = sFX.m_AudioClip;
				audioSource.timeSamples = 0;
				AudioSourcePool.Play(audioSource);
			}
			else
			{
				log.WarnFormat("PlayUISound invoked with no audio clip");
			}
		}
		return audioSource;
	}
```

- `public PlayLightningSFX(Unity.Mathematics.float3 targetPos) : System.Void`  

```csharp
public void PlayLightningSFX(float3 targetPos)
	{
		WeatherAudioData componentData = base.EntityManager.GetComponentData<WeatherAudioData>(m_WeatherAudioEntitiyQuery.GetSingletonEntity());
		float delay = math.distance(m_AudioListener.transform.position, targetPos) / componentData.m_LightningSoundSpeed;
		if (!GetRandomizeAudio(componentData.m_LightningAudio, out var sfx))
		{
			sfx = m_Clips[base.EntityManager.GetComponentData<AudioEffectData>(componentData.m_LightningAudio).m_AudioClipId];
		}
		if (sfx.m_AudioClip != null)
		{
			AudioSource audioSource = AudioSourcePool.Get();
			audioSource.clip = sfx.m_AudioClip;
			audioSource.transform.position = targetPos;
			audioSource.outputAudioMixerGroup = GetAudioMixerGroup(sfx.m_MixerGroup);
			audioSource.pitch = sfx.m_Pitch;
			audioSource.volume = sfx.m_Volume;
			audioSource.spatialBlend = sfx.m_SpatialBlend;
			audioSource.dopplerLevel = sfx.m_Doppler;
			audioSource.spread = sfx.m_Spread;
			audioSource.loop = sfx.m_Loop;
			audioSource.minDistance = sfx.m_MinMaxDistance.x;
			audioSource.maxDistance = sfx.m_MinMaxDistance.y;
			audioSource.rolloffMode = sfx.m_RolloffMode;
			if (sfx.m_RolloffMode == AudioRolloffMode.Custom)
			{
				audioSource.SetCustomCurve(AudioSourceCurveType.CustomRolloff, sfx.m_RolloffCurve);
			}
			audioSource.timeSamples = 0;
			audioSource.ignoreListenerPause = false;
			audioSource.priority = sfx.m_Priority;
			AudioSourcePool.PlayDelayed(audioSource, delay);
			m_TempAudioSources.Add(audioSource);
		}
	}
```

- `public PlayMenuMusic(System.String tag) : System.Threading.Tasks.Task`  

```csharp
public async Task PlayMenuMusic(string tag)
	{
		AudioAsset randomAsset = AssetDatabase.global.GetRandomAsset(SearchFilter<AudioAsset>.ByCondition((AudioAsset asset) => asset.ContainsTag(tag)));
		if (randomAsset != null)
		{
			m_MainMenuMusic = new AudioLoop(randomAsset, m_Mixer, m_MenuGroup);
			await m_MainMenuMusic.Start(m_PlayCount > 0);
			m_Radio?.Disable();
			m_PlayCount++;
		}
	}
```

- `public PlayUISound(Unity.Entities.Entity clipEntity, System.Single volume = 1) : System.Void`  

```csharp
public void PlayUISound(AudioClip clip, float volume = 1f)
	{
		if (clip != null)
		{
			if (m_UIAudioSource == null)
			{
				GameObject gameObject = new GameObject("UIAudioSource");
				m_UIAudioSource = gameObject.AddComponent<AudioSource>();
				m_UIAudioSource.outputAudioMixerGroup = m_UIGroup;
				m_UIAudioSource.dopplerLevel = 0f;
				m_UIAudioSource.playOnAwake = false;
				m_UIAudioSource.spatialBlend = 0f;
				m_UIAudioSource.ignoreListenerPause = true;
				UnityEngine.Object.DontDestroyOnLoad(gameObject);
			}
			m_UIAudioSource.PlayOneShot(clip, volume);
		}
		else
		{
			log.WarnFormat("PlayUISound invoked with no audio clip");
		}
	}
```

- `public PlayUISound(UnityEngine.AudioClip clip, System.Single volume = 1) : System.Void`  

```csharp
public void PlayUISound(AudioClip clip, float volume = 1f)
	{
		if (clip != null)
		{
			if (m_UIAudioSource == null)
			{
				GameObject gameObject = new GameObject("UIAudioSource");
				m_UIAudioSource = gameObject.AddComponent<AudioSource>();
				m_UIAudioSource.outputAudioMixerGroup = m_UIGroup;
				m_UIAudioSource.dopplerLevel = 0f;
				m_UIAudioSource.playOnAwake = false;
				m_UIAudioSource.spatialBlend = 0f;
				m_UIAudioSource.ignoreListenerPause = true;
				UnityEngine.Object.DontDestroyOnLoad(gameObject);
			}
			m_UIAudioSource.PlayOneShot(clip, volume);
		}
		else
		{
			log.WarnFormat("PlayUISound invoked with no audio clip");
		}
	}
```

- `public PlayUISoundIfNotPlaying(Unity.Entities.Entity clipEntity, System.Single volume = 1) : System.Boolean`  

```csharp
public bool PlayUISoundIfNotPlaying(AudioClip clipEntity, float volume = 1f)
	{
		if (m_UIAudioSource == null || !m_UIAudioSource.isPlaying)
		{
			PlayUISound(clipEntity, volume);
			return true;
		}
		return false;
	}
```

- `public PlayUISoundIfNotPlaying(UnityEngine.AudioClip clipEntity, System.Single volume = 1) : System.Boolean`  

```csharp
public bool PlayUISoundIfNotPlaying(AudioClip clipEntity, float volume = 1f)
	{
		if (m_UIAudioSource == null || !m_UIAudioSource.isPlaying)
		{
			PlayUISound(clipEntity, volume);
			return true;
		}
		return false;
	}
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreDeserialize(Context context)
	{
		m_LastSaveRadioChannel = string.Empty;
		m_LastSaveRadioSkipAds = false;
	}
```

- `public PreSerialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void PreSerialize(Context context)
	{
		m_LastSaveRadioChannel = string.Empty;
		m_LastSaveRadioSkipAds = false;
	}
```

- `public RegisterSFX(Game.Prefabs.Effects.SFX sfx) : System.Int32`  

```csharp
public int RegisterSFX(SFX sfx)
	{
		int num = m_Clips.IndexOf(sfx);
		if (num == -1)
		{
			int count = m_Clips.Count;
			m_Clips.Add(sfx);
			return count;
		}
		return num;
	}
```

- `private RemoveAudio(Game.Effects.SourceInfo sourceInfo, System.Int32 index) : System.Void`  

```csharp
private void RemoveAudio(SourceInfo sourceInfo, int index)
	{
		if (m_AudioInfos[index].m_AudioSource != null)
		{
			AudioSourcePool.Release(m_AudioInfos[index].m_AudioSource);
		}
		m_CurrentEffects.Remove(sourceInfo);
		if (index < m_AudioInfos.Count - 1)
		{
			m_AudioInfos[index] = m_AudioInfos[m_AudioInfos.Count - 1];
			m_CurrentEffects[m_AudioInfos[index].m_SourceInfo] = index;
		}
		m_AudioInfos.RemoveAt(m_AudioInfos.Count - 1);
	}
```

- `public Reset() : System.Void`  

```csharp
public void Reset()
	{
		ClearCameraAmbientSources();
		for (int i = 0; i < m_AudioInfos.Count; i++)
		{
			AudioSourcePool.Release(m_AudioInfos[i].m_AudioSource);
		}
		m_CurrentEffects.Clear();
		m_AudioInfos.Clear();
	}
```

- `public ResetAudioOnMainThread() : System.Threading.Tasks.Task`  

```csharp
public async Task ResetAudioOnMainThread()
	{
		TaskCompletionSource<bool> taskCompletion = new TaskCompletionSource<bool>();
		m_MainThreadContext.Send(delegate
		{
			Reset();
			taskCompletion.SetResult(result: true);
		}, null);
		await taskCompletion.Task;
	}
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `private SetAudioSourceData(UnityEngine.AudioSource audioSource, Game.Prefabs.Effects.SFX sfx, System.Single volume) : System.Void`  

```csharp
private void SetAudioSourceData(AudioSource audioSource, SFX sfx, float volume)
	{
		audioSource.pitch = sfx.m_Pitch;
		audioSource.volume = volume;
		audioSource.clip = sfx.m_AudioClip;
		audioSource.loop = sfx.m_Loop;
		audioSource.minDistance = sfx.m_MinMaxDistance.x;
		audioSource.maxDistance = sfx.m_MinMaxDistance.y;
		audioSource.spatialBlend = sfx.m_SpatialBlend;
		audioSource.spread = sfx.m_Spread;
		audioSource.rolloffMode = sfx.m_RolloffMode;
		if (sfx.m_RolloffMode == AudioRolloffMode.Custom)
		{
			audioSource.SetCustomCurve(AudioSourceCurveType.CustomRolloff, sfx.m_RolloffCurve);
		}
		audioSource.outputAudioMixerGroup = GetAudioMixerGroup(sfx.m_MixerGroup);
		audioSource.dopplerLevel = 0f;
		audioSource.timeSamples = 0;
		if (sfx.m_RandomStartTime)
		{
			Unity.Mathematics.Random random = new Unity.Mathematics.Random((uint)DateTime.Now.Ticks);
			audioSource.timeSamples = random.NextInt(sfx.m_AudioClip.samples);
		}
		audioSource.ignoreListenerPause = false;
		audioSource.priority = sfx.m_Priority;
	}
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public void SetDefaults(Context context)
	{
		m_LastSaveRadioChannel = string.Empty;
		m_LastSaveRadioSkipAds = false;
	}
```

- `public SetGlobalAudioSettings() : System.Void`  

```csharp
public void SetGlobalAudioSettings()
	{
		ClearCameraAmbientSources();
		if (m_AmbientSettingsQuery.IsEmptyIgnoreFilter)
		{
			return;
		}
		Entity singletonEntity = m_AmbientSettingsQuery.GetSingletonEntity();
		DynamicBuffer<AmbientAudioEffect> buffer = base.World.EntityManager.GetBuffer<AmbientAudioEffect>(singletonEntity, isReadOnly: true);
		AmbientAudioSettingsData componentData = base.World.EntityManager.GetComponentData<AmbientAudioSettingsData>(singletonEntity);
		float num = (componentData.m_MaxHeight - componentData.m_MinHeight) / (float)(buffer.Length + 1);
		float num2 = componentData.m_MinHeight + num * (float)buffer.Length - num * (1f - componentData.m_OverlapRatio);
		for (int i = 0; i < buffer.Length; i++)
		{
			EffectPrefab prefab = m_PrefabSystem.GetPrefab<EffectPrefab>(buffer[i].m_Effect);
			if (prefab != null)
			{
				SFX component = prefab.GetComponent<SFX>();
				AudioSource audioSource = AudioSourcePool.Get();
				SetAudioSourceData(audioSource, component, component.m_Volume);
				UpdateAudioSource(audioSource, component, new Game.Objects.Transform
				{
					m_Position = float3.zero,
					m_Rotation = quaternion.identity
				}, 1f, disableDoppler: true);
				List<CameraAmbientAudioInfo> list = m_CameraAmbientSources;
				CameraAmbientAudioInfo cameraAmbientAudioInfo = new CameraAmbientAudioInfo();
				cameraAmbientAudioInfo.id = i;
				cameraAmbientAudioInfo.height = num2;
				cameraAmbientAudioInfo.source = audioSource;
				cameraAmbientAudioInfo.transform = audioSource.transform;
				list.Add(cameraAmbientAudioInfo);
				audioSource.maxDistance = num * componentData.m_OverlapRatio;
				audioSource.minDistance = audioSource.maxDistance * componentData.m_MinDistanceRatio;
				AudioSourcePool.Play(audioSource);
				num2 -= num;
			}
		}
	}
```

- `private SetGlobalAudioSourcePosition(Game.Audio.AudioManager+CameraAmbientAudioInfo info, Unity.Mathematics.float3 position) : System.Void`  

```csharp
private void SetGlobalAudioSourcePosition(CameraAmbientAudioInfo info, float3 position)
	{
		float3 @float = position;
		if (info.id == 0)
		{
			@float.y = math.max(info.height, position.y);
		}
		else
		{
			@float.y = info.height;
		}
		info.transform.position = @float;
	}
```

- `private SetVolume(System.String volumeProperty, System.Single value) : System.Void`  

```csharp
private void SetVolume(string volumeProperty, float value)
	{
		if (GameManager.instance.gameMode == GameMode.Game && m_GameScreenUISystem.isMenuActive && m_AudioFadeStatus == FadeStatus.None)
		{
			switch (volumeProperty)
			{
			case "WorldVolume":
				return;
			case "AudioGroupsVolume":
				return;
			case "AmbienceVolume":
				return;
			case "ServiceBuildingsVolume":
				return;
			case "RadioVolume":
				return;
			}
		}
		m_Mixer.SetFloat(volumeProperty, Mathf.Log10(Mathf.Min(Mathf.Max(value, 0.0001f), 1f)) * 20f);
	}
```

- `public StopExclusiveUISound(UnityEngine.AudioSource audioSource) : System.Void`  

```csharp
public void StopExclusiveUISound(AudioSource audioSource)
	{
		if (audioSource != null)
		{
			AudioSourcePool.Release(audioSource);
		}
	}
```

- `public StopMenuMusic() : System.Void`  

```csharp
public void StopMenuMusic()
	{
		m_MainMenuMusic?.FadeOut();
	}
```

- `private SyncAudioSources() : System.Void`  

```csharp
private void SyncAudioSources()
	{
		for (int i = 0; i < m_AudioInfos.Count; i++)
		{
			AudioInfo audioInfo = m_AudioInfos[i];
			if (audioInfo.m_AudioSource == null)
			{
				RemoveAudio(audioInfo.m_SourceInfo, i);
			}
			else if (!audioInfo.m_AudioSource.isPlaying && m_CurrentEffects.ContainsKey(audioInfo.m_SourceInfo))
			{
				RemoveAudio(audioInfo.m_SourceInfo, i);
			}
		}
		ComponentLookup<Game.Tools.EditorContainer> componentLookup = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_EditorContainer_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<Moving> componentLookup2 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Objects_Moving_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<Temp> componentLookup3 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Tools_Temp_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<AudioEffectData> componentLookup4 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_AudioEffectData_RO_ComponentLookup, ref base.CheckedStateRef);
		ComponentLookup<VehicleAudioEffectData> componentLookup5 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Prefabs_VehicleAudioEffectData_RO_ComponentLookup, ref base.CheckedStateRef);
		BufferLookup<Effect> bufferLookup = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Prefabs_Effect_RO_BufferLookup, ref base.CheckedStateRef);
		BufferLookup<EnabledEffect> bufferLookup2 = InternalCompilerInterface.GetBufferLookup(ref __TypeHandle.__Game_Effects_EnabledEffect_RO_BufferLookup, ref base.CheckedStateRef);
		ComponentLookup<EffectInstance> componentLookup6 = InternalCompilerInterface.GetComponentLookup(ref __TypeHandle.__Game_Effects_EffectInstance_RO_ComponentLookup, ref base.CheckedStateRef);
		JobHandle dependencies;
		NativeList<EnabledEffectData> enabledData = m_EffectControlSystem.GetEnabledData(readOnly: true, out dependencies);
		dependencies.Complete();
		for (int j = 0; j < m_AudioInfos.Count; j++)
		{
			AudioInfo value = m_AudioInfos[j];
			bool flag;
			Entity entity;
			float num;
			Game.Objects.Transform transform;
			if (base.EntityManager.TryGetComponent<PrefabRef>(value.m_SourceInfo.m_Entity, out var component) && value.m_AudioSource != null)
			{
				num = 0f;
				flag = false;
				transform = default(Game.Objects.Transform);
				entity = default(Entity);
				if (value.m_SourceInfo.m_EffectIndex >= 0)
				{
					DynamicBuffer<EnabledEffect> effects = bufferLookup2[value.m_SourceInfo.m_Entity];
					if (bufferLookup.TryGetBuffer(component.m_Prefab, out var bufferData))
					{
						if (GetEffect(effects, value.m_SourceInfo.m_EffectIndex, out var effect))
						{
							_ = bufferData[value.m_SourceInfo.m_EffectIndex];
							EnabledEffectData enabledEffectData = enabledData[effect.m_EnabledIndex];
							num = enabledEffectData.m_Intensity;
							flag = (enabledEffectData.m_Flags & EnabledEffectFlags.AudioDisabled) != 0;
							transform = new Game.Objects.Transform(enabledEffectData.m_Position, enabledEffectData.m_Rotation);
							entity = value.m_SourceInfo.m_Entity;
							goto IL_0326;
						}
					}
					else if (componentLookup.HasComponent(value.m_SourceInfo.m_Entity) && effects.Length != 0)
					{
						EnabledEffectData enabledEffectData2 = enabledData[effects[0].m_EnabledIndex];
						num = enabledEffectData2.m_Intensity;
						flag = (enabledEffectData2.m_Flags & EnabledEffectFlags.AudioDisabled) != 0;
						transform = new Game.Objects.Transform(enabledEffectData2.m_Position, enabledEffectData2.m_Rotation);
						entity = value.m_SourceInfo.m_Entity;
						goto IL_0326;
					}
				}
				else if (value.m_SourceInfo.m_EffectIndex == -1)
				{
					EffectInstance effectInstance = componentLookup6[value.m_SourceInfo.m_Entity];
					num = effectInstance.m_Intensity;
					transform = new Game.Objects.Transform(effectInstance.m_Position, effectInstance.m_Rotation);
					goto IL_0326;
				}
			}
			value.m_Status = FadeStatus.FadeOut;
			m_AudioInfos[j] = value;
			if (value.m_AudioSource.volume < 0.001f || value.m_MaxVolume < 0.001f || !base.EntityManager.Exists(value.m_SFXEntity))
			{
				RemoveAudio(value.m_SourceInfo, j--);
				continue;
			}
			int audioClipId = componentLookup4[value.m_SFXEntity].m_AudioClipId;
			value.m_AudioSource.transform.position += (Vector3)(value.m_Velocity * m_DeltaTime);
			value.m_AudioSource.volume = GetFadedVolume(value.m_Status, m_Clips[audioClipId].m_FadeTimes, value.m_AudioSource.volume, value.m_MaxVolume);
			continue;
			IL_0326:
			int audioClipId2 = componentLookup4[value.m_SFXEntity].m_AudioClipId;
			if (flag)
			{
				value.m_Status = FadeStatus.FadeOut;
			}
			float3 @float = value.m_AudioSource.transform.position;
			if (!UpdateAudioSource(value.m_AudioSource, m_Clips[audioClipId2], transform, num, entity == followed && entity != Entity.Null, j, value.m_Status, value.m_SourceInfo))
			{
				j--;
				continue;
			}
			value.m_MaxVolume = m_Clips[audioClipId2].m_Volume * num;
			value.m_Velocity = ((float3)value.m_AudioSource.transform.position - @float) / math.max(1E-06f, m_DeltaTime);
			m_AudioInfos[j] = value;
			if (componentLookup5.HasComponent(value.m_SFXEntity))
			{
				if (componentLookup3.HasComponent(entity))
				{
					entity = componentLookup3[entity].m_Original;
				}
				float velocity = 0f;
				if (componentLookup2.HasComponent(entity))
				{
					velocity = math.length(componentLookup2[entity].m_Velocity);
				}
				UpdateAudioSourceByVelocity(value.m_AudioSource, velocity, componentLookup5[value.m_SFXEntity], value.m_Status);
				float num2 = m_Clips[audioClipId2].m_Doppler * math.saturate(1f - (m_SimulationSystem.smoothSpeed - 1f) * 0.3f);
				if (value.m_AudioSource.dopplerLevel != num2)
				{
					value.m_AudioSource.dopplerLevel = num2;
				}
			}
		}
	}
```

- `public UpdateAudioListener(UnityEngine.Vector3 position, UnityEngine.Quaternion rotation) : System.Void`  

```csharp
public void UpdateAudioListener(Vector3 position, Quaternion rotation)
	{
		if (m_AudioListener != null && GameManager.instance.gameMode == GameMode.Game && !GameManager.instance.isGameLoading)
		{
			m_AudioListener.enabled = false;
			m_AudioListener.transform.position = position;
			m_AudioListener.transform.rotation = rotation;
			m_AudioListener.enabled = true;
			if (m_CameraAmbientSources.Count > 0)
			{
				UpdateGlobalAudioSources(m_AudioListener.transform);
			}
		}
	}
```

- `private UpdateAudioSource(UnityEngine.AudioSource audioSource, Game.Prefabs.Effects.SFX sfx, Game.Objects.Transform transform, System.Single intensity, System.Boolean disableDoppler, System.Int32 i = -1, Game.Audio.AudioManager+FadeStatus status = None, Game.Effects.SourceInfo sourceInfo = null) : System.Boolean`  

```csharp
private System.Boolean UpdateAudioSource(UnityEngine.AudioSource audioSource, Game.Prefabs.Effects.SFX sfx, Game.Objects.Transform transform, System.Single intensity, System.Boolean disableDoppler, System.Int32 i, Game.Audio.AudioManager+FadeStatus status, Game.Effects.SourceInfo sourceInfo);
```

- `private UpdateAudioSourceByVelocity(UnityEngine.AudioSource audioSource, System.Single velocity, Game.Prefabs.VehicleAudioEffectData vehicleData, Game.Audio.AudioManager+FadeStatus status) : System.Void`  

```csharp
private void UpdateAudioSourceByVelocity(AudioSource audioSource, float velocity, VehicleAudioEffectData vehicleData, FadeStatus status)
	{
		velocity = math.saturate((velocity - vehicleData.m_SpeedLimits.x) / (vehicleData.m_SpeedLimits.y - vehicleData.m_SpeedLimits.x));
		audioSource.pitch = math.lerp(vehicleData.m_SpeedPitches.x, vehicleData.m_SpeedPitches.y, velocity);
		float num = math.lerp(vehicleData.m_SpeedVolumes.x, vehicleData.m_SpeedVolumes.y, velocity);
		if (status == FadeStatus.FadeOut)
		{
			audioSource.volume = math.min(audioSource.volume, num);
		}
		else
		{
			audioSource.volume = num;
		}
	}
```

- `private UpdateGameAudioSetting() : System.Void`  

```csharp
private void UpdateGameAudioSetting()
	{
		if (m_SimulationSystem.selectedSpeed == 0f && !m_IsGamePausedLastUpdate)
		{
			m_AudioFadeStatus = FadeStatus.FadeOut;
		}
		else if (m_SimulationSystem.selectedSpeed != 0f && m_IsGamePausedLastUpdate)
		{
			m_AudioFadeStatus = FadeStatus.FadeIn;
			disastersVolume = 0.0001f;
			worldVolume = 0.0001f;
		}
		if (!m_IsMenuActivatedLastUpdate && m_GameScreenUISystem.isMenuActive)
		{
			m_AudioFadeStatus = FadeStatus.FadeOut;
			m_ShouldUnpauseRadioAfterGameUnpaused = m_Radio.hasEmergency || !m_Radio.paused;
		}
		else if (m_IsMenuActivatedLastUpdate && !m_GameScreenUISystem.isMenuActive)
		{
			m_AudioFadeStatus = FadeStatus.FadeIn;
			ambienceVolume = 0.0001f;
			serviceBuildingsVolume = 0.0001f;
			audioGroupsVolume = 0.0001f;
			radioVolume = 0.0001f;
			m_Radio.ForceRadioPause(!m_ShouldUnpauseRadioAfterGameUnpaused);
		}
		if (m_AudioFadeStatus == FadeStatus.FadeOut)
		{
			m_AudioFadeStatus = FadeStatus.None;
			if (disastersVolume > 0.0001f)
			{
				m_Mixer.SetFloat("DisastersVolume", Mathf.Log10(Mathf.Min(Mathf.Max(disastersVolume - UnityEngine.Time.deltaTime / 1f, 0.0001f), 1f)) * 20f);
				m_AudioFadeStatus = FadeStatus.FadeOut;
			}
			if (worldVolume > 0.0001f)
			{
				m_Mixer.SetFloat("WorldVolume", Mathf.Log10(Mathf.Min(Mathf.Max(worldVolume - UnityEngine.Time.deltaTime / 1f, 0.0001f), 1f)) * 20f);
				m_AudioFadeStatus = FadeStatus.FadeOut;
			}
			if (m_GameScreenUISystem.isMenuActive)
			{
				if (serviceBuildingsVolume > 0.0001f)
				{
					m_Mixer.SetFloat("ServiceBuildingsVolume", Mathf.Log10(Mathf.Min(Mathf.Max(serviceBuildingsVolume - UnityEngine.Time.deltaTime / 1f, 0.0001f), 1f)) * 20f);
					m_AudioFadeStatus = FadeStatus.FadeOut;
				}
				if (ambienceVolume > 0.0001f)
				{
					m_Mixer.SetFloat("AmbienceVolume", Mathf.Log10(Mathf.Min(Mathf.Max(ambienceVolume - UnityEngine.Time.deltaTime / 1f, 0.0001f), 1f)) * 20f);
					m_AudioFadeStatus = FadeStatus.FadeOut;
				}
				if (audioGroupsVolume > 0.0001f)
				{
					m_Mixer.SetFloat("AudioGroupsVolume", Mathf.Log10(Mathf.Min(Mathf.Max(audioGroupsVolume - UnityEngine.Time.deltaTime / 1f, 0.0001f), 1f)) * 20f);
					m_AudioFadeStatus = FadeStatus.FadeOut;
				}
				if (radioVolume > 0.0001f)
				{
					m_Mixer.SetFloat("RadioVolume", Mathf.Log10(Mathf.Min(Mathf.Max(radioVolume - UnityEngine.Time.deltaTime / 1f, 0.0001f), 1f)) * 20f);
					m_AudioFadeStatus = FadeStatus.FadeOut;
				}
				else
				{
					m_Radio.ForceRadioPause(pause: true);
				}
			}
		}
		else if (m_AudioFadeStatus == FadeStatus.FadeIn)
		{
			m_AudioFadeStatus = FadeStatus.None;
			if (m_SimulationSystem.selectedSpeed != 0f)
			{
				if (disastersVolume < SharedSettings.instance.audio.disastersVolume)
				{
					m_Mixer.SetFloat("DisastersVolume", Mathf.Log10(Mathf.Min(Mathf.Max(disastersVolume + UnityEngine.Time.deltaTime / 1f, 0.0001f), 1f)) * 20f);
					m_AudioFadeStatus = FadeStatus.FadeIn;
				}
				if (worldVolume < SharedSettings.instance.audio.worldVolume)
				{
					m_Mixer.SetFloat("WorldVolume", Mathf.Log10(Mathf.Min(Mathf.Max(worldVolume + UnityEngine.Time.deltaTime / 1f, 0.0001f), 1f)) * 20f);
					m_AudioFadeStatus = FadeStatus.FadeIn;
				}
			}
			if (!m_GameScreenUISystem.isMenuActive)
			{
				if (serviceBuildingsVolume < SharedSettings.instance.audio.serviceBuildingsVolume)
				{
					m_Mixer.SetFloat("ServiceBuildingsVolume", Mathf.Log10(Mathf.Min(Mathf.Max(serviceBuildingsVolume + UnityEngine.Time.deltaTime / 1f, 0.0001f), 1f)) * 20f);
					m_AudioFadeStatus = FadeStatus.FadeIn;
				}
				if (ambienceVolume < SharedSettings.instance.audio.ambienceVolume)
				{
					m_Mixer.SetFloat("AmbienceVolume", Mathf.Log10(Mathf.Min(Mathf.Max(ambienceVolume + UnityEngine.Time.deltaTime / 1f, 0.0001f), 1f)) * 20f);
					m_AudioFadeStatus = FadeStatus.FadeIn;
				}
				if (audioGroupsVolume < SharedSettings.instance.audio.audioGroupsVolume)
				{
					m_Mixer.SetFloat("AudioGroupsVolume", Mathf.Log10(Mathf.Min(Mathf.Max(audioGroupsVolume + UnityEngine.Time.deltaTime / 1f, 0.0001f), 1f)) * 20f);
					m_AudioFadeStatus = FadeStatus.FadeIn;
				}
				if (radioVolume < SharedSettings.instance.audio.radioVolume)
				{
					m_Mixer.SetFloat("RadioVolume", Mathf.Log10(Mathf.Min(Mathf.Max(radioVolume + UnityEngine.Time.deltaTime / 1f, 0.0001f), 1f)) * 20f);
					m_AudioFadeStatus = FadeStatus.FadeIn;
				}
			}
		}
		m_IsGamePausedLastUpdate = m_SimulationSystem.selectedSpeed == 0f;
		m_IsMenuActivatedLastUpdate = m_GameScreenUISystem.isMenuActive;
	}
```

- `public UpdateGlobalAudioSources(UnityEngine.Transform cameraTransform) : System.Void`  

```csharp
public void UpdateGlobalAudioSources(UnityEngine.Transform cameraTransform)
	{
		if (m_CameraAmbientSources.Count > 0 && m_CameraAmbientSources[0].source == null)
		{
			SetGlobalAudioSettings();
		}
		for (int i = 0; i < m_CameraAmbientSources.Count; i++)
		{
			SetGlobalAudioSourcePosition(m_CameraAmbientSources[i], cameraTransform.position);
		}
	}
```

- `private UpdateMenuMusic() : System.Void`  

```csharp
private void UpdateMenuMusic()
	{
		m_MainMenuMusic?.Update(base.CheckedStateRef.WorldUnmanaged.Time.DeltaTime);
	}
```

- `private UpdateTempAudioSources() : System.Void`  

```csharp
private void UpdateTempAudioSources()
	{
		foreach (AudioSource item in m_TempAudioSources)
		{
			if (item != null && !item.isPlaying)
			{
				AudioSourcePool.Release(item);
			}
		}
		m_TempAudioSources.RemoveAll((AudioSource audiosouce) => audiosouce == null || audiosouce.gameObject == null || !audiosouce.gameObject.activeSelf);
	}
```


## Nested types

- `Game.Audio.AudioManager+AudioSourcePool`  
- `Game.Audio.AudioManager+FadeStatus`  
- `Game.Audio.AudioManager+AudioInfo`  
- `Game.Audio.AudioManager+CameraAmbientAudioInfo`  
- `Game.Audio.AudioManager+TypeHandle`  
- `Game.Audio.AudioManager+<>c`  
- `Game.Audio.AudioManager+<>c__DisplayClass111_0`  
- `Game.Audio.AudioManager+<>c__DisplayClass125_0`  
- `Game.Audio.AudioManager+<PlayMenuMusic>d__125`  
- `Game.Audio.AudioManager+<ResetAudioOnMainThread>d__111`  

