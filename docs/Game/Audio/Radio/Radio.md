# Game.Audio.Radio.Radio

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `public Game.Audio.Radio.Radio+OnRadioEvent Reloaded`  
- `public Game.Audio.Radio.Radio+OnRadioEvent SettingsChanged`  
- `public Game.Audio.Radio.Radio+OnRadioEvent ProgramChanged`  
- `public Game.Audio.Radio.Radio+OnClipChanged ClipChanged`  
- `private System.Collections.Generic.Dictionary<System.String, Game.Audio.Radio.Radio+RadioNetwork> m_Networks`  
- `private System.Collections.Generic.Dictionary<System.String, Game.Audio.Radio.Radio+RuntimeRadioChannel> m_RadioChannels`  
- `private Game.Audio.Radio.Radio+RuntimeRadioChannel m_CurrentChannel`  
- `private System.Boolean m_Paused`  
- `private System.Boolean <skipAds>k__BackingField`  
- `private System.Boolean m_Muted`  
- `private Game.Audio.Radio.Radio+ClipInfo <currentClip>k__BackingField`  
- `private System.Int32 m_ReplayIndex`  
- `private System.Collections.Generic.List<Game.Audio.Radio.Radio+ClipInfo> m_PlaylistHistory`  
- `private System.Collections.Generic.List<Game.Audio.Radio.Radio+ClipInfo> m_Queue`  
- `private Game.Audio.Radio.Radio+RadioPlayer m_RadioPlayer`  
- `private System.Boolean m_IsEnabled`  
- `private System.String m_LastSaveRadioChannel`  
- `private System.Boolean m_LastSaveRadioAdsState`  
- `private System.Boolean m_IsActive`  
- `private Game.Audio.Radio.Radio+RuntimeRadioChannel[] m_CachedRadioChannelDescriptors`  
- `private System.Collections.Generic.Dictionary<Game.Audio.Radio.Radio+SegmentType, Game.Audio.Radio.Radio+OnDemandClips> m_OnDemandClips`  
- `private static readonly System.String kAlertsTag`  
- `private static readonly System.String kAlertsIntroTag`  
- `private static Colossal.Logging.ILog log`  
- `private static readonly System.Int32 kMaxHistoryLength`  
- `private static const System.Single kSimulationSecondsPerDay`  
- `private static const System.Single kSimtimeToRealtime`  
- `private static const System.Int32 kSecondsPerDay`  
- `private static const System.String kUniqueNameChars`  

## Properties

- `public Game.Audio.Radio.Radio+RuntimeRadioChannel currentChannel { get; set }`  
- `public System.Boolean paused { get; set }`  
- `public System.Boolean skipAds { get; set }`  
- `public System.Boolean muted { get; set }`  
- `public Game.Audio.Radio.Radio+ClipInfo currentClip { get; private set }`  
- `public System.Boolean isEnabled { get }`  
- `public System.Boolean isActive { get; set }`  
- `public Game.Audio.Radio.Radio+RadioNetwork[] networkDescriptors { get }`  
- `public Game.Audio.Radio.Radio+RuntimeRadioChannel[] radioChannelDescriptors { get }`  
- `public System.String currentlyPlayingClipName { get }`  
- `public System.Double currentlyPlayingDuration { get }`  
- `public System.Double currentlyPlayingElapsed { get }`  
- `public System.Double currentlyPlayingRemaining { get }`  
- `public System.Double nextTimeCheck { get }`  
- `public Colossal.IO.AssetDatabase.AudioAsset pendingClip { get }`  
- `public System.Boolean hasEmergency { get }`  
- `public Unity.Entities.Entity emergency { get }`  
- `public Unity.Entities.Entity emergencyTarget { get }`  
- `public UnityEngine.Texture equalizerTexture { get }`  

## Constructors

- `public Radio(UnityEngine.Audio.AudioMixerGroup radioGroup)`  

## Methods

