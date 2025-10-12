# Game.UI.InGame.RadioUISystem

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `Game.UI.UISystemBase`  

## Fields

- `private Game.Prefabs.PrefabSystem m_PrefabSystem`  
- `private Game.Audio.Radio.Radio m_Radio`  
- `private Game.UI.InGame.GamePanelUISystem m_GamePanelUISystem`  
- `private Game.Rendering.CameraUpdateSystem m_CameraUpdateSystem`  
- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_PausedBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_MutedBinding`  
- `private Colossal.UI.Binding.ValueBinding<System.Boolean> m_SkipAds`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.Audio.Radio.Radio+RadioNetwork[]> m_NetworksBinding`  
- `private Colossal.UI.Binding.GetterValueBinding<Game.Audio.Radio.Radio+RuntimeRadioChannel[]> m_StationsBinding`  
- `private Colossal.UI.Binding.ValueBinding<Game.UI.InGame.RadioUISystem+ClipInfo> m_CurrentSegmentBinding`  
- `private Colossal.UI.Binding.EventBinding m_SegmentChangedBinding`  
- `private System.Collections.Generic.Dictionary<System.String, System.String> m_LastSelectedStations`  
- `private Game.UI.Localization.CachedLocalizedStringBuilder<System.String> m_EmergencyMessages`  
- `private static const System.String kGroup`  

## Constructors

- `public RadioUISystem()`  

## Methods

- `private <OnCreate>b__14_2() : System.Boolean`  
- `private <OnCreate>b__14_3() : System.Boolean`  
- `private <OnCreate>b__14_4() : Unity.Entities.Entity`  
- `private FocusEmergency() : System.Void`  
- `private GetClipInfo(Game.Audio.Radio.Radio radio, Colossal.IO.AssetDatabase.AudioAsset asset) : Game.UI.InGame.RadioUISystem+ClipInfo`  
- `private GetCurrentClipInfo() : Game.UI.InGame.RadioUISystem+ClipInfo`  
- `private GetMetaType(Game.Audio.Radio.Radio+SegmentType type) : Colossal.IO.AssetDatabase.AudioAsset+Metatag`  
- `private OnClipChanged(Game.Audio.Radio.Radio radio, Colossal.IO.AssetDatabase.AudioAsset asset) : System.Void`  
- `protected virtual OnCreate() : System.Void`  
- `protected virtual OnDestroy() : System.Void`  
- `private OnProgramChanged(Game.Audio.Radio.Radio radio) : System.Void`  
- `private OnRadioReloaded(Game.Audio.Radio.Radio radio) : System.Void`  
- `private PlayNext() : System.Void`  
- `private PlayPrevious() : System.Void`  
- `private SelectNetwork(System.String name) : System.Void`  
- `private SelectStation(System.String name) : System.Void`  
- `private SetMuted(System.Boolean muted) : System.Void`  
- `private SetPaused(System.Boolean paused) : System.Void`  
- `private SetSkipAds(System.Boolean skipAds) : System.Void`  
- `private SetVolume(System.Single volume) : System.Void`  
- `private WriteEmergencyMessage(Colossal.UI.Binding.IJsonWriter writer, Unity.Entities.Entity entity) : System.Void`  

## Nested types

- `Game.UI.InGame.RadioUISystem+ClipInfo`  
- `Game.UI.InGame.RadioUISystem+<>c`  

