# Game.Settings.GraphicsSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.GlobalQualitySettings`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`, `SettingsUIGroupOrder`, `SettingsUIShowGroupName`  

## Code

```csharp
public class GraphicsSettings : Game.Settings.GlobalQualitySettings, System.IEquatable<Game.Settings.Setting>
{
    private System.Int32 m_resolutionItemsVersion;
    private System.Boolean m_ShowAllResolutions;
    private Game.Settings.ScreenResolution m_Resolution;
    private System.Int32 <displayIndex>k__BackingField;
    private Game.Settings.DisplayMode <displayMode>k__BackingField;
    private System.Boolean <vSync>k__BackingField;
    private System.Int32 <maxFrameLatency>k__BackingField;
    private Game.Settings.GraphicsSettings+CursorMode <cursorMode>k__BackingField;
    private Game.Settings.GraphicsSettings+DepthOfFieldMode <depthOfFieldMode>k__BackingField;
    private System.Single <tiltShiftNearStart>k__BackingField;
    private System.Single <tiltShiftNearEnd>k__BackingField;
    private System.Single <tiltShiftFarStart>k__BackingField;
    private System.Single <tiltShiftFarEnd>k__BackingField;
    private Game.Settings.GraphicsSettings+DlssQuality <dlssQuality>k__BackingField;
    private System.Int32 m_DlssQuality;
    private static UnityEngine.Camera m_Camera;
    private static UnityEngine.Rendering.Volume m_VolumeOverride;
    public static const System.String kName;
    public static const System.String kMainGroup;
    public static const System.String kDepthOfFieldGroup;
    public static const System.String kQualityGroup;
    public static const System.String kUpscalersGroup;
    private static const System.Int32 kDisplayIndexNotSelected;

    public System.Int32 currentDisplayIndex { get; set; }
    public System.Int32 displayIndex { get; set; }
    public System.Boolean showAllResolutions { get; set; }
    public Game.Settings.ScreenResolution resolution { get; set; }
    public Game.Settings.DisplayMode displayMode { get; set; }
    public System.Boolean vSync { get; set; }
    public System.Int32 maxFrameLatency { get; set; }
    public Game.Settings.GraphicsSettings+CursorMode cursorMode { get; set; }
    public Game.Settings.GraphicsSettings+DepthOfFieldMode depthOfFieldMode { get; set; }
    public System.Single tiltShiftNearStart { get; set; }
    public System.Single tiltShiftNearEnd { get; set; }
    public System.Single tiltShiftFarStart { get; set; }
    public System.Single tiltShiftFarEnd { get; set; }
    public Game.Settings.GraphicsSettings+DlssQuality dlssQuality { get; set; }
    public System.Boolean isDlssActive { get; }
    public System.Boolean isFsr2Active { get; }
    private System.Boolean isDLSSDisabled { private get; }
    private System.Boolean isFSRDisabled { private get; }

    public GraphicsSettings();

    internal virtual System.Void AddToPageData(Game.UI.Menu.AutomaticSettings+SettingPageData pageData);
    public virtual System.Void Apply();
    private System.Void ApplyDLSSAutoSettings(UnityEngine.Camera camera);
    public System.Void ApplyResolution();
    private System.Void CleanupVolumeOverride();
    private System.Void CreateVolumeOverride();
    private System.Int32 GetActiveDisplayIndex(System.Collections.Generic.IReadOnlyList`1[[UnityEngine.DisplayInfo, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& displayInfos);
    public static Game.UI.Widgets.DropdownItem<System.Int32>[] GetDisplayIndexValues();
    public virtual Game.UI.Menu.AutomaticSettings+SettingPageData GetPageData(System.String id, System.Boolean addPrefix);
    public System.Int32 GetResolutionItemsVersion();
    public static Game.UI.Widgets.DropdownItem<Game.Settings.ScreenResolution>[] GetScreenResolutionValues();
    public T GetVolumeOverride<T>();
    private System.Boolean IsDLSSDectected();
    public System.Boolean IsTiltShiftDisabled();
    private System.Collections.IEnumerator MoveToDisplay(UnityEngine.DisplayInfo display);
    public System.Void OnResolutionItemsNeedRebuild(System.Boolean value);
    public System.Void OnSetDisplayIndex(System.Int32 index);
    public System.Void OnSetDisplayMode(Game.Settings.DisplayMode mode);
    public System.Void OnSetResolution(Game.Settings.ScreenResolution resolution);
    public virtual System.Void SetDefaults();
    private UnityEngine.NVIDIA.DLSSQuality ToDlssQuality(Game.Settings.GraphicsSettings+DlssQuality dlssQuality);
}
```


## Fields

- `private System.Int32 m_resolutionItemsVersion`  

```csharp
private System.Int32 m_resolutionItemsVersion;
```

- `private System.Boolean m_ShowAllResolutions`  

```csharp
private System.Boolean m_ShowAllResolutions;
```

- `private Game.Settings.ScreenResolution m_Resolution`  

```csharp
private Game.Settings.ScreenResolution m_Resolution;
```

- `private System.Int32 <displayIndex>k__BackingField`  

```csharp
private System.Int32 <displayIndex>k__BackingField;
```

- `private Game.Settings.DisplayMode <displayMode>k__BackingField`  

```csharp
private Game.Settings.DisplayMode <displayMode>k__BackingField;
```

- `private System.Boolean <vSync>k__BackingField`  

```csharp
private System.Boolean <vSync>k__BackingField;
```

- `private System.Int32 <maxFrameLatency>k__BackingField`  

```csharp
private System.Int32 <maxFrameLatency>k__BackingField;
```

- `private Game.Settings.GraphicsSettings+CursorMode <cursorMode>k__BackingField`  

```csharp
private Game.Settings.GraphicsSettings+CursorMode <cursorMode>k__BackingField;
```

- `private Game.Settings.GraphicsSettings+DepthOfFieldMode <depthOfFieldMode>k__BackingField`  

```csharp
private Game.Settings.GraphicsSettings+DepthOfFieldMode <depthOfFieldMode>k__BackingField;
```

- `private System.Single <tiltShiftNearStart>k__BackingField`  

```csharp
private System.Single <tiltShiftNearStart>k__BackingField;
```

- `private System.Single <tiltShiftNearEnd>k__BackingField`  

```csharp
private System.Single <tiltShiftNearEnd>k__BackingField;
```

- `private System.Single <tiltShiftFarStart>k__BackingField`  

```csharp
private System.Single <tiltShiftFarStart>k__BackingField;
```

- `private System.Single <tiltShiftFarEnd>k__BackingField`  

```csharp
private System.Single <tiltShiftFarEnd>k__BackingField;
```

- `private Game.Settings.GraphicsSettings+DlssQuality <dlssQuality>k__BackingField`  

```csharp
private Game.Settings.GraphicsSettings+DlssQuality <dlssQuality>k__BackingField;
```

- `private System.Int32 m_DlssQuality`  

```csharp
private System.Int32 m_DlssQuality;
```

- `private static UnityEngine.Camera m_Camera`  

```csharp
private static UnityEngine.Camera m_Camera;
```

- `private static UnityEngine.Rendering.Volume m_VolumeOverride`  

```csharp
private static UnityEngine.Rendering.Volume m_VolumeOverride;
```

- `public static const System.String kName`  

```csharp
public static const System.String kName;
```

- `public static const System.String kMainGroup`  

```csharp
public static const System.String kMainGroup;
```

- `public static const System.String kDepthOfFieldGroup`  

```csharp
public static const System.String kDepthOfFieldGroup;
```

- `public static const System.String kQualityGroup`  

```csharp
public static const System.String kQualityGroup;
```

- `public static const System.String kUpscalersGroup`  

```csharp
public static const System.String kUpscalersGroup;
```

- `private static const System.Int32 kDisplayIndexNotSelected`  

```csharp
private static const System.Int32 kDisplayIndexNotSelected;
```


## Properties

- `public System.Int32 currentDisplayIndex { get; set }`  

```csharp
public System.Int32 currentDisplayIndex { get; set; }
```

- `public System.Int32 displayIndex { get; set }`  

```csharp
public System.Int32 displayIndex { get; set; }
```

- `public System.Boolean showAllResolutions { get; set }`  

```csharp
public System.Boolean showAllResolutions { get; set; }
```

- `public Game.Settings.ScreenResolution resolution { get; set }`  

```csharp
public Game.Settings.ScreenResolution resolution { get; set; }
```

- `public Game.Settings.DisplayMode displayMode { get; set }`  

```csharp
public Game.Settings.DisplayMode displayMode { get; set; }
```

- `public System.Boolean vSync { get; set }`  

```csharp
public System.Boolean vSync { get; set; }
```

- `public System.Int32 maxFrameLatency { get; set }`  

```csharp
public System.Int32 maxFrameLatency { get; set; }
```

- `public Game.Settings.GraphicsSettings+CursorMode cursorMode { get; set }`  

```csharp
public Game.Settings.GraphicsSettings+CursorMode cursorMode { get; set; }
```

- `public Game.Settings.GraphicsSettings+DepthOfFieldMode depthOfFieldMode { get; set }`  

```csharp
public Game.Settings.GraphicsSettings+DepthOfFieldMode depthOfFieldMode { get; set; }
```

- `public System.Single tiltShiftNearStart { get; set }`  

```csharp
public System.Single tiltShiftNearStart { get; set; }
```

- `public System.Single tiltShiftNearEnd { get; set }`  

```csharp
public System.Single tiltShiftNearEnd { get; set; }
```

- `public System.Single tiltShiftFarStart { get; set }`  

```csharp
public System.Single tiltShiftFarStart { get; set; }
```

- `public System.Single tiltShiftFarEnd { get; set }`  

```csharp
public System.Single tiltShiftFarEnd { get; set; }
```

- `public Game.Settings.GraphicsSettings+DlssQuality dlssQuality { get; set }`  

```csharp
public Game.Settings.GraphicsSettings+DlssQuality dlssQuality { get; set; }
```

- `public System.Boolean isDlssActive { get }`  

```csharp
public System.Boolean isDlssActive { get; }
```

- `public System.Boolean isFsr2Active { get }`  

```csharp
public System.Boolean isFsr2Active { get; }
```

- `private System.Boolean isDLSSDisabled { private get }`  

```csharp
private System.Boolean isDLSSDisabled { private get; }
```

- `private System.Boolean isFSRDisabled { private get }`  

```csharp
private System.Boolean isFSRDisabled { private get; }
```


## Constructors

- `public GraphicsSettings()`  

```csharp
public GraphicsSettings();
```


## Methods

- `internal virtual AddToPageData(Game.UI.Menu.AutomaticSettings+SettingPageData pageData) : System.Void`  

```csharp
internal virtual System.Void AddToPageData(Game.UI.Menu.AutomaticSettings+SettingPageData pageData);
```

- `public virtual Apply() : System.Void`  

```csharp
public virtual System.Void Apply();
```

- `private ApplyDLSSAutoSettings(UnityEngine.Camera camera) : System.Void`  

```csharp
private System.Void ApplyDLSSAutoSettings(UnityEngine.Camera camera);
```

- `public ApplyResolution() : System.Void`  

```csharp
public System.Void ApplyResolution();
```

- `private CleanupVolumeOverride() : System.Void`  

```csharp
private System.Void CleanupVolumeOverride();
```

- `private CreateVolumeOverride() : System.Void`  

```csharp
private System.Void CreateVolumeOverride();
```

- `private GetActiveDisplayIndex(System.Collections.Generic.IReadOnlyList`1[[UnityEngine.DisplayInfo, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& displayInfos) : System.Int32`  

```csharp
private System.Int32 GetActiveDisplayIndex(System.Collections.Generic.IReadOnlyList`1[[UnityEngine.DisplayInfo, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& displayInfos);
```

- `public static GetDisplayIndexValues() : Game.UI.Widgets.DropdownItem<System.Int32>[]`  

```csharp
public static Game.UI.Widgets.DropdownItem<System.Int32>[] GetDisplayIndexValues();
```

- `public virtual GetPageData(System.String id, System.Boolean addPrefix) : Game.UI.Menu.AutomaticSettings+SettingPageData`  

```csharp
public virtual Game.UI.Menu.AutomaticSettings+SettingPageData GetPageData(System.String id, System.Boolean addPrefix);
```

- `public GetResolutionItemsVersion() : System.Int32`  

```csharp
public System.Int32 GetResolutionItemsVersion();
```

- `public static GetScreenResolutionValues() : Game.UI.Widgets.DropdownItem<Game.Settings.ScreenResolution>[]`  

```csharp
public static Game.UI.Widgets.DropdownItem<Game.Settings.ScreenResolution>[] GetScreenResolutionValues();
```

- `public GetVolumeOverride<T>() : T`  

```csharp
public T GetVolumeOverride<T>();
```

- `private IsDLSSDectected() : System.Boolean`  

```csharp
private System.Boolean IsDLSSDectected();
```

- `public IsTiltShiftDisabled() : System.Boolean`  

```csharp
public System.Boolean IsTiltShiftDisabled();
```

- `private MoveToDisplay(UnityEngine.DisplayInfo display) : System.Collections.IEnumerator`  

```csharp
private System.Collections.IEnumerator MoveToDisplay(UnityEngine.DisplayInfo display);
```

- `public OnResolutionItemsNeedRebuild(System.Boolean value) : System.Void`  

```csharp
public System.Void OnResolutionItemsNeedRebuild(System.Boolean value);
```

- `public OnSetDisplayIndex(System.Int32 index) : System.Void`  

```csharp
public System.Void OnSetDisplayIndex(System.Int32 index);
```

- `public OnSetDisplayMode(Game.Settings.DisplayMode mode) : System.Void`  

```csharp
public System.Void OnSetDisplayMode(Game.Settings.DisplayMode mode);
```

- `public OnSetResolution(Game.Settings.ScreenResolution resolution) : System.Void`  

```csharp
public System.Void OnSetResolution(Game.Settings.ScreenResolution resolution);
```

- `public virtual SetDefaults() : System.Void`  

```csharp
public virtual System.Void SetDefaults();
```

- `private ToDlssQuality(Game.Settings.GraphicsSettings+DlssQuality dlssQuality) : UnityEngine.NVIDIA.DLSSQuality`  

```csharp
private UnityEngine.NVIDIA.DLSSQuality ToDlssQuality(Game.Settings.GraphicsSettings+DlssQuality dlssQuality);
```


## Nested types

- `Game.Settings.GraphicsSettings+DepthOfFieldMode`  
- `Game.Settings.GraphicsSettings+CursorMode`  
- `Game.Settings.GraphicsSettings+DlssQuality`  
- `Game.Settings.GraphicsSettings+<>c`  
- `Game.Settings.GraphicsSettings+<MoveToDisplay>d__82`  

