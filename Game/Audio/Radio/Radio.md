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
public Radio(AudioMixerGroup radioGroup)
	{
		m_OnDemandClips = new Dictionary<SegmentType, OnDemandClips>();
		m_OnDemandClips[SegmentType.Commercial] = GetCommercialClips;
		m_OnDemandClips[SegmentType.PSA] = GetPSAClips;
		m_OnDemandClips[SegmentType.Playlist] = GetPlaylistClips;
		m_OnDemandClips[SegmentType.Talkshow] = GetTalkShowClips;
		m_OnDemandClips[SegmentType.News] = GetNewsClips;
		m_OnDemandClips[SegmentType.Weather] = GetWeatherClips;
		m_RadioPlayer = new RadioPlayer(radioGroup);
		SettingsChanged = (OnRadioEvent)Delegate.Combine(SettingsChanged, new OnRadioEvent(OnSettingsChanged));
	}
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
private bool AlertPlayingOrQueued()
	{
		if (!(currentClip.m_Emergency != Entity.Null))
		{
			if (m_Queue.Count > 0)
			{
				return m_Queue[0].m_Emergency != Entity.Null;
			}
			return false;
		}
		return true;
	}
```

- `private CheckEntitlement(Game.Assets.IContentPrerequisite target) : System.Boolean`  

```csharp
private bool CheckEntitlement(IContentPrerequisite target)
	{
		if (target.contentPrerequisites != null)
		{
			return target.contentPrerequisites.All(delegate(string x)
			{
				DlcId dlcId = PlatformManager.instance.GetDlcId(x);
				return PlatformManager.instance.IsDlcOwned(dlcId);
			});
		}
		return true;
	}
```

- `private Clear() : System.Void`  

```csharp
private void Clear()
	{
		m_CachedRadioChannelDescriptors = null;
		m_Networks.Clear();
		m_RadioChannels.Clear();
		currentChannel = null;
		OnDisabled();
	}
```

- `private ClearEmergencyQueue() : System.Void`  

```csharp
private void ClearEmergencyQueue()
	{
		JobHandle deps;
		NativeQueue<RadioTag> emergencyQueue = World.DefaultGameObjectInjectionWorld.GetExistingSystemManaged<RadioTagSystem>().GetEmergencyQueue(out deps);
		deps.Complete();
		emergencyQueue.Clear();
	}
```

- `private ClearQueue(System.Boolean clearEmergencies = False) : System.Void`  

```csharp
private void ClearQueue(bool clearEmergencies = false)
	{
		for (int i = 0; i < m_Queue.Count; i++)
		{
			if (m_Queue[i].m_LoadTask != null && (clearEmergencies || m_Queue[i].m_Emergency == Entity.Null))
			{
				m_Queue[i].m_Asset.Unload();
			}
		}
		if (clearEmergencies)
		{
			m_Queue.Clear();
			return;
		}
		m_Queue.RemoveAll((ClipInfo clip) => clip.m_Emergency == Entity.Null);
	}
```

- `public Disable() : System.Void`  

```csharp
public void Disable()
	{
		m_RadioPlayer?.Dispose();
		m_IsEnabled = false;
		OnDisabled();
	}
```

- `public Enable(UnityEngine.GameObject listener) : System.Void`  

```csharp
public void Enable(GameObject listener)
	{
		if (currentChannel == null)
		{
			if (m_LastSaveRadioChannel != null && m_RadioChannels.TryGetValue(m_LastSaveRadioChannel, out var value))
			{
				currentChannel = value;
				skipAds = m_LastSaveRadioAdsState;
			}
			else
			{
				skipAds = false;
				currentChannel = radioChannelDescriptors[0];
			}
		}
		if (m_IsActive && !m_IsEnabled && listener != null)
		{
			m_RadioPlayer.Create(listener);
			m_RadioPlayer.muted = m_Muted;
			SetSpectrumSettings(SharedSettings.instance.radio.enableSpectrum, SharedSettings.instance.radio.spectrumNumSamples, SharedSettings.instance.radio.fftWindowType, SharedSettings.instance.radio.bandType, SharedSettings.instance.radio.equalizerBarSpacing, SharedSettings.instance.radio.equalizerSidesPadding);
			m_IsEnabled = true;
		}
	}
```

- `private FinishCurrentClip() : System.Void`  

```csharp
private void FinishCurrentClip()
	{
		m_RadioPlayer.Play(null);
	}
