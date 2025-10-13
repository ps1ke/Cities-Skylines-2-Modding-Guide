# Game.Audio.Radio.Radio

**Assembly:** `Game`  
**Namespace:** `Game.Audio.Radio`  

**Type:** class public  

**Base:** `System.Object`  

## Code

```csharp
public class Radio
{
    public Game.Audio.Radio.Radio+OnRadioEvent Reloaded;
    public Game.Audio.Radio.Radio+OnRadioEvent SettingsChanged;
    public Game.Audio.Radio.Radio+OnRadioEvent ProgramChanged;
    public Game.Audio.Radio.Radio+OnClipChanged ClipChanged;
    private System.Collections.Generic.Dictionary<System.String, Game.Audio.Radio.Radio+RadioNetwork> m_Networks;
    private System.Collections.Generic.Dictionary<System.String, Game.Audio.Radio.Radio+RuntimeRadioChannel> m_RadioChannels;
    private Game.Audio.Radio.Radio+RuntimeRadioChannel m_CurrentChannel;
    private System.Boolean m_Paused;
    private System.Boolean <skipAds>k__BackingField;
    private System.Boolean m_Muted;
    private Game.Audio.Radio.Radio+ClipInfo <currentClip>k__BackingField;
    private System.Int32 m_ReplayIndex;
    private System.Collections.Generic.List<Game.Audio.Radio.Radio+ClipInfo> m_PlaylistHistory;
    private System.Collections.Generic.List<Game.Audio.Radio.Radio+ClipInfo> m_Queue;
    private Game.Audio.Radio.Radio+RadioPlayer m_RadioPlayer;
    private System.Boolean m_IsEnabled;
    private System.String m_LastSaveRadioChannel;
    private System.Boolean m_LastSaveRadioAdsState;
    private System.Boolean m_IsActive;
    private Game.Audio.Radio.Radio+RuntimeRadioChannel[] m_CachedRadioChannelDescriptors;
    private System.Collections.Generic.Dictionary<Game.Audio.Radio.Radio+SegmentType, Game.Audio.Radio.Radio+OnDemandClips> m_OnDemandClips;
    private static readonly System.String kAlertsTag;
    private static readonly System.String kAlertsIntroTag;
    private static Colossal.Logging.ILog log;
    private static readonly System.Int32 kMaxHistoryLength;
    private static const System.Single kSimulationSecondsPerDay;
    private static const System.Single kSimtimeToRealtime;
    private static const System.Int32 kSecondsPerDay;
    private static const System.String kUniqueNameChars;

    public Game.Audio.Radio.Radio+RuntimeRadioChannel currentChannel { get; set; }
    public System.Boolean paused { get; set; }
    public System.Boolean skipAds { get; set; }
    public System.Boolean muted { get; set; }
    public Game.Audio.Radio.Radio+ClipInfo currentClip { get; private set; }
    public System.Boolean isEnabled { get; }
    public System.Boolean isActive { get; set; }
    public Game.Audio.Radio.Radio+RadioNetwork[] networkDescriptors { get; }
    public Game.Audio.Radio.Radio+RuntimeRadioChannel[] radioChannelDescriptors { get; }
    public System.String currentlyPlayingClipName { get; }
    public System.Double currentlyPlayingDuration { get; }
    public System.Double currentlyPlayingElapsed { get; }
    public System.Double currentlyPlayingRemaining { get; }
    public System.Double nextTimeCheck { get; }
    public Colossal.IO.AssetDatabase.AudioAsset pendingClip { get; }
    public System.Boolean hasEmergency { get; }
    public Unity.Entities.Entity emergency { get; }
    public Unity.Entities.Entity emergencyTarget { get; }
    public UnityEngine.Texture equalizerTexture { get; }

    public Radio(UnityEngine.Audio.AudioMixerGroup radioGroup);

    private System.Void <LoadRadio>b__87_1(Game.Audio.Radio.Radio+RadioNetwork network, Colossal.IO.AssetDatabase.SourceMeta meta);
    private System.Void <LoadRadio>b__87_2(Game.Audio.Radio.Radio+RadioChannel channel, Colossal.IO.AssetDatabase.SourceMeta meta);
    private System.Boolean AlertPlayingOrQueued();
    private System.Boolean CheckEntitlement(Game.Assets.IContentPrerequisite target);
    private System.Void Clear();
    private System.Void ClearEmergencyQueue();
    private System.Void ClearQueue(System.Boolean clearEmergencies);
    public System.Void Disable();
    public System.Void Enable(UnityEngine.GameObject listener);
    private System.Void FinishCurrentClip();
    public System.Void ForceRadioPause(System.Boolean pause);
    public System.Int32 GetActiveSource();
    public System.Double GetAudioSourceDuration(System.Int32 i);
    public System.Double GetAudioSourceTimeElapsed(System.Int32 i);
    public System.Double GetAudioSourceTimeRemaining(System.Int32 i);
    private System.Void GetCommercialClips(Game.Audio.Radio.Radio+RuntimeSegment segment);
    private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AudioAsset> GetEventClips(Game.Audio.Radio.Radio+RuntimeSegment segment, Colossal.IO.AssetDatabase.AudioAsset+Metatag metatag, System.Boolean newestFirst, System.Boolean flush);
    private System.Void GetNewsClips(Game.Audio.Radio.Radio+RuntimeSegment segment);
    private System.Void GetPlaylistClips(Game.Audio.Radio.Radio+RuntimeSegment segment);
    private System.Void GetPSAClips(Game.Audio.Radio.Radio+RuntimeSegment segment);
    public Game.Audio.Radio.Radio+RuntimeRadioChannel GetRadioChannel(System.String name);
    private Colossal.IO.AssetDatabase.AudioAsset[] GetSegmentAudioClip(System.Int32 clipsCap, System.String[] requiredTags, Game.Audio.Radio.Radio+SegmentType segmentType);
    private T[] GetSortedUIDescriptor<T>(System.Collections.Generic.Dictionary<System.String, T> desc);
    private System.Void GetTalkShowClips(Game.Audio.Radio.Radio+RuntimeSegment segment);
    private System.Void GetWeatherClips(Game.Audio.Radio.Radio+RuntimeSegment segment);
    private System.Void InvokeClipcallback(Colossal.IO.AssetDatabase.AudioAsset currentAsset);
    private System.Boolean IsEmergencyClipInQueue(Game.Triggers.RadioTag tag);
    private System.Void LoadRadio(System.Boolean enable);
    private System.Void Log(Game.Audio.Radio.Radio+RadioNetwork network);
    private System.Void Log(Game.Audio.Radio.Radio+RuntimeRadioChannel channel);
    private System.Void Log(Colossal.IO.AssetDatabase.AudioAsset clip);
    private System.Void Log(Game.Audio.Radio.Radio+RuntimeProgram program);
    private System.Void Log(Game.Audio.Radio.Radio+RuntimeSegment segment);
    private System.Void LogBrandPopularity(Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity> brandPopularity);
    private System.Void LogMap(System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AudioAsset>> map);
    private System.Void LogRadio();
    private static System.String MakeUniqueName(System.String name, System.Int32 length);
    private static System.String MakeUniqueRandomName(System.String name, System.Int32 length);
    public System.Void NextSong();
    private System.Void OnDisabled();
    private System.Void OnSettingsChanged(Game.Audio.Radio.Radio radio);
    public System.Void PreviousSong();
    private System.Void QueueClip(Game.Audio.Radio.Radio+ClipInfo clip, System.Boolean pushToFront);
    private System.Void QueueEmergencyClips();
    private System.Void QueueEmergencyIntroClip(Unity.Entities.Entity emergency, Unity.Entities.Entity emergencyTarget);
    private System.Void QueueNextClip();
    public System.Void Reload(System.Boolean enable);
    public System.Void RestoreRadioSettings(System.String savedChannel, System.Boolean savedAds);
    public System.Void SetSpectrumSettings(System.Boolean enabled, System.Int32 numSamples, UnityEngine.FFTWindow fftWindow, Game.Audio.Radio.Radio+Spectrum+BandType bandType, System.Single spacing, System.Single padding);
    private System.Boolean SetupNextClip();
    private System.Boolean SetupOrSkipSegment();
    private static System.Void SupportValueTypesForAOT();
    public System.Void Update(System.Single normalizedTime);
    private System.Void ValidateQueue();
}
```


