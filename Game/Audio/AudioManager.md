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
public AudioManager();
```


## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  

```csharp
private System.Void __AssignQueries(Unity.Entities.SystemState& state);
```

- `public AddSourceUpdateWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  

```csharp
public System.Void AddSourceUpdateWriter(Unity.Jobs.JobHandle jobHandle);
```

- `private ClearCameraAmbientSources() : System.Void`  

```csharp
private System.Void ClearCameraAmbientSources();
```

- `public Deserialize<TReader>(TReader reader) : System.Void`  

```csharp
public System.Void Deserialize<TReader>(TReader reader);
```

- `private Fadeout(Game.Effects.SourceInfo sourceInfo, System.Int32 index) : System.Void`  

```csharp
private System.Void Fadeout(Game.Effects.SourceInfo sourceInfo, System.Int32 index);
```

- `private GetAudioMixerGroup(Game.Effects.MixerGroup group) : UnityEngine.Audio.AudioMixerGroup`  

```csharp
private UnityEngine.Audio.AudioMixerGroup GetAudioMixerGroup(Game.Effects.MixerGroup group);
```

- `public static GetClosestSourcePosition(Unity.Mathematics.float3 targetPosition, Game.Objects.Transform sourceTransform, Unity.Mathematics.float3 sourceOffset, Unity.Mathematics.float3 sourceSize) : Unity.Mathematics.float3`  

```csharp
public static Unity.Mathematics.float3 GetClosestSourcePosition(Unity.Mathematics.float3 targetPosition, Game.Objects.Transform sourceTransform, Unity.Mathematics.float3 sourceOffset, Unity.Mathematics.float3 sourceSize);
```

- `private GetEffect(Unity.Entities.DynamicBuffer<Game.Effects.EnabledEffect> effects, System.Int32 effectIndex, Game.Effects.EnabledEffect& effect) : System.Boolean`  

```csharp
private System.Boolean GetEffect(Unity.Entities.DynamicBuffer<Game.Effects.EnabledEffect> effects, System.Int32 effectIndex, Game.Effects.EnabledEffect& effect);
```

- `private GetFadedVolume(Game.Audio.AudioManager+FadeStatus status, Unity.Mathematics.float2 sfxFades, System.Single currentVolume, System.Single targetVolume) : System.Single`  

```csharp
private System.Single GetFadedVolume(Game.Audio.AudioManager+FadeStatus status, Unity.Mathematics.float2 sfxFades, System.Single currentVolume, System.Single targetVolume);
```

- `public GetRandomizeAudio(Unity.Entities.Entity sfxEntity, Game.Prefabs.Effects.SFX& sfx) : System.Boolean`  

```csharp
public System.Boolean GetRandomizeAudio(Unity.Entities.Entity sfxEntity, Game.Prefabs.Effects.SFX& sfx);
```

- `public GetSourceUpdateData(Unity.Jobs.JobHandle& deps) : Game.Effects.SourceUpdateData`  

```csharp
public Game.Effects.SourceUpdateData GetSourceUpdateData(Unity.Jobs.JobHandle& deps);
```

- `private GetVolume(System.String volumeProperty) : System.Single`  

```csharp
private System.Single GetVolume(System.String volumeProperty);
```

- `public MoveAudioListenerForDoppler(Unity.Mathematics.float3 m_FollowOffset) : System.Void`  

```csharp
public System.Void MoveAudioListenerForDoppler(Unity.Mathematics.float3 m_FollowOffset);
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

- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  

```csharp
protected virtual System.Void OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext);
```

- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  

```csharp
protected virtual System.Void OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode);
```

- `protected virtual OnUpdate() : System.Void`  

```csharp
protected virtual System.Void OnUpdate();
```

- `public PlayExclusiveUISound(Unity.Entities.Entity clipEntity) : UnityEngine.AudioSource`  

```csharp
public UnityEngine.AudioSource PlayExclusiveUISound(Unity.Entities.Entity clipEntity);
```

- `public PlayLightningSFX(Unity.Mathematics.float3 targetPos) : System.Void`  

```csharp
public System.Void PlayLightningSFX(Unity.Mathematics.float3 targetPos);
```

- `public PlayMenuMusic(System.String tag) : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task PlayMenuMusic(System.String tag);
```

- `public PlayUISound(Unity.Entities.Entity clipEntity, System.Single volume = 1) : System.Void`  

```csharp
public System.Void PlayUISound(Unity.Entities.Entity clipEntity, System.Single volume);
```

- `public PlayUISound(UnityEngine.AudioClip clip, System.Single volume = 1) : System.Void`  

```csharp
public System.Void PlayUISound(UnityEngine.AudioClip clip, System.Single volume);
```

- `public PlayUISoundIfNotPlaying(Unity.Entities.Entity clipEntity, System.Single volume = 1) : System.Boolean`  

```csharp
public System.Boolean PlayUISoundIfNotPlaying(Unity.Entities.Entity clipEntity, System.Single volume);
```

- `public PlayUISoundIfNotPlaying(UnityEngine.AudioClip clipEntity, System.Single volume = 1) : System.Boolean`  

```csharp
public System.Boolean PlayUISoundIfNotPlaying(UnityEngine.AudioClip clipEntity, System.Single volume);
```

- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreDeserialize(Colossal.Serialization.Entities.Context context);
```