```

- `public ForceRadioPause(System.Boolean pause) : System.Void`  

```csharp
public void ForceRadioPause(bool pause)
	{
		if (pause)
		{
			m_RadioPlayer.Pause();
		}
		else
		{
			m_RadioPlayer.Unpause();
		}
	}
```

- `public GetActiveSource() : System.Int32`  

```csharp
public int GetActiveSource()
	{
		return 0;
	}
```

- `public GetAudioSourceDuration(System.Int32 i) : System.Double`  

```csharp
public double GetAudioSourceDuration(int i)
	{
		return m_RadioPlayer.GetAudioSourceDuration();
	}
```

- `public GetAudioSourceTimeElapsed(System.Int32 i) : System.Double`  

```csharp
public double GetAudioSourceTimeElapsed(int i)
	{
		return m_RadioPlayer.GetAudioSourceTimeElapsed();
	}
```

- `public GetAudioSourceTimeRemaining(System.Int32 i) : System.Double`  

```csharp
public double GetAudioSourceTimeRemaining(int i)
	{
		return m_RadioPlayer.GetAudioSourceTimeRemaining();
	}
```

- `private GetCommercialClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  

```csharp
private void GetCommercialClips(RuntimeSegment segment)
	{
		if (!m_Networks.TryGetValue(currentChannel.network, out var value) || !value.allowAds)
		{
			return;
		}
		WeightedRandom<AudioAsset> weightedRandom = new WeightedRandom<AudioAsset>();
		Dictionary<string, List<AudioAsset>> dictionary = new Dictionary<string, List<AudioAsset>>();
		foreach (AudioAsset asset in AssetDatabase.global.GetAssets(SearchFilter<AudioAsset>.ByCondition((AudioAsset asset) => segment.tags.All(asset.ContainsTag))))
		{
			string metaTag = asset.GetMetaTag(AudioAsset.Metatag.Brand);
			if (metaTag != null)
			{
				if (!dictionary.TryGetValue(metaTag, out var value2))
				{
					value2 = new List<AudioAsset>();
					dictionary.Add(metaTag, value2);
				}
				value2.Add(asset);
			}
			else
			{
				log.ErrorFormat("Asset {0} ({1}) does not contain a brand metatag (for Commercial segment)", asset.id, asset.GetMetaTag(AudioAsset.Metatag.Title) ?? "<No title>");
			}
		}
		LogMap(dictionary);
		JobHandle dependency;
		NativeList<BrandPopularitySystem.BrandPopularity> brandPopularity = World.DefaultGameObjectInjectionWorld.GetExistingSystemManaged<BrandPopularitySystem>().ReadBrandPopularity(out dependency);
		dependency.Complete();
		LogBrandPopularity(brandPopularity);
		for (int num = 0; num < brandPopularity.Length; num++)
		{
			if (World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<PrefabSystem>().TryGetPrefab<BrandPrefab>(brandPopularity[num].m_BrandPrefab, out var prefab) && dictionary.TryGetValue(prefab.name, out var value3))
			{
				weightedRandom.AddRange(value3, brandPopularity[num].m_Popularity);
			}
		}
		List<AudioAsset> list = new List<AudioAsset>();
		for (int num2 = 0; num2 < segment.clipsCap; num2++)
		{
			AudioAsset audioAsset = weightedRandom.NextAndRemove();
			if (audioAsset != null)
			{
				list.Add(audioAsset);
			}
		}
		segment.clips = list;
		Log(segment);
	}
```

- `private GetEventClips(Game.Audio.Radio.Radio+RuntimeSegment segment, Colossal.IO.AssetDatabase.AudioAsset+Metatag metatag, System.Boolean newestFirst = False, System.Boolean flush = False) : System.Collections.Generic.List<Colossal.IO.AssetDatabase.AudioAsset>`  

