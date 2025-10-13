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
public GraphicsSettings()
	{
		CreateVolumeOverride();
		AddQualitySetting(new DynamicResolutionScaleSettings(Level.High));
		AddQualitySetting(new AntiAliasingQualitySettings(Level.High));
		AddQualitySetting(new CloudsQualitySettings(Level.High, m_VolumeOverride.profileRef));
		AddQualitySetting(new FogQualitySettings(Level.Low, m_VolumeOverride.profileRef));
		AddQualitySetting(new VolumetricsQualitySettings(Level.High, m_VolumeOverride.profileRef));
		AddQualitySetting(new SSAOQualitySettings(Level.High, m_VolumeOverride.profileRef));
		AddQualitySetting(new SSGIQualitySettings(Level.High, m_VolumeOverride.profileRef));
		AddQualitySetting(new SSRQualitySettings(Level.High, m_VolumeOverride.profileRef));
		AddQualitySetting(new DepthOfFieldQualitySettings(Level.High, m_VolumeOverride.profileRef));
		AddQualitySetting(new MotionBlurQualitySettings(Level.High, m_VolumeOverride.profileRef));
		AddQualitySetting(new ShadowsQualitySettings(Level.High, m_VolumeOverride.profileRef));
		AddQualitySetting(new TerrainQualitySettings(Level.High, m_VolumeOverride.profileRef));
		AddQualitySetting(new WaterQualitySettings(Level.High, m_VolumeOverride.profileRef));
		AddQualitySetting(new LevelOfDetailQualitySettings(Level.High));
		AddQualitySetting(new AnimationQualitySettings(Level.High));
		AddQualitySetting(new TextureQualitySettings(Level.High));
		SetDefaults();
	}
```


## Methods

- `internal virtual AddToPageData(Game.UI.Menu.AutomaticSettings+SettingPageData pageData) : System.Void`  

```csharp
internal override void AddToPageData(AutomaticSettings.SettingPageData pageData)
	{
	}
```

- `public virtual Apply() : System.Void`  

```csharp
public override void Apply()
	{
		base.Apply();
		ApplyResolution();
		QualitySettings.vSyncCount = (vSync ? 1 : 0);
		QualitySettings.maxQueuedFrames = maxFrameLatency;
		Cursor.lockState = cursorMode.ToUnityCursorMode();
		if (TryGetGameplayCamera(ref m_Camera))
		{
			ApplyDLSSAutoSettings(m_Camera);
		}
		StringBuilder stringBuilder = new StringBuilder();
		foreach (QualitySetting item in EnumerateQualitySettings())
		{
			stringBuilder.AppendFormat("{0}: {1}", item.GetType().Name, item.GetLevel());
			if (item != base.lastSetting)
			{
				stringBuilder.Append(" - ");
			}
			item.Apply();
		}
		Setting.log.InfoFormat("Current resolution: {1} {2} - Current quality settings: {0}", stringBuilder.ToString(), resolution, displayMode);
	}
```

- `private ApplyDLSSAutoSettings(UnityEngine.Camera camera) : System.Void`  

```csharp
private void ApplyDLSSAutoSettings(Camera camera)
	{
		m_DlssQuality = -1;
		if (IsDLSSDectected())
		{
			DlssQuality dlssQuality = this.dlssQuality;
			if (this.dlssQuality == DlssQuality.Auto)
			{
				ScreenResolution currentResolution = ScreenHelper.currentResolution;
				long num = currentResolution.width * currentResolution.height;
				dlssQuality = ((num >= 2073600) ? ((num <= 3686400) ? DlssQuality.MaximumQuality : ((num > 8294400) ? DlssQuality.UltraPerformance : DlssQuality.MaximumPerformance)) : DlssQuality.Off);
			}
			if (dlssQuality != DlssQuality.Off)
			{
				m_DlssQuality = (int)ToDlssQuality(dlssQuality);
			}
		}
		bool flag = m_DlssQuality >= 0;
		HDAdditionalCameraData component = camera.GetComponent<HDAdditionalCameraData>();
		component.allowDeepLearningSuperSampling = flag;
		component.deepLearningSuperSamplingUseCustomQualitySettings = true;
		if (flag)
		{
			component.deepLearningSuperSamplingQuality = (uint)m_DlssQuality;
		}
	}
```

- `public ApplyResolution() : System.Void`  

```csharp
public void ApplyResolution()
	{
		IReadOnlyList<DisplayInfo> displayInfos;
		int activeDisplayIndex = GetActiveDisplayIndex(out displayInfos);
		if (displayIndex < 0 || displayIndex >= displayInfos.Count)
		{
			displayIndex = 0;
		}
		if (activeDisplayIndex != displayIndex)
		{
			Setting.log.InfoFormat("Switching from display {0} to {1}", activeDisplayIndex, displayIndex);
			GameManager.instance.StartCoroutine(MoveToDisplay(displayInfos[displayIndex]));
		}
		ScreenResolution currentResolution = ScreenHelper.currentResolution;
		DisplayMode currentDisplayMode = ScreenHelper.currentDisplayMode;
		if (currentResolution != resolution || currentDisplayMode != displayMode)
		{
			Setting.log.InfoFormat("Applying resolution: {0} {1}", resolution, displayMode);
			if (resolution.isValid)
			{
				Screen.SetResolution(resolution.width, resolution.height, ScreenHelper.GetFullscreenMode(displayMode), resolution.refreshRate);
			}
			else
			{
				Setting.log.ErrorFormat("Resolution {0} {1} is invalid", resolution, displayMode);
			}
		}
	}