- `public PreSerialize(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void PreSerialize(Colossal.Serialization.Entities.Context context);
```

- `public RegisterSFX(Game.Prefabs.Effects.SFX sfx) : System.Int32`  

```csharp
public System.Int32 RegisterSFX(Game.Prefabs.Effects.SFX sfx);
```

- `private RemoveAudio(Game.Effects.SourceInfo sourceInfo, System.Int32 index) : System.Void`  

```csharp
private System.Void RemoveAudio(Game.Effects.SourceInfo sourceInfo, System.Int32 index);
```

- `public Reset() : System.Void`  

```csharp
public System.Void Reset();
```

- `public ResetAudioOnMainThread() : System.Threading.Tasks.Task`  

```csharp
public System.Threading.Tasks.Task ResetAudioOnMainThread();
```

- `public Serialize<TWriter>(TWriter writer) : System.Void`  

```csharp
public System.Void Serialize<TWriter>(TWriter writer);
```

- `private SetAudioSourceData(UnityEngine.AudioSource audioSource, Game.Prefabs.Effects.SFX sfx, System.Single volume) : System.Void`  

```csharp
private System.Void SetAudioSourceData(UnityEngine.AudioSource audioSource, Game.Prefabs.Effects.SFX sfx, System.Single volume);
```

- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  

```csharp
public System.Void SetDefaults(Colossal.Serialization.Entities.Context context);
```

- `public SetGlobalAudioSettings() : System.Void`  

```csharp
public System.Void SetGlobalAudioSettings();
```

- `private SetGlobalAudioSourcePosition(Game.Audio.AudioManager+CameraAmbientAudioInfo info, Unity.Mathematics.float3 position) : System.Void`  

```csharp
private System.Void SetGlobalAudioSourcePosition(Game.Audio.AudioManager+CameraAmbientAudioInfo info, Unity.Mathematics.float3 position);
```

- `private SetVolume(System.String volumeProperty, System.Single value) : System.Void`  

```csharp
private System.Void SetVolume(System.String volumeProperty, System.Single value);
```

- `public StopExclusiveUISound(UnityEngine.AudioSource audioSource) : System.Void`  

```csharp
public System.Void StopExclusiveUISound(UnityEngine.AudioSource audioSource);
```

- `public StopMenuMusic() : System.Void`  

```csharp
public System.Void StopMenuMusic();
```

- `private SyncAudioSources() : System.Void`  

```csharp
private System.Void SyncAudioSources();
```

- `public UpdateAudioListener(UnityEngine.Vector3 position, UnityEngine.Quaternion rotation) : System.Void`  

```csharp
public System.Void UpdateAudioListener(UnityEngine.Vector3 position, UnityEngine.Quaternion rotation);
```

- `private UpdateAudioSource(UnityEngine.AudioSource audioSource, Game.Prefabs.Effects.SFX sfx, Game.Objects.Transform transform, System.Single intensity, System.Boolean disableDoppler, System.Int32 i = -1, Game.Audio.AudioManager+FadeStatus status = None, Game.Effects.SourceInfo sourceInfo = null) : System.Boolean`  

```csharp
private System.Boolean UpdateAudioSource(UnityEngine.AudioSource audioSource, Game.Prefabs.Effects.SFX sfx, Game.Objects.Transform transform, System.Single intensity, System.Boolean disableDoppler, System.Int32 i, Game.Audio.AudioManager+FadeStatus status, Game.Effects.SourceInfo sourceInfo);
```

- `private UpdateAudioSourceByVelocity(UnityEngine.AudioSource audioSource, System.Single velocity, Game.Prefabs.VehicleAudioEffectData vehicleData, Game.Audio.AudioManager+FadeStatus status) : System.Void`  

```csharp
private System.Void UpdateAudioSourceByVelocity(UnityEngine.AudioSource audioSource, System.Single velocity, Game.Prefabs.VehicleAudioEffectData vehicleData, Game.Audio.AudioManager+FadeStatus status);
```

- `private UpdateGameAudioSetting() : System.Void`  

```csharp
private System.Void UpdateGameAudioSetting();
```

- `public UpdateGlobalAudioSources(UnityEngine.Transform cameraTransform) : System.Void`  

```csharp
public System.Void UpdateGlobalAudioSources(UnityEngine.Transform cameraTransform);
```

- `private UpdateMenuMusic() : System.Void`  

```csharp
private System.Void UpdateMenuMusic();
```

- `private UpdateTempAudioSources() : System.Void`  

```csharp
private System.Void UpdateTempAudioSources();
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