```csharp
private List<AudioAsset> GetEventClips(RuntimeSegment segment, AudioAsset.Metatag metatag, bool newestFirst = false, bool flush = false)
	{
		RadioTagSystem existingSystemManaged = World.DefaultGameObjectInjectionWorld.GetExistingSystemManaged<RadioTagSystem>();
		PrefabSystem orCreateSystemManaged = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<PrefabSystem>();
		List<AudioAsset> list = new List<AudioAsset>(segment.clipsCap);
		List<AudioAsset> list2 = new List<AudioAsset>();
		RadioTag radioTag;
		while (list.Count < segment.clipsCap && existingSystemManaged.TryPopEvent(segment.type, newestFirst, out radioTag))
		{
			list2.Clear();
			foreach (AudioAsset asset in AssetDatabase.global.GetAssets(SearchFilter<AudioAsset>.ByCondition((AudioAsset asset) => segment.tags.All(asset.ContainsTag))))
			{
				if (asset.GetMetaTag(metatag) == orCreateSystemManaged.GetPrefab<PrefabBase>(radioTag.m_Event).name)
				{
					list2.Add(asset);
				}
			}
			if (list2.Count > 0)
			{
				list.Add(list2[new Unity.Mathematics.Random((uint)DateTime.Now.Ticks).NextInt(0, list2.Count)]);
			}
		}
		if (flush)
		{
			existingSystemManaged.FlushEvents(segment.type);
		}
		return list;
	}
```

- `private GetNewsClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  

```csharp
private void GetNewsClips(RuntimeSegment segment)
	{
		List<AudioAsset> eventClips = GetEventClips(segment, AudioAsset.Metatag.NewsType);
		segment.clips = eventClips;
		Log(segment);
	}
```

- `private GetPlaylistClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  

```csharp
private void GetPlaylistClips(RuntimeSegment segment)
	{
		segment.clips = GetSegmentAudioClip(segment.clipsCap, segment.tags, segment.type);
	}
```

- `private GetPSAClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  

```csharp
private void GetPSAClips(RuntimeSegment segment)
	{
		if (m_Networks.TryGetValue(currentChannel.network, out var value) && !value.allowAds)
		{
			List<AudioAsset> eventClips = GetEventClips(segment, AudioAsset.Metatag.PSAType);
			segment.clips = eventClips;
			Log(segment);
		}
	}
```

- `public GetRadioChannel(System.String name) : Game.Audio.Radio.Radio+RuntimeRadioChannel`  

```csharp
public RuntimeRadioChannel GetRadioChannel(string name)
	{
		if (m_RadioChannels.TryGetValue(name, out var value))
		{
			return value;
		}
		return null;
	}
```

- `private GetSegmentAudioClip(System.Int32 clipsCap, System.String[] requiredTags, Game.Audio.Radio.Radio+SegmentType segmentType) : Colossal.IO.AssetDatabase.AudioAsset[]`  

```csharp
private AudioAsset[] GetSegmentAudioClip(int clipsCap, string[] requiredTags, SegmentType segmentType)
	{
		IEnumerable<AudioAsset> assets = AssetDatabase.global.GetAssets(SearchFilter<AudioAsset>.ByCondition((AudioAsset asset) => requiredTags.All(asset.ContainsTag)));
		List<AudioAsset> list = new List<AudioAsset>();
		list.AddRange(assets);
		System.Random rnd = new System.Random();
		List<int> list2 = (from x in Enumerable.Range(0, list.Count)
			orderby rnd.Next()
			select x).Take(clipsCap).ToList();
		AudioAsset[] array = new AudioAsset[clipsCap];
		for (int num = 0; num < array.Length; num++)
		{
			array[num] = list[list2[num]];
		}
		return array;
	}
```

- `private GetSortedUIDescriptor<T>(System.Collections.Generic.Dictionary<System.String, T> desc) : T[]`  

```csharp
private T[] GetSortedUIDescriptor<T>(System.Collections.Generic.Dictionary<System.String, T> desc);
```

- `private GetTalkShowClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  

```csharp
private void GetTalkShowClips(RuntimeSegment segment)
	{
		segment.clips = GetSegmentAudioClip(segment.clipsCap, segment.tags, segment.type);
	}
```

- `private GetWeatherClips(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  

```csharp
private void GetWeatherClips(RuntimeSegment segment)
	{
		List<AudioAsset> eventClips = GetEventClips(segment, AudioAsset.Metatag.WeatherType, newestFirst: true, flush: true);
		segment.clips = eventClips;
		Log(segment);
	}
```

- `private InvokeClipcallback(Colossal.IO.AssetDatabase.AudioAsset currentAsset) : System.Void`  

```csharp
private void InvokeClipcallback(AudioAsset currentAsset)
	{
		try
		{
			ClipChanged?.Invoke(this, currentAsset);
		}
		catch (Exception exception)
		{
			log.Critical(exception);
		}
	}
