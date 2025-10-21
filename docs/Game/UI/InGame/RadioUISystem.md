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
public RadioUISystem();
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
private System.Void FocusEmergency();
```

- `private GetClipInfo(Game.Audio.Radio.Radio radio, Colossal.IO.AssetDatabase.AudioAsset asset) : Game.UI.InGame.RadioUISystem+ClipInfo`  

```csharp
private Game.UI.InGame.RadioUISystem+ClipInfo GetClipInfo(Game.Audio.Radio.Radio radio, Colossal.IO.AssetDatabase.AudioAsset asset);
```

- `private GetCurrentClipInfo() : Game.UI.InGame.RadioUISystem+ClipInfo`  

```csharp
private Game.UI.InGame.RadioUISystem+ClipInfo GetCurrentClipInfo();
```

- `private GetMetaType(Game.Audio.Radio.Radio+SegmentType type) : Colossal.IO.AssetDatabase.AudioAsset+Metatag`  

```csharp
private Colossal.IO.AssetDatabase.AudioAsset+Metatag GetMetaType(Game.Audio.Radio.Radio+SegmentType type);
```

- `private OnClipChanged(Game.Audio.Radio.Radio radio, Colossal.IO.AssetDatabase.AudioAsset asset) : System.Void`  

```csharp
private System.Void OnClipChanged(Game.Audio.Radio.Radio radio, Colossal.IO.AssetDatabase.AudioAsset asset);
```

- `protected virtual OnCreate() : System.Void`  

```csharp
protected virtual System.Void OnCreate();
```

- `protected virtual OnDestroy() : System.Void`  

```csharp
protected virtual System.Void OnDestroy();
```

- `private OnProgramChanged(Game.Audio.Radio.Radio radio) : System.Void`  

```csharp
private System.Void OnProgramChanged(Game.Audio.Radio.Radio radio);
```

- `private OnRadioReloaded(Game.Audio.Radio.Radio radio) : System.Void`  

```csharp
private System.Void OnRadioReloaded(Game.Audio.Radio.Radio radio);
```

- `private PlayNext() : System.Void`  

```csharp
private System.Void PlayNext();
```

- `private PlayPrevious() : System.Void`  

```csharp
private System.Void PlayPrevious();
```

- `private SelectNetwork(System.String name) : System.Void`  

```csharp
private System.Void SelectNetwork(System.String name);
```

- `private SelectStation(System.String name) : System.Void`  

```csharp
private System.Void SelectStation(System.String name);
```

- `private SetMuted(System.Boolean muted) : System.Void`  

```csharp
private System.Void SetMuted(System.Boolean muted);
```

- `private SetPaused(System.Boolean paused) : System.Void`  

```csharp
private System.Void SetPaused(System.Boolean paused);
```

- `private SetSkipAds(System.Boolean skipAds) : System.Void`  

```csharp
private System.Void SetSkipAds(System.Boolean skipAds);
```

- `private SetVolume(System.Single volume) : System.Void`  

```csharp
private System.Void SetVolume(System.Single volume);
```

- `private WriteEmergencyMessage(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

```csharp
private System.Void WriteEmergencyMessage(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity);
```


## Nested types

- `Game.UI.InGame.RadioUISystem+ClipInfo`  
- `Game.UI.InGame.RadioUISystem+<>c`  