## Fields

- `public Game.Audio.Radio.Radio+OnRadioEvent Reloaded`  

```csharp
public Game.Audio.Radio.Radio+OnRadioEvent Reloaded;
```

- `public Game.Audio.Radio.Radio+OnRadioEvent SettingsChanged`  

```csharp
public Game.Audio.Radio.Radio+OnRadioEvent SettingsChanged;
```

- `public Game.Audio.Radio.Radio+OnRadioEvent ProgramChanged`  

```csharp
public Game.Audio.Radio.Radio+OnRadioEvent ProgramChanged;
```

- `public Game.Audio.Radio.Radio+OnClipChanged ClipChanged`  

```csharp
public Game.Audio.Radio.Radio+OnClipChanged ClipChanged;
```

- `private System.Collections.Generic.Dictionary<System.String, Game.Audio.Radio.Radio+RadioNetwork> m_Networks`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.Audio.Radio.Radio+RadioNetwork> m_Networks;
```

- `private System.Collections.Generic.Dictionary<System.String, Game.Audio.Radio.Radio+RuntimeRadioChannel> m_RadioChannels`  

```csharp
private System.Collections.Generic.Dictionary<System.String, Game.Audio.Radio.Radio+RuntimeRadioChannel> m_RadioChannels;
```

- `private Game.Audio.Radio.Radio+RuntimeRadioChannel m_CurrentChannel`  

```csharp
private Game.Audio.Radio.Radio+RuntimeRadioChannel m_CurrentChannel;
```

- `private System.Boolean m_Paused`  

```csharp
private System.Boolean m_Paused;
```

- `private System.Boolean <skipAds>k__BackingField`  

```csharp
private System.Boolean <skipAds>k__BackingField;
```

- `private System.Boolean m_Muted`  

```csharp
private System.Boolean m_Muted;
```

- `private Game.Audio.Radio.Radio+ClipInfo <currentClip>k__BackingField`  

```csharp
private Game.Audio.Radio.Radio+ClipInfo <currentClip>k__BackingField;
```

- `private System.Int32 m_ReplayIndex`  

```csharp
private System.Int32 m_ReplayIndex;
```

- `private System.Collections.Generic.List<Game.Audio.Radio.Radio+ClipInfo> m_PlaylistHistory`  

```csharp
private System.Collections.Generic.List<Game.Audio.Radio.Radio+ClipInfo> m_PlaylistHistory;
```

- `private System.Collections.Generic.List<Game.Audio.Radio.Radio+ClipInfo> m_Queue`  

```csharp
private System.Collections.Generic.List<Game.Audio.Radio.Radio+ClipInfo> m_Queue;
```

- `private Game.Audio.Radio.Radio+RadioPlayer m_RadioPlayer`  

```csharp
private Game.Audio.Radio.Radio+RadioPlayer m_RadioPlayer;
```

- `private System.Boolean m_IsEnabled`  

```csharp
private System.Boolean m_IsEnabled;
```

- `private System.String m_LastSaveRadioChannel`  

```csharp
private System.String m_LastSaveRadioChannel;
```

- `private System.Boolean m_LastSaveRadioAdsState`  

```csharp
private System.Boolean m_LastSaveRadioAdsState;
```

- `private System.Boolean m_IsActive`  

```csharp
private System.Boolean m_IsActive;
```

- `private Game.Audio.Radio.Radio+RuntimeRadioChannel[] m_CachedRadioChannelDescriptors`  

```csharp
private Game.Audio.Radio.Radio+RuntimeRadioChannel[] m_CachedRadioChannelDescriptors;
```

- `private System.Collections.Generic.Dictionary<Game.Audio.Radio.Radio+SegmentType, Game.Audio.Radio.Radio+OnDemandClips> m_OnDemandClips`  

```csharp
private System.Collections.Generic.Dictionary<Game.Audio.Radio.Radio+SegmentType, Game.Audio.Radio.Radio+OnDemandClips> m_OnDemandClips;
```

- `private static readonly System.String kAlertsTag`  

```csharp
private static readonly System.String kAlertsTag;
```

- `private static readonly System.String kAlertsIntroTag`  

```csharp
private static readonly System.String kAlertsIntroTag;
```

- `private static Colossal.Logging.ILog log`  

```csharp
private static Colossal.Logging.ILog log;
```

- `private static readonly System.Int32 kMaxHistoryLength`  

```csharp
private static readonly System.Int32 kMaxHistoryLength;
```

- `private static const System.Single kSimulationSecondsPerDay`  

```csharp
private static const System.Single kSimulationSecondsPerDay;
```

- `private static const System.Single kSimtimeToRealtime`  

```csharp
private static const System.Single kSimtimeToRealtime;
```

- `private static const System.Int32 kSecondsPerDay`  

```csharp
private static const System.Int32 kSecondsPerDay;
```

- `private static const System.String kUniqueNameChars`  

```csharp
private static const System.String kUniqueNameChars;
```


## Properties

- `public Game.Audio.Radio.Radio+RuntimeRadioChannel currentChannel { get; set }`  

```csharp
public Game.Audio.Radio.Radio+RuntimeRadioChannel currentChannel { get; set; }
```

- `public System.Boolean paused { get; set }`  

```csharp
public System.Boolean paused { get; set; }
```

- `public System.Boolean skipAds { get; set }`  

```csharp
public System.Boolean skipAds { get; set; }
```

- `public System.Boolean muted { get; set }`  

```csharp
public System.Boolean muted { get; set; }
```

- `public Game.Audio.Radio.Radio+ClipInfo currentClip { get; private set }`  

```csharp
public Game.Audio.Radio.Radio+ClipInfo currentClip { get; private set; }
```

- `public System.Boolean isEnabled { get }`  

```csharp
public System.Boolean isEnabled { get; }
```

- `public System.Boolean isActive { get; set }`  

```csharp
public System.Boolean isActive { get; set; }
```

- `public Game.Audio.Radio.Radio+RadioNetwork[] networkDescriptors { get }`  

```csharp
public Game.Audio.Radio.Radio+RadioNetwork[] networkDescriptors { get; }
```

- `public Game.Audio.Radio.Radio+RuntimeRadioChannel[] radioChannelDescriptors { get }`  

```csharp
public Game.Audio.Radio.Radio+RuntimeRadioChannel[] radioChannelDescriptors { get; }
```

- `public System.String currentlyPlayingClipName { get }`  

```csharp
public System.String currentlyPlayingClipName { get; }
```

- `public System.Double currentlyPlayingDuration { get }`  

```csharp
public System.Double currentlyPlayingDuration { get; }
```

- `public System.Double currentlyPlayingElapsed { get }`  

```csharp
public System.Double currentlyPlayingElapsed { get; }
```

- `public System.Double currentlyPlayingRemaining { get }`  

```csharp
public System.Double currentlyPlayingRemaining { get; }
```

- `public System.Double nextTimeCheck { get }`  

```csharp
public System.Double nextTimeCheck { get; }
```

- `public Colossal.IO.AssetDatabase.AudioAsset pendingClip { get }`  

```csharp
public Colossal.IO.AssetDatabase.AudioAsset pendingClip { get; }
```

- `public System.Boolean hasEmergency { get }`  

```csharp
public System.Boolean hasEmergency { get; }
```

- `public Unity.Entities.Entity emergency { get }`  

```csharp
public Unity.Entities.Entity emergency { get; }
```

- `public Unity.Entities.Entity emergencyTarget { get }`  

```csharp
public Unity.Entities.Entity emergencyTarget { get; }
```

- `public UnityEngine.Texture equalizerTexture { get }`  

```csharp
public UnityEngine.Texture equalizerTexture { get; }
```


## Constructors

- `public Radio(UnityEngine.Audio.AudioMixerGroup radioGroup)`  

```csharp
public Radio(UnityEngine.Audio.AudioMixerGroup radioGroup);
```


## Methods

- `private <LoadRadio>b__87_1(Game.Audio.Radio.Radio+RadioNetwork network, Colossal.IO.AssetDatabase.SourceMeta meta) : System.Void`  

```csharp
private System.Void <LoadRadio>b__87_1(Game.Audio.Radio.Radio+RadioNetwork network, Colossal.IO.AssetDatabase.SourceMeta meta);
```

- `private <LoadRadio>b__87_2(Game.Audio.Radio.Radio+RadioChannel channel, Colossal.IO.AssetDatabase.SourceMeta meta) : System.Void`  

```csharp
private System.Void <LoadRadio>b__87_2(Game.Audio.Radio.Radio+RadioChannel channel, Colossal.IO.AssetDatabase.SourceMeta meta);
```

- `private AlertPlayingOrQueued() : System.Boolean`  

```csharp
private System.Boolean AlertPlayingOrQueued();
```

- `private CheckEntitlement(Game.Assets.IContentPrerequisite target) : System.Boolean`  

```csharp
private System.Boolean CheckEntitlement(Game.Assets.IContentPrerequisite target);
```

- `private Clear() : System.Void`  

```csharp
private System.Void Clear();
```

- `private ClearEmergencyQueue() : System.Void`  

```csharp
private System.Void ClearEmergencyQueue();
```

- `private ClearQueue(System.Boolean clearEmergencies = False) : System.Void`  

```csharp
private System.Void ClearQueue(System.Boolean clearEmergencies);
```

- `public Disable() : System.Void`  

```csharp
public System.Void Disable();
```

- `public Enable(UnityEngine.GameObject listener) : System.Void`  

```csharp
public System.Void Enable(UnityEngine.GameObject listener);
```

- `private FinishCurrentClip() : System.Void`  

```csharp
private System.Void FinishCurrentClip();
```

- `public ForceRadioPause(System.Boolean pause) : System.Void`  

```csharp
public System.Void ForceRadioPause(System.Boolean pause);
```

- `public GetActiveSource() : System.Int32`  

```csharp
public System.Int32 GetActiveSource();
```

- `public GetAudioSourceDuration(System.Int32 i) : System.Double`  

```csharp
public System.Double GetAudioSourceDuration(System.Int32 i);
```

- `public GetAudioSourceTimeElapsed(System.Int32 i) : System.Double`  

```csharp
public System.Double GetAudioSourceTimeElapsed(System.Int32 i);
```

- `public GetAudioSourceTimeRemaining(System.Int32 i) : System.Double`  

```csharp
public System.Double GetAudioSourceTimeRemaining(System.Int32 i);
```

- `private GetCommercialClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  