```

- `private IsEmergencyClipInQueue(Game.Triggers.RadioTag tag) : System.Boolean`  

```csharp
private bool IsEmergencyClipInQueue(RadioTag tag)
	{
		if (currentClip.m_Emergency != Entity.Null && currentClip.m_Emergency == tag.m_Event)
		{
			return true;
		}
		for (int i = 0; i < m_Queue.Count; i++)
		{
			if (m_Queue[i].m_Emergency != Entity.Null && m_Queue[i].m_Emergency == tag.m_Event)
			{
				return true;
			}
		}
		return false;
	}
```

- `private LoadRadio(System.Boolean enable) : System.Void`  

```csharp
private void LoadRadio(bool enable)
	{
		try
		{
			Clear();
			using (Colossal.PerformanceCounter.Start(delegate(TimeSpan t)
			{
				log.DebugFormat("Loaded radio configuration in {0}ms", t.TotalMilliseconds);
			}))
			{
				AssetDatabase.global.LoadSettings("Radio Network", delegate(RadioNetwork network, SourceMeta meta)
				{
					if (CheckEntitlement(network))
					{
						m_Networks.Add(network.name, network);
					}
				});
				AssetDatabase.global.LoadSettings("Radio Channel", delegate(RadioChannel channel, SourceMeta meta)
				{
					if (CheckEntitlement(channel))
					{
						string text = channel.name;
						while (m_RadioChannels.ContainsKey(text))
						{
							text = text + "_" + MakeUniqueRandomName(text, 4);
						}
						log.InfoFormat("Radio channel id '{0}' added", text);
						m_RadioChannels.Add(text, channel.CreateRuntime(meta.path));
					}
				});
			}
			LogRadio();
			if (enable)
			{
				Enable(Camera.main.gameObject);
			}
		}
		catch (Exception exception)
		{
			log.Error(exception);
		}
	}
```

- `private Log(Game.Audio.Radio.Radio+RadioNetwork network) : System.Void`  

```csharp
private void Log(RuntimeSegment segment)
	{
		log.Debug($"type: {segment.type}");
		using (log.indent.scoped)
		{
			if (segment.tags != null)
			{
				log.Debug("tags: " + string.Join(", ", segment.tags));
			}
			if (segment.clips == null)
			{
				return;
			}
			log.Verbose($"duration total: {segment.durationMs}ms ({FormatUtils.FormatTimeDebug(segment.durationMs)})");
			log.DebugFormat("Clips ({0})", segment.clips.Count);
			using (log.indent.scoped)
			{
				foreach (AudioAsset clip in segment.clips)
				{
					Log(clip);
				}
			}
			log.DebugFormat("Clips cap: {0}", segment.clipsCap);
		}
	}
```

- `private Log(Game.Audio.Radio.Radio+RuntimeRadioChannel channel) : System.Void`  

```csharp
private void Log(RuntimeSegment segment)
	{
		log.Debug($"type: {segment.type}");
		using (log.indent.scoped)
		{
			if (segment.tags != null)
			{
				log.Debug("tags: " + string.Join(", ", segment.tags));
			}
			if (segment.clips == null)
			{
				return;
			}
			log.Verbose($"duration total: {segment.durationMs}ms ({FormatUtils.FormatTimeDebug(segment.durationMs)})");
			log.DebugFormat("Clips ({0})", segment.clips.Count);
			using (log.indent.scoped)
			{
				foreach (AudioAsset clip in segment.clips)
				{
					Log(clip);
				}
			}
			log.DebugFormat("Clips cap: {0}", segment.clipsCap);
		}
	}
```

- `private Log(Colossal.IO.AssetDatabase.AudioAsset clip) : System.Void`  

```csharp
private void Log(RuntimeSegment segment)
	{
		log.Debug($"type: {segment.type}");
		using (log.indent.scoped)
		{
			if (segment.tags != null)
			{
				log.Debug("tags: " + string.Join(", ", segment.tags));
			}
			if (segment.clips == null)
			{
				return;
			}
			log.Verbose($"duration total: {segment.durationMs}ms ({FormatUtils.FormatTimeDebug(segment.durationMs)})");
			log.DebugFormat("Clips ({0})", segment.clips.Count);
			using (log.indent.scoped)
			{
				foreach (AudioAsset clip in segment.clips)
				{
					Log(clip);
				}
			}
			log.DebugFormat("Clips cap: {0}", segment.clipsCap);
		}
	}
