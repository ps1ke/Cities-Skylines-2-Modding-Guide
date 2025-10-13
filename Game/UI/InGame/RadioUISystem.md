# Game.UI.InGame.RadioUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Code

```csharp
public class RadioUISystem : Game.UI.UISystemBase
{
    private Game.Prefabs.PrefabSystem m_PrefabSystem;
    private Game.Audio.Radio.Radio m_Radio;
    private Game.UI.InGame.GamePanelUISystem m_GamePanelUISystem;
    private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_PausedBinding;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_MutedBinding;
    private Colossal.UI.Binding.ValueBinding<System.Boolean> m_SkipAds;
    private Colossal.UI.Binding.GetterValueBinding<Game.Audio.Radio.Radio+RadioNetwork[]> m_NetworksBinding;
    private Colossal.UI.Binding.GetterValueBinding<Game.Audio.Radio.Radio+RuntimeRadioChannel[]> m_StationsBinding;
    private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.RadioUISystem+ClipInfo> m_CurrentSegmentBinding;
    private Colossal.UI.Binding.EventBinding m_SegmentChangedBinding;
    private System.Collections.Generic.Dictionary<System.String, System.String> m_LastSelectedStations;
    private Game.UI.Localization.CachedLocalizedStringBuilder<System.String> m_EmergencyMessages;
    private static const System.String kGroup;

    public RadioUISystem();

    private System.Boolean <OnCreate>b__14_2();
    private System.Boolean <OnCreate>b__14_3();
    private Unity.Entities.Entity <OnCreate>b__14_4();
    private System.Void FocusEmergency();
    private Game.UI.InGame.RadioUISystem+ClipInfo GetClipInfo(Game.Audio.Radio.Radio radio, Colossal.IO.AssetDatabase.AudioAsset asset);
    private Game.UI.InGame.RadioUISystem+ClipInfo GetCurrentClipInfo();
    private Colossal.IO.AssetDatabase.AudioAsset+Metatag GetMetaType(Game.Audio.Radio.Radio+SegmentType type);
    private System.Void OnClipChanged(Game.Audio.Radio.Radio radio, Colossal.IO.AssetDatabase.AudioAsset asset);
    protected virtual System.Void OnCreate();
    protected virtual System.Void OnDestroy();
    private System.Void OnProgramChanged(Game.Audio.Radio.Radio radio);
    private System.Void OnRadioReloaded(Game.Audio.Radio.Radio radio);
    private System.Void PlayNext();
    private System.Void PlayPrevious();
    private System.Void SelectNetwork(System.String name);
    private System.Void SelectStation(System.String name);
    private System.Void SetMuted(System.Boolean muted);
    private System.Void SetPaused(System.Boolean paused);
    private System.Void SetSkipAds(System.Boolean skipAds);
    private System.Void SetVolume(System.Single volume);
    private System.Void WriteEmergencyMessage(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
}
```


## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  

```csharp
private Game.Prefabs.PrefabSystem m_PrefabSystem;
```

- `private Game.Audio.Radio.Radio m_Radio`  

```csharp
private Game.Audio.Radio.Radio m_Radio;
```

- `private Game.UI.InGame.GamePanelUISystem m_GamePanelUISystem`  

```csharp
private Game.UI.InGame.GamePanelUISystem m_GamePanelUISystem;
```

- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  

```csharp
private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_PausedBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_PausedBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_MutedBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_MutedBinding;
```

- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_SkipAds`  

```csharp
private Colossal.UI.Binding.ValueBinding<System.Boolean> m_SkipAds;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.Audio.Radio.Radio+RadioNetwork[]> m_NetworksBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.Audio.Radio.Radio+RadioNetwork[]> m_NetworksBinding;
```

- `private Colossal.UI.Binding.GetterValueBinding<Game.Audio.Radio.Radio+RuntimeRadioChannel[]> m_StationsBinding`  

```csharp
private Colossal.UI.Binding.GetterValueBinding<Game.Audio.Radio.Radio+RuntimeRadioChannel[]> m_StationsBinding;
```

- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.RadioUISystem+ClipInfo> m_CurrentSegmentBinding`  

```csharp
private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.RadioUISystem+ClipInfo> m_CurrentSegmentBinding;
```