```csharp
private System.Void GetCommercialClips(Game.Audio.Radio.Radio+RuntimeSegment segment);
```

- `private GetEventClips(Game.Audio.Radio.Radio+RuntimeSegment segment, Colossal.IO.AssetDatabase.AudioAsset+Metatag metatag, System.Boolean newestFirst = False, System.Boolean flush = False) : System.Collections.Generic.List<Colossal.IO.AssetDatabase.AudioAsset>`  

```csharp
private System.Collections.Generic.List<Colossal.IO.AssetDatabase.AudioAsset> GetEventClips(Game.Audio.Radio.Radio+RuntimeSegment segment, Colossal.IO.AssetDatabase.AudioAsset+Metatag metatag, System.Boolean newestFirst, System.Boolean flush);
```

- `private GetNewsClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  

```csharp
private System.Void GetNewsClips(Game.Audio.Radio.Radio+RuntimeSegment segment);
```

- `private GetPlaylistClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  

```csharp
private System.Void GetPlaylistClips(Game.Audio.Radio.Radio+RuntimeSegment segment);
```

- `private GetPSAClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  

```csharp
private System.Void GetPSAClips(Game.Audio.Radio.Radio+RuntimeSegment segment);
```

- `public GetRadioChannel(System.String name) : Game.Audio.Radio.Radio+RuntimeRadioChannel`  

```csharp
public Game.Audio.Radio.Radio+RuntimeRadioChannel GetRadioChannel(System.String name);
```

- `private GetSegmentAudioClip(System.Int32 clipsCap, System.String[] requiredTags, Game.Audio.Radio.Radio+SegmentType segmentType) : Colossal.IO.AssetDatabase.AudioAsset[]`  

```csharp
private Colossal.IO.AssetDatabase.AudioAsset[] GetSegmentAudioClip(System.Int32 clipsCap, System.String[] requiredTags, Game.Audio.Radio.Radio+SegmentType segmentType);
```

- `private GetSortedUIDescriptor<T>(System.Collections.Generic.Dictionary<System.String, T> desc) : T[]`  

```csharp
private T[] GetSortedUIDescriptor<T>(System.Collections.Generic.Dictionary<System.String, T> desc);
```

- `private GetTalkShowClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  