```

- `private Log(Game.Audio.Radio.Radio+RuntimeProgram program) : System.Void`  

```csharp
private void Log(RuntimeSegment segment)
	{
		log.Debug($"type: {segment.type}");
		using (log.indent.scoped)
		{
			if (segment.tags != null)
			{
				log.Debug("tags: " + string.Join(", ", segment.tags));
			}
			if (segment.clips == null)
			{
				return;
			}
			log.Verbose($"duration total: {segment.durationMs}ms ({FormatUtils.FormatTimeDebug(segment.durationMs)})");
			log.DebugFormat("Clips ({0})", segment.clips.Count);
			using (log.indent.scoped)
			{
				foreach (AudioAsset clip in segment.clips)
				{
					Log(clip);
				}
			}
			log.DebugFormat("Clips cap: {0}", segment.clipsCap);
		}
	}
```

- `private Log(Game.Audio.Radio.Radio+RuntimeSegment segment) : System.Void`  

```csharp
private void Log(RuntimeSegment segment)
	{
		log.Debug($"type: {segment.type}");
		using (log.indent.scoped)
		{
			if (segment.tags != null)
			{
				log.Debug("tags: " + string.Join(", ", segment.tags));
			}
			if (segment.clips == null)
			{
				return;
			}
			log.Verbose($"duration total: {segment.durationMs}ms ({FormatUtils.FormatTimeDebug(segment.durationMs)})");
			log.DebugFormat("Clips ({0})", segment.clips.Count);
			using (log.indent.scoped)
			{
				foreach (AudioAsset clip in segment.clips)
				{
					Log(clip);
				}
			}
			log.DebugFormat("Clips cap: {0}", segment.clipsCap);
		}
	}
```

- `private LogBrandPopularity(Unity.Collections.NativeList<Game.Simulation.BrandPopularitySystem+BrandPopularity> brandPopularity) : System.Void`  

```csharp
private void LogBrandPopularity(NativeList<BrandPopularitySystem.BrandPopularity> brandPopularity)
	{
		if (log.isDebugEnabled)
		{
			string text = "Brands popularity:\n";
			PrefabSystem orCreateSystemManaged = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<PrefabSystem>();
			for (int i = 0; i < brandPopularity.Length; i++)
			{
				string prefabName = orCreateSystemManaged.GetPrefabName(brandPopularity[i].m_BrandPrefab);
				text += $"{prefabName} - {brandPopularity[i].m_Popularity}\n";
			}
			log.Verbose(text);
		}
	}
```

- `private LogMap(System.Collections.Generic.Dictionary<System.String, System.Collections.Generic.List<Colossal.IO.AssetDatabase.AudioAsset>> map) : System.Void`  

```csharp
private void LogMap(Dictionary<string, List<AudioAsset>> map)
	{
		if (!log.isDebugEnabled)
		{
			return;
		}
		string text = "Audio asset map:\n";
		foreach (KeyValuePair<string, List<AudioAsset>> item in map)
		{
			text = text + item.Key + "\n";
			foreach (AudioAsset item2 in item.Value)
			{
				text += $"  {item2.GetMetaTag(AudioAsset.Metatag.Title)} ({item2.id})\n";
			}
		}
		log.Verbose(text);
	}
```

- `private LogRadio() : System.Void`  

```csharp
private void LogRadio()
	{
		if (!log.isDebugEnabled)
		{
			return;
		}
		log.DebugFormat("Networks ({0})", m_Networks.Count);
		using (log.indent.scoped)
		{
			foreach (RadioNetwork value in m_Networks.Values)
			{
				Log(value);
			}
		}
		log.DebugFormat("Channels ({0})", m_RadioChannels.Count);
		using (log.indent.scoped)
		{
			foreach (RuntimeRadioChannel value2 in m_RadioChannels.Values)
			{
				Log(value2);
			}
		}
	}
```

- `private static MakeUniqueName(System.String name, System.Int32 length) : System.String`  

```csharp
private static string MakeUniqueName(string name, int length)
	{
		char[] array = new char[length];
		for (int i = 0; i < name.Length; i++)
		{
			array[i % (length - 1)] += name[i];
		}
		for (int j = 0; j < array.Length; j++)
		{
			array[j] = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789"[array[j] % "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789".Length];
		}
		return new string(array);
	}