- `private Colossal.UI.Binding.EventBinding m_SegmentChangedBinding`  

```csharp
private Colossal.UI.Binding.EventBinding m_SegmentChangedBinding;
```

- `private System.Collections.Generic.Dictionary<System.String, System.String> m_LastSelectedStations`  

```csharp
private System.Collections.Generic.Dictionary<System.String, System.String> m_LastSelectedStations;
```

- `private Game.UI.Localization.CachedLocalizedStringBuilder<System.String> m_EmergencyMessages`  

```csharp
private Game.UI.Localization.CachedLocalizedStringBuilder<System.String> m_EmergencyMessages;
```

- `private static const System.String kGroup`  

```csharp
private static const System.String kGroup;
```


## Constructors

- `public RadioUISystem()`  

```csharp
[Preserve]
	public RadioUISystem()
	{
	}
```


## Methods

- `private <OnCreate>b__14_2() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__14_2();
```

- `private <OnCreate>b__14_3() : System.Boolean`  

```csharp
private System.Boolean <OnCreate>b__14_3();
```

- `private <OnCreate>b__14_4() : Unity.Entities.Entity`  

```csharp
private Unity.Entities.Entity <OnCreate>b__14_4();
```

- `private FocusEmergency() : System.Void`  

```csharp
private void FocusEmergency()
	{
		if (m_CameraUpdateSystem.orbitCameraController != null && m_Radio.emergencyTarget != Entity.Null)
		{
			m_CameraUpdateSystem.orbitCameraController.followedEntity = m_Radio.emergencyTarget;
			m_CameraUpdateSystem.orbitCameraController.TryMatchPosition(m_CameraUpdateSystem.activeCameraController);
			m_CameraUpdateSystem.activeCameraController = m_CameraUpdateSystem.orbitCameraController;
		}
	}
```

- `private GetClipInfo(Game.Audio.Radio.Radio radio, Colossal.IO.AssetDatabase.AudioAsset asset) : Game.UI.InGame.RadioUISystem+ClipInfo`  

```csharp
private ClipInfo GetClipInfo(Radio radio, AudioAsset asset)
	{
		if (asset != null)
		{
			if (asset.GetMetaTag(AudioAsset.Metatag.Type) == "Music")
			{
				return new ClipInfo
				{
					title = asset.GetMetaTag(AudioAsset.Metatag.Title),
					info = asset.GetMetaTag(AudioAsset.Metatag.Artist)
				};
			}
			return new ClipInfo
			{
				title = radio.currentChannel.name,
				info = radio.currentChannel.currentProgram.name
			};
		}
		return null;
	}
```

- `private GetCurrentClipInfo() : Game.UI.InGame.RadioUISystem+ClipInfo`  

```csharp
private ClipInfo GetCurrentClipInfo()
	{
		return GetClipInfo(m_Radio, m_Radio.currentClip.m_Asset);
	}
```

- `private GetMetaType(Game.Audio.Radio.Radio+SegmentType type) : Colossal.IO.AssetDatabase.AudioAsset+Metatag`  

```csharp
private AudioAsset.Metatag GetMetaType(Radio.SegmentType type)
	{
		return type switch
		{
			Radio.SegmentType.Playlist => AudioAsset.Metatag.Artist, 
			Radio.SegmentType.Commercial => AudioAsset.Metatag.Brand, 
			_ => AudioAsset.Metatag.Artist, 
		};
	}
```

- `private OnClipChanged(Game.Audio.Radio.Radio radio, Colossal.IO.AssetDatabase.AudioAsset asset) : System.Void`  

```csharp
private void OnClipChanged(Radio radio, AudioAsset asset)
	{
		m_StationsBinding.TriggerUpdate();
		m_CurrentSegmentBinding.Update(GetClipInfo(radio, asset));
	}
```

- `protected virtual OnCreate() : System.Void`  

