# Game.Audio.AudioManager

**Assembly:** `Game`  
**Namespace:** `Game.Audio`  

**Type:** class public  

**Base:** `Game.GameSystemBase`  
**Implements:** `Colossal.Serialization.Entities.IDefaultSerializable`, `Colossal.Serialization.Entities.ISerializable`, `Game.Serialization.IPreDeserialize`, `Game.Serialization.IPreSerialize`  

**Attributes:** `CompilerGenerated`  

## Fields

- `private System.Collections.Generic.List<Game.Audio.AudioManager+AudioInfo> m_AudioInfos`  
- `private System.Threading.SynchronizationContext m_MainThreadContext`  
- `private UnityEngine.Audio.AudioMixer m_Mixer`  
- `private UnityEngine.Audio.AudioMixerGroup m_AmbientGroup`  
- `private UnityEngine.Audio.AudioMixerGroup m_InGameGroup`  
- `private UnityEngine.Audio.AudioMixerGroup m_RadioGroup`  
- `private UnityEngine.Audio.AudioMixerGroup m_UIGroup`  
- `private UnityEngine.Audio.AudioMixerGroup m_MenuGroup`  
- `private UnityEngine.Audio.AudioMixerGroup m_WorldGroup`  
- `private UnityEngine.Audio.AudioMixerGroup m_ServiceBuildingGroup`  
- `private UnityEngine.Audio.AudioMixerGroup m_AudioGroupGroup`  
- `private UnityEngine.Audio.AudioMixerGroup m_DisasterGroup`  
- `private Game.Audio.AudioLoop m_MainMenuMusic`  
- `private UnityEngine.AudioSource m_UIAudioSource`  
- `private UnityEngine.AudioSource m_UIHtmlAudioSource`  
- `private UnityEngine.AudioListener m_AudioListener`  
- `private Unity.Collections.NativeQueue<Game.Effects.SourceUpdateInfo> m_SourceUpdateQueue`  
- `private Game.Effects.SourceUpdateData m_SourceUpdateData`  
- `private Unity.Jobs.JobHandle m_SourceUpdateWriter`  
- `private Game.Simulation.SimulationSystem m_SimulationSystem`  
- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.UI.InGame.GameScreenUISystem m_GameScreenUISystem`  
- `private Game.Effects.EffectControlSystem m_EffectControlSystem`  
- `private Game.Common.RandomSeed m_RandomSeed`  
- `private System.Single m_FadeOutMenu`  
- `private System.Single m_DeltaTime`  
- `private System.Boolean m_IsGamePausedLastUpdate`  
- `private System.Boolean m_IsMenuActivatedLastUpdate`  
- `private System.Boolean m_ShouldUnpauseRadioAfterGameUnpaused`  
- `private System.String m_LastSaveRadioChannel`  
- `private System.Boolean m_LastSaveRadioSkipAds`  
- `private Game.Audio.AudioManager+FadeStatus m_AudioFadeStatus`  
- `private Game.Simulation.TimeSystem m_TimeSystem`  
- `private System.Collections.Generic.List<Game.Prefabs.Effects.SFX> m_Clips`  
- `private Unity.Collections.NativeParallelHashMap<Game.Effects.SourceInfo, System.Int32> m_CurrentEffects`  
- `private Unity.Entities.EntityQuery m_AmbientSettingsQuery`  
- `private Unity.Entities.EntityQuery m_SoundQuery`  
- `private Unity.Entities.EntityQuery m_WeatherAudioEntitiyQuery`  
- `private System.Collections.Generic.List<Game.Audio.AudioManager+CameraAmbientAudioInfo> m_CameraAmbientSources`  
- `private System.Collections.Generic.List<UnityEngine.AudioSource> m_TempAudioSources`  
- `private Game.Audio.Radio.Radio m_Radio`  
- `private Unity.Entities.Entity <followed>k__BackingField`  
- `private System.Int32 m_PlayCount`  
- `private Game.Audio.AudioManager+TypeHandle __TypeHandle`  
- `private static readonly Colossal.Logging.ILog log`  
- `private static Game.Audio.AudioManager <instance>k__BackingField`  
- `private static const System.Single kDopplerLevelReduceFactor`  
- `private static const System.String kMasterVolumeProperty`  
- `private static const System.String kRadioVolumeProperty`  
- `private static const System.String kUIVolumeProperty`  
- `private static const System.String kMenuVolumeProperty`  
- `private static const System.String kInGameVolumeProperty`  
- `private static const System.String kAmbienceVolumeProperty`  
- `private static const System.String kDisastersVolumeProperty`  
- `private static const System.String kWorldVolumeProperty`  
- `private static const System.String kAudioGroupsVolumeProperty`  
- `private static const System.String kServiceBuildingsVolumeProperty`  

## Properties

- `public static Game.Audio.AudioManager instance { get; private set }`  
- `public UnityEngine.AudioSource UIHtmlAudioSource { get }`  
- `public Game.Audio.Radio.Radio radio { get }`  
- `private Unity.Entities.Entity followed { private get; set }`  
- `public System.Single masterVolume { get; set }`  
- `public System.Single radioVolume { get; set }`  
- `public System.Single uiVolume { get; set }`  
- `public System.Single menuVolume { get; set }`  
- `public System.Single ingameVolume { get; set }`  
- `public System.Single ambienceVolume { get; set }`  
- `public System.Single disastersVolume { get; set }`  
- `public System.Single worldVolume { get; set }`  
- `public System.Single audioGroupsVolume { get; set }`  
- `public System.Single serviceBuildingsVolume { get; set }`  

## Constructors

- `public AudioManager()`  

## Methods

- `private __AssignQueries(Unity.Entities.SystemState& state) : System.Void`  
- `public AddSourceUpdateWriter(Unity.Jobs.JobHandle jobHandle) : System.Void`  
- `private ClearCameraAmbientSources() : System.Void`  
- `public Deserialize<TReader>(TReader reader) : System.Void`  
- `private Fadeout(Game.Effects.SourceInfo sourceInfo, System.Int32 index) : System.Void`  
- `private GetAudioMixerGroup(Game.Effects.MixerGroup group) : UnityEngine.Audio.AudioMixerGroup`  
- `public static GetClosestSourcePosition(Unity.Mathematics.float3 targetPosition, Game.Objects.Transform sourceTransform, Unity.Mathematics.float3 sourceOffset, Unity.Mathematics.float3 sourceSize) : Unity.Mathematics.float3`  
- `private GetEffect(Unity.Entities.DynamicBuffer<Game.Effects.EnabledEffect> effects, System.Int32 effectIndex, Game.Effects.EnabledEffect& effect) : System.Boolean`  
- `private GetFadedVolume(Game.Audio.AudioManager+FadeStatus status, Unity.Mathematics.float2 sfxFades, System.Single currentVolume, System.Single targetVolume) : System.Single`  
- `public GetRandomizeAudio(Unity.Entities.Entity sfxEntity, Game.Prefabs.Effects.SFX& sfx) : System.Boolean`  
- `public GetSourceUpdateData(Unity.Jobs.JobHandle& deps) : Game.Effects.SourceUpdateData`  
- `private GetVolume(System.String volumeProperty) : System.Single`  
- `public MoveAudioListenerForDoppler(Unity.Mathematics.float3 m_FollowOffset) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnCreateForCompiler() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `protected virtual OnGameLoaded(Colossal.Serialization.Entities.Context serializationContext) : System.Void`  
- `protected virtual OnGameLoadingComplete(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnGamePreload(Colossal.Serialization.Entities.Purpose purpose, Game.GameMode mode) : System.Void`  
- `protected virtual OnUpdate() : System.Void`  
- `public PlayExclusiveUISound(Unity.Entities.Entity clipEntity) : UnityEngine.AudioSource`  
- `public PlayLightningSFX(Unity.Mathematics.float3 targetPos) : System.Void`  
- `public PlayMenuMusic(System.String tag) : System.Threading.Tasks.Task`  
- `public PlayUISound(Unity.Entities.Entity clipEntity, System.Single volume = 1) : System.Void`  
- `public PlayUISound(UnityEngine.AudioClip clip, System.Single volume = 1) : System.Void`  
- `public PlayUISoundIfNotPlaying(Unity.Entities.Entity clipEntity, System.Single volume = 1) : System.Boolean`  
- `public PlayUISoundIfNotPlaying(UnityEngine.AudioClip clipEntity, System.Single volume = 1) : System.Boolean`  
- `public PreDeserialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public PreSerialize(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public RegisterSFX(Game.Prefabs.Effects.SFX sfx) : System.Int32`  
- `private RemoveAudio(Game.Effects.SourceInfo sourceInfo, System.Int32 index) : System.Void`  
- `public Reset() : System.Void`  
- `public ResetAudioOnMainThread() : System.Threading.Tasks.Task`  
- `public Serialize<TWriter>(TWriter writer) : System.Void`  
- `private SetAudioSourceData(UnityEngine.AudioSource audioSource, Game.Prefabs.Effects.SFX sfx, System.Single volume) : System.Void`  
- `public SetDefaults(Colossal.Serialization.Entities.Context context) : System.Void`  
- `public SetGlobalAudioSettings() : System.Void`  
- `private SetGlobalAudioSourcePosition(Game.Audio.AudioManager+CameraAmbientAudioInfo info, Unity.Mathematics.float3 position) : System.Void`  
- `private SetVolume(System.String volumeProperty, System.Single value) : System.Void`  
- `public StopExclusiveUISound(UnityEngine.AudioSource audioSource) : System.Void`  
- `public StopMenuMusic() : System.Void`  
- `private SyncAudioSources() : System.Void`  
- `public UpdateAudioListener(UnityEngine.Vector3 position, UnityEngine.Quaternion rotation) : System.Void`  
- `private UpdateAudioSource(UnityEngine.AudioSource audioSource, Game.Prefabs.Effects.SFX sfx, Game.Objects.Transform transform, System.Single intensity, System.Boolean disableDoppler, System.Int32 i = -1, Game.Audio.AudioManager+FadeStatus status = None, Game.Effects.SourceInfo sourceInfo = null) : System.Boolean`  
- `private UpdateAudioSourceByVelocity(UnityEngine.AudioSource audioSource, System.Single velocity, Game.Prefabs.VehicleAudioEffectData vehicleData, Game.Audio.AudioManager+FadeStatus status) : System.Void`  
- `private UpdateGameAudioSetting() : System.Void`  
- `public UpdateGlobalAudioSources(UnityEngine.Transform cameraTransform) : System.Void`  
- `private UpdateMenuMusic() : System.Void`  
- `private UpdateTempAudioSources() : System.Void`  

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

