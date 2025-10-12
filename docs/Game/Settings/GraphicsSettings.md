# Game.Settings.GraphicsSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.GlobalQualitySettings`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`, `SettingsUIGroupOrder`, `SettingsUIShowGroupName`  

## Fields

- `private System.Int32 m_resolutionItemsVersion`  
- `private System.Boolean m_ShowAllResolutions`  
- `private Game.Settings.ScreenResolution m_Resolution`  
- `private System.Int32 <displayIndex>k__BackingField`  
- `private Game.Settings.DisplayMode <displayMode>k__BackingField`  
- `private System.Boolean <vSync>k__BackingField`  
- `private System.Int32 <maxFrameLatency>k__BackingField`  
- `private Game.Settings.GraphicsSettings+CursorMode <cursorMode>k__BackingField`  
- `private Game.Settings.GraphicsSettings+DepthOfFieldMode <depthOfFieldMode>k__BackingField`  
- `private System.Single <tiltShiftNearStart>k__BackingField`  
- `private System.Single <tiltShiftNearEnd>k__BackingField`  
- `private System.Single <tiltShiftFarStart>k__BackingField`  
- `private System.Single <tiltShiftFarEnd>k__BackingField`  
- `private Game.Settings.GraphicsSettings+DlssQuality <dlssQuality>k__BackingField`  
- `private System.Int32 m_DlssQuality`  
- `private static UnityEngine.Camera m_Camera`  
- `private static UnityEngine.Rendering.Volume m_VolumeOverride`  
- `public static const System.String kName`  
- `public static const System.String kMainGroup`  
- `public static const System.String kDepthOfFieldGroup`  
- `public static const System.String kQualityGroup`  
- `public static const System.String kUpscalersGroup`  
- `private static const System.Int32 kDisplayIndexNotSelected`  

## Properties

- `public System.Int32 currentDisplayIndex { get; set }`  
- `public System.Int32 displayIndex { get; set }`  
- `public System.Boolean showAllResolutions { get; set }`  
- `public Game.Settings.ScreenResolution resolution { get; set }`  
- `public Game.Settings.DisplayMode displayMode { get; set }`  
- `public System.Boolean vSync { get; set }`  
- `public System.Int32 maxFrameLatency { get; set }`  
- `public Game.Settings.GraphicsSettings+CursorMode cursorMode { get; set }`  
- `public Game.Settings.GraphicsSettings+DepthOfFieldMode depthOfFieldMode { get; set }`  
- `public System.Single tiltShiftNearStart { get; set }`  
- `public System.Single tiltShiftNearEnd { get; set }`  
- `public System.Single tiltShiftFarStart { get; set }`  
- `public System.Single tiltShiftFarEnd { get; set }`  
- `public Game.Settings.GraphicsSettings+DlssQuality dlssQuality { get; set }`  
- `public System.Boolean isDlssActive { get }`  
- `public System.Boolean isFsr2Active { get }`  
- `private System.Boolean isDLSSDisabled { private get }`  
- `private System.Boolean isFSRDisabled { private get }`  

## Constructors

- `public GraphicsSettings()`  

## Methods

- `internal virtual AddToPageData(Game.UI.Menu.AutomaticSettings+SettingPageData pageData) : System.Void`  
- `public virtual Apply() : System.Void`  
- `private ApplyDLSSAutoSettings(UnityEngine.Camera camera) : System.Void`  
- `public ApplyResolution() : System.Void`  
- `private CleanupVolumeOverride() : System.Void`  
- `private CreateVolumeOverride() : System.Void`  
- `private GetActiveDisplayIndex(System.Collections.Generic.IReadOnlyList`1[[UnityEngine.DisplayInfo, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& displayInfos) : System.Int32`  
- `public static GetDisplayIndexValues() : Game.UI.Widgets.DropdownItem<System.Int32>[]`  
- `public virtual GetPageData(System.String id, System.Boolean addPrefix) : Game.UI.Menu.AutomaticSettings+SettingPageData`  
- `public GetResolutionItemsVersion() : System.Int32`  
- `public static GetScreenResolutionValues() : Game.UI.Widgets.DropdownItem<Game.Settings.ScreenResolution>[]`  
- `public GetVolumeOverride<T>() : T`  
- `private IsDLSSDectected() : System.Boolean`  
- `public IsTiltShiftDisabled() : System.Boolean`  
- `private MoveToDisplay(UnityEngine.DisplayInfo display) : System.Collections.IEnumerator`  
- `public OnResolutionItemsNeedRebuild(System.Boolean value) : System.Void`  
- `public OnSetDisplayIndex(System.Int32 index) : System.Void`  
- `public OnSetDisplayMode(Game.Settings.DisplayMode mode) : System.Void`  
- `public OnSetResolution(Game.Settings.ScreenResolution resolution) : System.Void`  
- `public virtual SetDefaults() : System.Void`  
- `private ToDlssQuality(Game.Settings.GraphicsSettings+DlssQuality dlssQuality) : UnityEngine.NVIDIA.DLSSQuality`  

## Nested types

- `Game.Settings.GraphicsSettings+DepthOfFieldMode`  
- `Game.Settings.GraphicsSettings+CursorMode`  
- `Game.Settings.GraphicsSettings+DlssQuality`  
- `Game.Settings.GraphicsSettings+<>c`  
- `Game.Settings.GraphicsSettings+<MoveToDisplay>d__82`  