```

- `private static MakeUniqueRandomName(System.String name, System.Int32 length) : System.String`  

```csharp
private static string MakeUniqueRandomName(string name, int length)
	{
		char[] array = new char[length];
		for (int i = 0; i < array.Length; i++)
		{
			array[i] = "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789"[UnityEngine.Random.Range(0, "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789".Length) % "ABCDEFGHIJKLMNOPQRSTUVWXYZabcdefghijklmnopqrstuvwxyz0123456789".Length];
		}
		return new string(array);
	}
```

- `public NextSong() : System.Void`  

```csharp
public void NextSong()
	{
		if (m_ReplayIndex > 0)
		{
			m_ReplayIndex--;
			ClipInfo clip = m_PlaylistHistory[m_ReplayIndex];
			clip.m_Replaying = true;
			clip.m_LoadTask = clip.m_Asset.LoadAsync();
			QueueClip(clip, pushToFront: true);
		}
		FinishCurrentClip();
	}
```

- `private OnDisabled() : System.Void`  

```csharp
private void OnDisabled()
	{
		FinishCurrentClip();
		ClearQueue(clearEmergencies: true);
		m_ReplayIndex = 0;
		if (currentClip.m_LoadTask != null)
		{
			currentClip.m_Asset.Unload();
		}
		currentClip = default(ClipInfo);
		m_PlaylistHistory.Clear();
	}
```

- `private OnSettingsChanged(Game.Audio.Radio.Radio radio) : System.Void`  

```csharp
private void OnSettingsChanged(Radio radio)
	{
		if (radio.isActive)
		{
			if (GameManager.instance != null && GameManager.instance.gameMode == GameMode.Game && Camera.main != null && radio.radioChannelDescriptors.Length != 0)
			{
				radio.Enable(Camera.main.gameObject);
			}
		}
		else
		{
			Disable();
		}
	}
```

- `public PreviousSong() : System.Void`  

```csharp
public void PreviousSong()
	{
		if (m_RadioPlayer.GetAudioSourceTimeElapsed() > 2.0 || m_ReplayIndex >= m_PlaylistHistory.Count - 1)
		{
			m_RadioPlayer.Rewind();
			return;
		}
		m_ReplayIndex++;
		ClipInfo clip = m_PlaylistHistory[m_ReplayIndex];
		clip.m_Replaying = true;
		clip.m_LoadTask = clip.m_Asset.LoadAsync();
		QueueClip(clip, pushToFront: true);
		FinishCurrentClip();
	}
```

- `private QueueClip(Game.Audio.Radio.Radio+ClipInfo clip, System.Boolean pushToFront = False) : System.Void`  

```csharp
private void QueueClip(ClipInfo clip, bool pushToFront = false)
	{
		if (clip.m_Emergency != Entity.Null || clip.m_ResumeAtPosition >= 0 || pushToFront)
		{
			int num = m_Queue.FindIndex((ClipInfo info) => info.m_Emergency == Entity.Null);
			m_Queue.Insert((num < 0) ? m_Queue.Count : num, clip);
		}
		else
		{
			m_Queue.Add(clip);
		}
	}
```

- `private QueueEmergencyClips() : System.Void`  

```csharp
private void QueueEmergencyClips()
	{
		JobHandle deps;
		NativeQueue<RadioTag> emergencyQueue = World.DefaultGameObjectInjectionWorld.GetExistingSystemManaged<RadioTagSystem>().GetEmergencyQueue(out deps);
		deps.Complete();
		while (emergencyQueue.Count > 0)
		{
			RadioTag tag = emergencyQueue.Dequeue();
			if (IsEmergencyClipInQueue(tag))
			{
				continue;
			}
			List<AudioAsset> list = new List<AudioAsset>();
			PrefabBase prefab = World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<PrefabSystem>().GetPrefab<PrefabBase>(tag.m_Event);
			foreach (AudioAsset asset in AssetDatabase.global.GetAssets(SearchFilter<AudioAsset>.ByCondition((AudioAsset asset) => asset.ContainsTag(kAlertsTag))))
			{
				if (asset.GetMetaTag(AudioAsset.Metatag.AlertType) == prefab.name)
				{
					list.Add(asset);
				}
			}
			if (list.Count > 0)
			{
				if (!AlertPlayingOrQueued())
				{
					QueueEmergencyIntroClip(tag.m_Event, tag.m_Target);
				}
				AudioAsset audioAsset = list[new Unity.Mathematics.Random((uint)DateTime.Now.Ticks).NextInt(0, list.Count)];
				QueueClip(new ClipInfo
				{
					m_Asset = audioAsset,
					m_Emergency = tag.m_Event,
					m_EmergencyTarget = tag.m_Target,
					m_SegmentType = SegmentType.Emergency,
					m_LoadTask = audioAsset.LoadAsync(),
					m_ResumeAtPosition = -1
				});
			}
		}
		emergencyQueue.Clear();
	}