```csharp
private System.Void GetTalkShowClips(Game.Audio.Radio.Radio+RuntimeSegment segment);
```

- `private GetWeatherClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  

```csharp
private System.Void GetWeatherClips(Game.Audio.Radio.Radio+RuntimeSegment segment);
```

- `private InvokeClipcallback(Colossal.IO.AssetDatabase.AudioAsset currentAsset) : System.Void`  

```csharp
private System.Void InvokeClipcallback(Colossal.IO.AssetDatabase.AudioAsset currentAsset);
```

- `private IsEmergencyClipInQueue(Game.Triggers.RadioTag tag) : System.Boolean`  

```csharp
private System.Boolean IsEmergencyClipInQueue(Game.Triggers.RadioTag tag);
```

- `private LoadRadio(System.Boolean enable) : System.Void`  

```csharp
private System.Void LoadRadio(System.Boolean enable);
```

- `private Log(Game.Audio.Radio.Radio+RadioNetwork network) : System.Void`  

```csharp
private System.Void Log(Game.Audio.Radio.Radio+RadioNetwork network);
```

- `private Log(Game.Audio.Radio.Radio+RuntimeRadioChannel channel) : System.Void`  

```csharp
private System.Void Log(Game.Audio.Radio.Radio+RuntimeRadioChannel channel);
```

- `private Log(Colossal.IO.AssetDatabase.AudioAsset clip) : System.Void`  

```csharp
private System.Void Log(Colossal.IO.AssetDatabase.AudioAsset clip);
```

- `private Log(Game.Audio.Radio.Radio+RuntimeProgram program) : System.Void`  

```csharp
private System.Void Log(Game.Audio.Radio.Radio+RuntimeProgram program);
```

- `private Log(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  

```csharp
private System.Void Log(Game.Audio.Radio.Radio+RuntimeSegment segment);
```

- `private LogBrandPopularity(Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity> brandPopularity) : System.Void`  

```csharp
private System.Void LogBrandPopularity(Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity> brandPopularity);
```

- `private LogMap(System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AudioAsset>> map) : System.Void`  

```csharp
private System.Void LogMap(System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AudioAsset>> map);
```

- `private LogRadio() : System.Void`  

```csharp
private System.Void LogRadio();
```

- `private static MakeUniqueName(System.String name, System.Int32 length) : System.String`  

```csharp
private static System.String MakeUniqueName(System.String name, System.Int32 length);
```

- `private static MakeUniqueRandomName(System.String name, System.Int32 length) : System.String`  

```csharp
private static System.String MakeUniqueRandomName(System.String name, System.Int32 length);
```

- `public NextSong() : System.Void`  

```csharp
public System.Void NextSong();
```

- `private OnDisabled() : System.Void`  

```csharp
private System.Void OnDisabled();
```

- `private OnSettingsChanged(Game.Audio.Radio.Radio radio) : System.Void`  

```csharp
private System.Void OnSettingsChanged(Game.Audio.Radio.Radio radio);
```

- `public PreviousSong() : System.Void`  

```csharp
public System.Void PreviousSong();
```

- `private QueueClip(Game.Audio.Radio.Radio+ClipInfo clip, System.Boolean pushToFront = False) : System.Void`  

```csharp
private System.Void QueueClip(Game.Audio.Radio.Radio+ClipInfo clip, System.Boolean pushToFront);
```

- `private QueueEmergencyClips() : System.Void`  

```csharp
private System.Void QueueEmergencyClips();
```

- `private QueueEmergencyIntroClip(Unity.Entities.Entity emergency, Unity.Entities.Entity emergencyTarget) : System.Void`  

```csharp
private System.Void QueueEmergencyIntroClip(Unity.Entities.Entity emergency, Unity.Entities.Entity emergencyTarget);
```

- `private QueueNextClip() : System.Void`  

```csharp
private System.Void QueueNextClip();
```

- `public Reload(System.Boolean enable = True) : System.Void`  

```csharp
public System.Void Reload(System.Boolean enable);
```

- `public RestoreRadioSettings(System.String savedChannel, System.Boolean savedAds) : System.Void`  

```csharp
public System.Void RestoreRadioSettings(System.String savedChannel, System.Boolean savedAds);
```

- `public SetSpectrumSettings(System.Boolean enabled, System.Int32 numSamples, UnityEngine.FFTWindow fftWindow, Game.Audio.Radio.Radio+Spectrum+BandType bandType, System.Single spacing, System.Single padding) : System.Void`  

```csharp
public System.Void SetSpectrumSettings(System.Boolean enabled, System.Int32 numSamples, UnityEngine.FFTWindow fftWindow, Game.Audio.Radio.Radio+Spectrum+BandType bandType, System.Single spacing, System.Single padding);
```

- `private SetupNextClip() : System.Boolean`  

```csharp
private System.Boolean SetupNextClip();
```

- `private SetupOrSkipSegment() : System.Boolean`  

```csharp
private System.Boolean SetupOrSkipSegment();
```

- `private static SupportValueTypesForAOT() : System.Void`  

```csharp
private static System.Void SupportValueTypesForAOT();
```

- `public Update(System.Single normalizedTime) : System.Void`  

```csharp
public System.Void Update(System.Single normalizedTime);
```

- `private ValidateQueue() : System.Void`  

```csharp
private System.Void ValidateQueue();
```


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