- `private <LoadRadio>b__87_1(Game.Audio.Radio.Radio+RadioNetwork network, Colossal.IO.AssetDatabase.SourceMeta meta) : System.Void`  
- `private <LoadRadio>b__87_2(Game.Audio.Radio.Radio+RadioChannel channel, Colossal.IO.AssetDatabase.SourceMeta meta) : System.Void`  
- `private AlertPlayingOrQueued() : System.Boolean`  
- `private CheckEntitlement(Game.Assets.IContentPrerequisite target) : System.Boolean`  
- `private Clear() : System.Void`  
- `private ClearEmergencyQueue() : System.Void`  
- `private ClearQueue(System.Boolean clearEmergencies = False) : System.Void`  
- `public Disable() : System.Void`  
- `public Enable(UnityEngine.GameObject listener) : System.Void`  
- `private FinishCurrentClip() : System.Void`  
- `public ForceRadioPause(System.Boolean pause) : System.Void`  
- `public GetActiveSource() : System.Int32`  
- `public GetAudioSourceDuration(System.Int32 i) : System.Double`  
- `public GetAudioSourceTimeElapsed(System.Int32 i) : System.Double`  
- `public GetAudioSourceTimeRemaining(System.Int32 i) : System.Double`  
- `private GetCommercialClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  
- `private GetEventClips(Game.Audio.Radio.Radio+RuntimeSegment segment, Colossal.IO.AssetDatabase.AudioAsset+Metatag metatag, System.Boolean newestFirst = False, System.Boolean flush = False) : System.Collections.Generic.List<Colossal.IO.AssetDatabase.AudioAsset>`  
- `private GetNewsClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  
- `private GetPlaylistClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  
- `private GetPSAClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  
- `public GetRadioChannel(System.String name) : Game.Audio.Radio.Radio+RuntimeRadioChannel`  
- `private GetSegmentAudioClip(System.Int32 clipsCap, System.String[] requiredTags, Game.Audio.Radio.Radio+SegmentType segmentType) : Colossal.IO.AssetDatabase.AudioAsset[]`  
- `private GetSortedUIDescriptor<T>(System.Collections.Generic.Dictionary<System.String, T> desc) : T[]`  
- `private GetTalkShowClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  
- `private GetWeatherClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  
- `private InvokeClipcallback(Colossal.IO.AssetDatabase.AudioAsset currentAsset) : System.Void`  
- `private IsEmergencyClipInQueue(Game.Triggers.RadioTag tag) : System.Boolean`  
- `private LoadRadio(System.Boolean enable) : System.Void`  
- `private Log(Game.Audio.Radio.Radio+RadioNetwork network) : System.Void`  
- `private Log(Game.Audio.Radio.Radio+RuntimeRadioChannel channel) : System.Void`  
- `private Log(Colossal.IO.AssetDatabase.AudioAsset clip) : System.Void`  
- `private Log(Game.Audio.Radio.Radio+RuntimeProgram program) : System.Void`  
- `private Log(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  
- `private LogBrandPopularity(Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity> brandPopularity) : System.Void`  
- `private LogMap(System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AudioAsset>> map) : System.Void`  
- `private LogRadio() : System.Void`  
- `private static MakeUniqueName(System.String name, System.Int32 length) : System.String`  
- `private static MakeUniqueRandomName(System.String name, System.Int32 length) : System.String`  
- `public NextSong() : System.Void`  
- `private OnDisabled() : System.Void`  
- `private OnSettingsChanged(Game.Audio.Radio.Radio radio) : System.Void`  
- `public PreviousSong() : System.Void`  
- `private QueueClip(Game.Audio.Radio.Radio+ClipInfo clip, System.Boolean pushToFront = False) : System.Void`  
- `private QueueEmergencyClips() : System.Void`  
- `private QueueEmergencyIntroClip(Unity.Entities.Entity emergency, Unity.Entities.Entity emergencyTarget) : System.Void`  
- `private QueueNextClip() : System.Void`  
- `public Reload(System.Boolean enable = True) : System.Void`  
- `public RestoreRadioSettings(System.String savedChannel, System.Boolean savedAds) : System.Void`  
- `public SetSpectrumSettings(System.Boolean enabled, System.Int32 numSamples, UnityEngine.FFTWindow fftWindow, Game.Audio.Radio.Radio+Spectrum+BandType bandType, System.Single spacing, System.Single padding) : System.Void`  
- `private SetupNextClip() : System.Boolean`  
- `private SetupOrSkipSegment() : System.Boolean`  
- `private static SupportValueTypesForAOT() : System.Void`  
- `public Update(System.Single normalizedTime) : System.Void`  
- `private ValidateQueue() : System.Void`  

## Nested types

- `Game.Audio.Radio.Radio+ClipInfo`  
- `Game.Audio.Radio.Radio+OnRadioEvent`  
- `Game.Audio.Radio.Radio+OnClipChanged`  
- `Game.Audio.Radio.Radio+OnDemandClips`  
- `Game.Audio.Radio.Radio+RadioChannel`  
- `Game.Audio.Radio.Radio+RuntimeRadioChannel`  
- `Game.Audio.Radio.Radio+RadioNetwork`  
- `Game.Audio.Radio.Radio+RadioPlayer`  
- `Game.Audio.Radio.Radio+Program`  
- `Game.Audio.Radio.Radio+RuntimeProgram`  
- `Game.Audio.Radio.Radio+SegmentType`  
- `Game.Audio.Radio.Radio+Segment`  
- `Game.Audio.Radio.Radio+RuntimeSegment`  
- `Game.Audio.Radio.Radio+Spectrum`  
- `Game.Audio.Radio.Radio+<>c`  
- `Game.Audio.Radio.Radio+<>c__DisplayClass107_0`  
- `Game.Audio.Radio.Radio+<>c__DisplayClass108_0`  
- `Game.Audio.Radio.Radio+<>c__DisplayClass111_0`  