```

- `private QueueEmergencyIntroClip(Unity.Entities.Entity emergency, Unity.Entities.Entity emergencyTarget) : System.Void`  

```csharp
private void QueueEmergencyIntroClip(Entity emergency, Entity emergencyTarget)
	{
		List<AudioAsset> list = new List<AudioAsset>();
		foreach (AudioAsset asset in AssetDatabase.global.GetAssets(SearchFilter<AudioAsset>.ByCondition((AudioAsset asset) => asset.ContainsTag(kAlertsIntroTag))))
		{
			list.Add(asset);
		}
		if (list.Count > 0)
		{
			AudioAsset audioAsset = list[new Unity.Mathematics.Random((uint)DateTime.Now.Ticks).NextInt(0, list.Count)];
			QueueClip(new ClipInfo
			{
				m_Asset = audioAsset,
				m_Emergency = emergency,
				m_EmergencyTarget = emergencyTarget,
				m_SegmentType = SegmentType.Emergency,
				m_LoadTask = audioAsset.LoadAsync(),
				m_ResumeAtPosition = -1
			});
		}
	}
```

- `private QueueNextClip() : System.Void`  

```csharp
private void QueueNextClip()
	{
		if (m_Queue.Count == 0 && currentChannel?.currentProgram?.currentSegment?.currentClip != null)
		{
			QueueClip(new ClipInfo
			{
				m_Asset = currentChannel.currentProgram.currentSegment.currentClip,
				m_SegmentType = currentChannel.currentProgram.currentSegment.type,
				m_Emergency = Entity.Null,
				m_LoadTask = currentChannel.currentProgram.currentSegment.currentClip.LoadAsync(),
				m_ResumeAtPosition = -1
			});
			SetupNextClip();
		}
	}
```

- `public Reload(System.Boolean enable = True) : System.Void`  

```csharp
public void Reload(bool enable = true)
	{
		LoadRadio(enable);
		Reloaded?.Invoke(this);
	}
```

- `public RestoreRadioSettings(System.String savedChannel, System.Boolean savedAds) : System.Void`  

```csharp
public void RestoreRadioSettings(string savedChannel, bool savedAds)
	{
		m_LastSaveRadioChannel = savedChannel;
		m_LastSaveRadioAdsState = savedAds;
	}
```

- `public SetSpectrumSettings(System.Boolean enabled, System.Int32 numSamples, UnityEngine.FFTWindow fftWindow, Game.Audio.Radio.Radio+Spectrum+BandType bandType, System.Single spacing, System.Single padding) : System.Void`  

```csharp
public void SetSpectrumSettings(bool enabled, int numSamples, FFTWindow fftWindow, Spectrum.BandType bandType, float spacing, float padding)
	{
		m_RadioPlayer.SetSpectrumSettings(enabled, numSamples, fftWindow, bandType, spacing, padding);
	}
```

- `private SetupNextClip() : System.Boolean`  

```csharp
private bool SetupNextClip()
	{
		if (currentChannel?.currentProgram?.currentSegment == null)
		{
			return false;
		}
		if (!currentChannel.currentProgram.currentSegment.GoToNextClip())
		{
			currentChannel.currentProgram.GoToNextSegment();
			if (!SetupOrSkipSegment())
			{
				return false;
			}
		}
		return true;
	}
```

- `private SetupOrSkipSegment() : System.Boolean`  

```csharp
private bool SetupOrSkipSegment()
	{
		if (currentChannel?.currentProgram == null)
		{
			return false;
		}
		RuntimeProgram currentProgram = currentChannel.currentProgram;
		while (true)
		{
			RuntimeSegment currentSegment = currentProgram.currentSegment;
			if (currentSegment == null)
			{
				return false;
			}
			if (m_OnDemandClips.TryGetValue(currentSegment.type, out var value))
			{
				value(currentSegment);
			}
			if (currentSegment.clips.Count != 0)
			{
				break;
			}
			if (!currentProgram.GoToNextSegment())
			{
				return false;
			}
		}
		return true;
	}