```csharp
[Preserve]
	protected override void OnCreate()
	{
		base.OnCreate();
		m_PrefabSystem = base.World.GetOrCreateSystemManaged<PrefabSystem>();
		m_Radio = AudioManager.instance.radio;
		m_GamePanelUISystem = base.World.GetOrCreateSystemManaged<GamePanelUISystem>();
		m_CameraUpdateSystem = base.World.GetOrCreateSystemManaged<CameraUpdateSystem>();
		m_GamePanelUISystem.SetDefaultArgs(new RadioPanel());
		AddUpdateBinding(new GetterValueBinding<bool>("radio", "enabled", () => SharedSettings.instance.audio.radioActive));
		AddUpdateBinding(new GetterValueBinding<float>("radio", "volume", () => SharedSettings.instance.audio.radioVolume));
		AddBinding(m_PausedBinding = new ValueBinding<bool>("radio", "paused", m_Radio.paused));
		AddBinding(m_MutedBinding = new ValueBinding<bool>("radio", "muted", m_Radio.muted));
		AddBinding(m_SkipAds = new ValueBinding<bool>("radio", "skipAds", m_Radio.skipAds));
		AddUpdateBinding(new GetterValueBinding<bool>("radio", "emergencyMode", () => m_Radio.hasEmergency));
		AddUpdateBinding(new GetterValueBinding<bool>("radio", "emergencyFocusable", () => m_Radio.emergencyTarget != Entity.Null));
		AddUpdateBinding(new GetterValueBinding<Entity>("radio", "emergencyMessage", () => m_Radio.emergency, new DelegateWriter<Entity>(WriteEmergencyMessage)));
		AddUpdateBinding(new GetterValueBinding<string>("radio", "selectedNetwork", () => AudioManager.instance.radio.currentChannel?.network, ValueWriters.Nullable(new StringWriter())));
		AddUpdateBinding(new GetterValueBinding<string>("radio", "selectedStation", () => AudioManager.instance.radio.currentChannel?.name, ValueWriters.Nullable(new StringWriter())));
		AddBinding(m_NetworksBinding = new GetterValueBinding<Radio.RadioNetwork[]>("radio", "networks", () => AudioManager.instance.radio.networkDescriptors, new ArrayWriter<Radio.RadioNetwork>(new ValueWriter<Radio.RadioNetwork>())));
		AddBinding(m_StationsBinding = new GetterValueBinding<Radio.RuntimeRadioChannel[]>("radio", "stations", () => AudioManager.instance.radio.radioChannelDescriptors, new ArrayWriter<Radio.RuntimeRadioChannel>(new ValueWriter<Radio.RuntimeRadioChannel>())));
		AddBinding(m_CurrentSegmentBinding = new ValueBinding<ClipInfo>("radio", "currentSegment", GetCurrentClipInfo(), ValueWriters.Nullable(new ValueWriter<ClipInfo>())));
		AddBinding(m_SegmentChangedBinding = new EventBinding("radio", "segmentChanged"));
		AddBinding(new TriggerBinding<float>("radio", "setVolume", SetVolume));
		AddBinding(new TriggerBinding<bool>("radio", "setPaused", SetPaused));
		AddBinding(new TriggerBinding<bool>("radio", "setMuted", SetMuted));
		AddBinding(new TriggerBinding<bool>("radio", "setSkipAds", SetSkipAds));
		AddBinding(new TriggerBinding("radio", "playPrevious", PlayPrevious));
		AddBinding(new TriggerBinding("radio", "playNext", PlayNext));
		AddBinding(new TriggerBinding("radio", "focusEmergency", FocusEmergency));
		AddBinding(new TriggerBinding<string>("radio", "selectNetwork", SelectNetwork));
		AddBinding(new TriggerBinding<string>("radio", "selectStation", SelectStation));
		m_EmergencyMessages = CachedLocalizedStringBuilder<string>.Id((string name) => "Radio.EMERGENCY_MESSAGE[" + name + "]");
		m_LastSelectedStations = new Dictionary<string, string>();
		Radio radio = m_Radio;
		radio.Reloaded = (Radio.OnRadioEvent)Delegate.Combine(radio.Reloaded, new Radio.OnRadioEvent(OnRadioReloaded));
		Radio radio2 = m_Radio;
		radio2.ProgramChanged = (Radio.OnRadioEvent)Delegate.Combine(radio2.ProgramChanged, new Radio.OnRadioEvent(OnProgramChanged));
		Radio radio3 = m_Radio;
		radio3.ClipChanged = (Radio.OnClipChanged)Delegate.Combine(radio3.ClipChanged, new Radio.OnClipChanged(OnClipChanged));
	}
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
[Preserve]
	protected override void OnDestroy()
	{
		Radio radio = m_Radio;
		radio.Reloaded = (Radio.OnRadioEvent)Delegate.Remove(radio.Reloaded, new Radio.OnRadioEvent(OnRadioReloaded));
		Radio radio2 = m_Radio;
		radio2.ProgramChanged = (Radio.OnRadioEvent)Delegate.Remove(radio2.ProgramChanged, new Radio.OnRadioEvent(OnProgramChanged));
		Radio radio3 = m_Radio;
		radio3.ClipChanged = (Radio.OnClipChanged)Delegate.Remove(radio3.ClipChanged, new Radio.OnClipChanged(OnClipChanged));
		base.OnDestroy();
	}
```