```

- `private CleanupVolumeOverride() : System.Void`  

```csharp
private void CleanupVolumeOverride()
	{
		VolumeHelper.DestroyVolume(m_VolumeOverride);
	}
```

- `private CreateVolumeOverride() : System.Void`  

```csharp
private void CreateVolumeOverride()
	{
		if (m_VolumeOverride == null)
		{
			m_VolumeOverride = VolumeHelper.CreateVolume("VolumeQualitySettingsOverride", 100);
		}
	}
```

- `private GetActiveDisplayIndex(System.Collections.Generic.IReadOnlyList`1[[UnityEngine.DisplayInfo, UnityEngine.CoreModule, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null]]& displayInfos) : System.Int32`  

```csharp
private int GetActiveDisplayIndex(out IReadOnlyList<DisplayInfo> displayInfos)
	{
		List<DisplayInfo> list = new List<DisplayInfo>();
		Screen.GetDisplayLayout(list);
		displayInfos = list;
		for (int i = 0; i < list.Count; i++)
		{
			if (list[i].Equals(Screen.mainWindowDisplayInfo))
			{
				return i;
			}
		}
		return 0;
	}
```

- `public static GetDisplayIndexValues() : Game.UI.Widgets.DropdownItem<System.Int32>[]`  

```csharp
[Preserve]
	public static DropdownItem<int>[] GetDisplayIndexValues()
	{
		List<DisplayInfo> list = new List<DisplayInfo>();
		Screen.GetDisplayLayout(list);
		List<DropdownItem<int>> list2 = new List<DropdownItem<int>>(list.Count);
		for (int i = 0; i < list.Count; i++)
		{
			list2.Add(new DropdownItem<int>
			{
				value = i,
				displayName = ((!string.IsNullOrEmpty(list[i].name)) ? LocalizedString.Value($"{i}: {list[i].name}") : new LocalizedString("Options.DISPLAY_INDEX_FORMAT", null, new Dictionary<string, ILocElement> { 
				{
					"INDEX",
					LocalizedString.Value(i.ToString())
				} }))
			});
		}
		return list2.ToArray();
	}
```

- `public virtual GetPageData(System.String id, System.Boolean addPrefix) : Game.UI.Menu.AutomaticSettings+SettingPageData`  

```csharp
public override AutomaticSettings.SettingPageData GetPageData(string id, bool addPrefix)
	{
		AutomaticSettings.SettingPageData settingPageData = AutomaticSettings.FillSettingsPage(this, id, addPrefix);
		AutomaticSettings.ManualProperty property = new AutomaticSettings.ManualProperty(GetType(), typeof(Level), "Level")
		{
			canRead = true,
			canWrite = true,
			getter = (object settings) => ((GraphicsSettings)settings).GetLevel(),
			setter = delegate(object settings, object value)
			{
				((GraphicsSettings)settings).SetLevel((Level)value);
			},
			attributes = 
			{
				(Attribute)new SettingsUIDropdownAttribute(typeof(QualitySetting), "GetQualityValues"),
				(Attribute)new SettingsUIPathAttribute("GraphicsSettings.globalQuality"),
				(Attribute)new SettingsUIDisplayNameAttribute("GraphicsSettings.globalQuality")
			}
		};
		AutomaticSettings.SettingItemData item = new AutomaticSettings.SettingItemData(AutomaticSettings.WidgetType.AdvancedEnumDropdown, this, property, settingPageData.prefix)
		{
			isAdvanced = false,
			simpleGroup = "Quality",
			advancedGroup = "Quality"
		};
		settingPageData["General"].AddItem(item);
		foreach (QualitySetting qualitySetting in base.qualitySettings)
		{
			qualitySetting.AddToPageData(settingPageData);
		}
		return settingPageData;
	}
```

- `public GetResolutionItemsVersion() : System.Int32`  

```csharp
public int GetResolutionItemsVersion()
	{
		return m_resolutionItemsVersion;
	}
```

- `public static GetScreenResolutionValues() : Game.UI.Widgets.DropdownItem<Game.Settings.ScreenResolution>[]`  

```csharp
[Preserve]
	public static DropdownItem<ScreenResolution>[] GetScreenResolutionValues()
	{
		bool num = SharedSettings.instance.graphics.showAllResolutions;
		ScreenResolution[] availableResolutions = ScreenHelper.GetAvailableResolutions(num);
		List<DropdownItem<ScreenResolution>> list = new List<DropdownItem<ScreenResolution>>(availableResolutions.Length);
		string unit = (num ? "screenFrequency" : "integer");
		ScreenResolution[] array = availableResolutions;
		for (int i = 0; i < array.Length; i++)
		{
			ScreenResolution value = array[i];
			DropdownItem<ScreenResolution> obj = new DropdownItem<ScreenResolution>
			{
				value = value
			};
			Dictionary<string, ILocElement> dictionary = new Dictionary<string, ILocElement>();
			int width = value.width;
			dictionary.Add("WIDTH", LocalizedString.Value(width.ToString("D")));
			width = value.height;
			dictionary.Add("HEIGHT", LocalizedString.Value(width.ToString("D")));
			RefreshRate refreshRate = value.refreshRate;
			dictionary.Add("REFRESH_RATE", new LocalizedNumber<double>(refreshRate.value, unit));
			obj.displayName = new LocalizedString("Options.SCREEN_RESOLUTION_FORMAT", null, dictionary);
			list.Add(obj);
		}
		return list.ToArray();
	}
```

- `public GetVolumeOverride<T>() : T`  

```csharp
public T GetVolumeOverride<T>();
```

- `private IsDLSSDectected() : System.Boolean`  

```csharp
private bool IsDLSSDectected()
	{
		return HDDynamicResolutionPlatformCapabilities.DLSSDetected;
	}
```

- `public IsTiltShiftDisabled() : System.Boolean`  

```csharp
public bool IsTiltShiftDisabled()
	{
		return depthOfFieldMode != DepthOfFieldMode.TiltShift;
	}
```

- `private MoveToDisplay(UnityEngine.DisplayInfo display) : System.Collections.IEnumerator`  

```csharp
private IEnumerator MoveToDisplay(DisplayInfo display)
	{
		yield return Screen.MoveMainWindowTo(in display, Screen.mainWindowPosition);
		ScreenHelper.RebuildResolutions();
		OnResolutionItemsNeedRebuild(value: false);
		resolution = resolution;
	}
```

- `public OnResolutionItemsNeedRebuild(System.Boolean value) : System.Void`  

```csharp
public void OnResolutionItemsNeedRebuild(bool value)
	{
		m_resolutionItemsVersion++;
	}
```

- `public OnSetDisplayIndex(System.Int32 index) : System.Void`  

```csharp
public void OnSetDisplayIndex(int index)
	{
		if (displayMode == DisplayMode.Fullscreen)
		{
			World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<OptionsUISystem>().ShowDisplayConfirmation();
		}
	}
```

- `public OnSetDisplayMode(Game.Settings.DisplayMode mode) : System.Void`  

```csharp
public void OnSetDisplayMode(DisplayMode mode)
	{
		if (displayMode != DisplayMode.Fullscreen && mode == DisplayMode.Fullscreen)
		{
			World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<OptionsUISystem>().ShowDisplayConfirmation();
		}
	}
```

- `public OnSetResolution(Game.Settings.ScreenResolution resolution) : System.Void`  

```csharp
public void OnSetResolution(ScreenResolution resolution)
	{
		if (displayMode == DisplayMode.Fullscreen)
		{
			World.DefaultGameObjectInjectionWorld.GetOrCreateSystemManaged<OptionsUISystem>().ShowDisplayConfirmation();
		}
	}
```

- `public virtual SetDefaults() : System.Void`  

```csharp
public override void SetDefaults()
	{
		showAllResolutions = false;
		displayIndex = -1;
		resolution = ScreenHelper.currentResolution;
		displayMode = ScreenHelper.currentDisplayMode;
		depthOfFieldMode = DepthOfFieldMode.Physical;
		vSync = false;
		tiltShiftNearStart = 0.5f;
		tiltShiftNearEnd = 0.25f;
		tiltShiftFarStart = 0.25f;
		tiltShiftFarEnd = 0.5f;
		maxFrameLatency = QualitySettings.maxQueuedFrames;
		cursorMode = CursorMode.ConfinedToWindow;
		dlssQuality = (IsDLSSDectected() ? DlssQuality.Auto : DlssQuality.Off);
		base.SetDefaults();
	}
```

- `private ToDlssQuality(Game.Settings.GraphicsSettings+DlssQuality dlssQuality) : UnityEngine.NVIDIA.DLSSQuality`  

```csharp
private DLSSQuality ToDlssQuality(DlssQuality dlssQuality)
	{
		return dlssQuality switch
		{
			DlssQuality.MaximumQuality => DLSSQuality.MaximumQuality, 
			DlssQuality.Balanced => DLSSQuality.Balanced, 
			DlssQuality.MaximumPerformance => DLSSQuality.MaximumPerformance, 
			DlssQuality.UltraPerformance => DLSSQuality.UltraPerformance, 
			_ => throw new Exception($"Unsupported upscaler quality conversion {dlssQuality}"), 
		};
	}
```


## Nested types

- `Game.Settings.GraphicsSettings+DepthOfFieldMode`  
- `Game.Settings.GraphicsSettings+CursorMode`  
- `Game.Settings.GraphicsSettings+DlssQuality`  
- `Game.Settings.GraphicsSettings+<>c`  
- `Game.Settings.GraphicsSettings+<MoveToDisplay>d__82`  