```

- `private static SupportValueTypesForAOT() : System.Void`  

```csharp
private static void SupportValueTypesForAOT()
	{
		JSON.SupportTypeForAOT<SegmentType>();
	}
```

- `public Update(System.Single normalizedTime) : System.Void`  

```csharp
public void Update(float normalizedTime)
	{
		if (!isActive || !isEnabled)
		{
			ClearEmergencyQueue();
			return;
		}
		try
		{
			m_RadioPlayer.UpdateSpectrum();
			int timeOfDaySeconds = Mathf.RoundToInt(normalizedTime * 24f * 3600f);
			bool flag = false;
			bool flag2 = false;
			RuntimeRadioChannel[] array = radioChannelDescriptors;
			foreach (RuntimeRadioChannel obj in array)
			{
				bool flag3 = obj.Update(timeOfDaySeconds);
				if (obj == currentChannel)
				{
					flag = flag3;
				}
				flag2 = flag2 || flag3;
			}
			if (flag)
			{
				log.DebugFormat("Program changed callback for on-demand clips initialization");
				SetupOrSkipSegment();
			}
			QueueEmergencyClips();
			ValidateQueue();
			if (m_Queue.Count > 0)
			{
				ClipInfo clipInfo = m_Queue[0];
				if (currentClip.m_Emergency == Entity.Null && clipInfo.m_Emergency != Entity.Null)
				{
					if (clipInfo.m_LoadTask != null && clipInfo.m_LoadTask.IsCompleted)
					{
						m_RadioPlayer.Unpause();
						ClipInfo clip = currentClip;
						clip.m_ResumeAtPosition = m_RadioPlayer.playbackPosition;
						m_RadioPlayer.Play(clipInfo.m_LoadTask.Result);
						currentClip = clipInfo;
						m_Queue.RemoveAt(0);
						QueueClip(clip);
						InvokeClipcallback(currentClip.m_Asset);
					}
				}
				else if (m_RadioPlayer.GetAudioSourceTimeRemaining() <= 0.0 && clipInfo.m_LoadTask != null && clipInfo.m_LoadTask.IsCompleted)
				{
					if (clipInfo.m_SegmentType == SegmentType.Commercial && skipAds)
					{
						clipInfo.m_Asset.Unload();
						m_Queue.RemoveAt(0);
					}
					else
					{
						m_RadioPlayer.Play(clipInfo.m_LoadTask.Result, (clipInfo.m_ResumeAtPosition >= 0) ? clipInfo.m_ResumeAtPosition : 0);
						if (currentClip.m_LoadTask != null)
						{
							currentClip.m_Asset.Unload();
						}
						currentClip = clipInfo;
						if (currentClip.m_SegmentType == SegmentType.Playlist && currentClip.m_ResumeAtPosition < 0 && !currentClip.m_Replaying)
						{
							ClipInfo item = currentClip;
							item.m_LoadTask = null;
							m_PlaylistHistory.Insert(0, item);
							while (m_PlaylistHistory.Count > kMaxHistoryLength)
							{
								m_PlaylistHistory.RemoveAt(m_PlaylistHistory.Count - 1);
							}
						}
						if (!currentClip.m_Replaying)
						{
							m_ReplayIndex = 0;
						}
						m_Queue.RemoveAt(0);
						if (paused && currentClip.m_Emergency == Entity.Null)
						{
							m_RadioPlayer.Pause();
						}
						InvokeClipcallback(currentClip.m_Asset);
					}
				}
			}
			QueueNextClip();
			if (flag2)
			{
				ProgramChanged(this);
			}
		}
		catch (Exception exception)
		{
			log.Fatal(exception);
		}
	}
```

- `private ValidateQueue() : System.Void`  

```csharp
private void ValidateQueue()
	{
		for (int i = 0; i < m_Queue.Count; i++)
		{
			while (i < m_Queue.Count && (m_Queue[i].m_LoadTask == null || m_Queue[i].m_LoadTask.IsFaulted || m_Queue[i].m_LoadTask.IsCanceled))
			{
				if (m_Queue[i].m_LoadTask != null)
				{
					m_Queue[i].m_Asset.Unload();
				}
				m_Queue.RemoveAt(i);
			}
		}
	}
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