- `private OnProgramChanged(Game.Audio.Radio.Radio radio) : System.Void`  

```csharp
private void OnProgramChanged(Radio radio)
	{
		m_StationsBinding.TriggerUpdate();
	}
```

- `private OnRadioReloaded(Game.Audio.Radio.Radio radio) : System.Void`  

```csharp
private void OnRadioReloaded(Radio radio)
	{
		m_NetworksBinding.Update();
		m_StationsBinding.Update();
		m_SkipAds.Update(radio.skipAds);
	}
```

- `private PlayNext() : System.Void`  

```csharp
private void PlayNext()
	{
		AudioManager.instance.radio.NextSong();
	}
```

- `private PlayPrevious() : System.Void`  

```csharp
private void PlayPrevious()
	{
		AudioManager.instance.radio.PreviousSong();
	}
```

- `private SelectNetwork(System.String name) : System.Void`  

```csharp
private void SelectNetwork(string name)
	{
		if (m_LastSelectedStations.TryGetValue(name, out var value))
		{
			SelectStation(value);
			return;
		}
		Radio.RuntimeRadioChannel[] radioChannelDescriptors = AudioManager.instance.radio.radioChannelDescriptors;
		foreach (Radio.RuntimeRadioChannel runtimeRadioChannel in radioChannelDescriptors)
		{
			if (runtimeRadioChannel.network == name)
			{
				SelectStation(runtimeRadioChannel.name);
				break;
			}
		}
	}
```

- `private SelectStation(System.String name) : System.Void`  

```csharp
private void SelectStation(string name)
	{
		Radio.RuntimeRadioChannel radioChannel = AudioManager.instance.radio.GetRadioChannel(name);
		if (radioChannel != null)
		{
			Radio.RuntimeRadioChannel currentChannel = AudioManager.instance.radio.currentChannel;
			if (currentChannel != null)
			{
				m_LastSelectedStations[currentChannel.network] = currentChannel.name;
			}
			AudioManager.instance.radio.currentChannel = radioChannel;
		}
	}
```

- `private SetMuted(System.Boolean muted) : System.Void`  

```csharp
private void SetMuted(bool muted)
	{
		m_Radio.muted = muted;
		m_MutedBinding.Update(muted);
	}
```

- `private SetPaused(System.Boolean paused) : System.Void`  

```csharp
private void SetPaused(bool paused)
	{
		m_Radio.paused = paused;
		m_PausedBinding.Update(paused);
	}
```

- `private SetSkipAds(System.Boolean skipAds) : System.Void`  

```csharp
private void SetSkipAds(bool skipAds)
	{
		m_Radio.skipAds = skipAds;
		m_SkipAds.Update(skipAds);
	}
```

- `private SetVolume(System.Single volume) : System.Void`  

```csharp
private void SetVolume(float volume)
	{
		SharedSettings.instance.audio.radioVolume = volume;
		SharedSettings.instance.audio.Apply();
	}
```

- `private WriteEmergencyMessage(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
private void WriteEmergencyMessage(IJsonWriter writer, Entity entity)
	{
		if (entity != Entity.Null)
		{
			PrefabBase prefab = m_PrefabSystem.GetPrefab<PrefabBase>(m_Radio.emergency);
			writer.Write(m_EmergencyMessages[prefab.name]);
		}
		else
		{
			writer.WriteNull();
		}
	}
```


## Nested types

- `Game.UI.InGame.RadioUISystem+ClipInfo`  
- `Game.UI.InGame.RadioUISystem+<>c`  

