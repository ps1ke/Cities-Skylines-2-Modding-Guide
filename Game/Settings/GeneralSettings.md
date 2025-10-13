# Game.Settings.GeneralSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`  

## Code

```csharp
public class GeneralSettings : Game.Settings.Setting, System.IEquatable<Game.Settings.Setting>
{
    private Colossal.IO.AssetDatabase.AssetDatabase+AutoReloadMode m_AssetDatabaseAutoReloadMode;
    private Game.Simulation.SimulationSystem+PerformancePreference m_PerformancePreference;
    private Game.Settings.GeneralSettings+FPSMode <fpsMode>k__BackingField;
    private System.Boolean <autoSave>k__BackingField;
    private Game.Settings.GeneralSettings+AutoSaveInterval <autoSaveInterval>k__BackingField;
    private Game.Settings.GeneralSettings+AutoSaveCount <autoSaveCount>k__BackingField;
    private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Manager;
    private System.Boolean m_OptionalTelemetryConsentFaulted;
    public static const System.String kName;

    public Colossal.IO.AssetDatabase.AssetDatabase+AutoReloadMode assetDatabaseAutoReloadMode { get; set; }
    public Game.Simulation.SimulationSystem+PerformancePreference performancePreference { get; set; }
    public Game.Settings.GeneralSettings+FPSMode fpsMode { get; set; }
    public System.Boolean autoSave { get; set; }
    public Game.Settings.GeneralSettings+AutoSaveInterval autoSaveInterval { get; set; }
    public Game.Settings.GeneralSettings+AutoSaveCount autoSaveCount { get; set; }
    public System.Boolean autoSaveNow { get; set; }
    public System.Boolean allowOptionalTelemetry { get; set; }
    public System.Boolean resetSettings { set; }

    public GeneralSettings();

    private System.Void <InitializePlatform>b__39_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
    public static System.Boolean AutoSaveEnabled();
    public static System.Boolean CanSave();
    private System.Boolean HideTelemetryConsentChoice();
    private System.Void InitializePlatform();
    public virtual System.Void SetDefaults();
    private System.Void SetTelemetryConsentChoice(System.Boolean allow);
    private System.Boolean TelemetryConsentFaulted();
}
```


## Fields

- `private Colossal.IO.AssetDatabase.AssetDatabase+AutoReloadMode m_AssetDatabaseAutoReloadMode`  

```csharp
private Colossal.IO.AssetDatabase.AssetDatabase+AutoReloadMode m_AssetDatabaseAutoReloadMode;
```

- `private Game.Simulation.SimulationSystem+PerformancePreference m_PerformancePreference`  

```csharp
private Game.Simulation.SimulationSystem+PerformancePreference m_PerformancePreference;
```

- `private Game.Settings.GeneralSettings+FPSMode <fpsMode>k__BackingField`  

```csharp
private Game.Settings.GeneralSettings+FPSMode <fpsMode>k__BackingField;
```

- `private System.Boolean <autoSave>k__BackingField`  

```csharp
private System.Boolean <autoSave>k__BackingField;
```

- `private Game.Settings.GeneralSettings+AutoSaveInterval <autoSaveInterval>k__BackingField`  

```csharp
private Game.Settings.GeneralSettings+AutoSaveInterval <autoSaveInterval>k__BackingField;
```

- `private Game.Settings.GeneralSettings+AutoSaveCount <autoSaveCount>k__BackingField`  

```csharp
private Game.Settings.GeneralSettings+AutoSaveCount <autoSaveCount>k__BackingField;
```

- `private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Manager`  

```csharp
private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Manager;
```

- `private System.Boolean m_OptionalTelemetryConsentFaulted`  

```csharp
private System.Boolean m_OptionalTelemetryConsentFaulted;
```

- `public static const System.String kName`  

```csharp
public static const System.String kName;
```


## Properties

- `public Colossal.IO.AssetDatabase.AssetDatabase+AutoReloadMode assetDatabaseAutoReloadMode { get; set }`  

```csharp
public Colossal.IO.AssetDatabase.AssetDatabase+AutoReloadMode assetDatabaseAutoReloadMode { get; set; }
```

- `public Game.Simulation.SimulationSystem+PerformancePreference performancePreference { get; set }`  

```csharp
public Game.Simulation.SimulationSystem+PerformancePreference performancePreference { get; set; }
```

- `public Game.Settings.GeneralSettings+FPSMode fpsMode { get; set }`  

```csharp
public Game.Settings.GeneralSettings+FPSMode fpsMode { get; set; }
```

- `public System.Boolean autoSave { get; set }`  

```csharp
public System.Boolean autoSave { get; set; }
```

- `public Game.Settings.GeneralSettings+AutoSaveInterval autoSaveInterval { get; set }`  

```csharp
public Game.Settings.GeneralSettings+AutoSaveInterval autoSaveInterval { get; set; }
```

- `public Game.Settings.GeneralSettings+AutoSaveCount autoSaveCount { get; set }`  

```csharp
public Game.Settings.GeneralSettings+AutoSaveCount autoSaveCount { get; set; }
```

- `public System.Boolean autoSaveNow { get; set }`  

```csharp
public System.Boolean autoSaveNow { get; set; }
```

- `public System.Boolean allowOptionalTelemetry { get; set }`  

```csharp
public System.Boolean allowOptionalTelemetry { get; set; }
```

- `public System.Boolean resetSettings { set }`  

```csharp
public System.Boolean resetSettings { set; }
```


## Constructors

- `public GeneralSettings()`  

```csharp
public GeneralSettings()
	{
		SetDefaults();
		InitializePlatform();
	}
```


## Methods

- `private <InitializePlatform>b__39_0(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  

```csharp
private System.Void <InitializePlatform>b__39_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
```

- `public static AutoSaveEnabled() : System.Boolean`  

```csharp
public static bool AutoSaveEnabled()
	{
		return !SharedSettings.instance.general.autoSave;
	}
```

- `public static CanSave() : System.Boolean`  

```csharp
public static bool CanSave()
	{
		return !GameManager.instance.gameMode.IsGameOrEditor();
	}
```

- `private HideTelemetryConsentChoice() : System.Boolean`  

```csharp
private bool HideTelemetryConsentChoice()
	{
		if (m_Manager != null)
		{
			return !m_Manager.IsTelemetryConsentPresentable();
		}
		return true;
	}
```

- `private InitializePlatform() : System.Void`  

```csharp
private void InitializePlatform()
	{
		m_Manager = PlatformManager.instance.GetPSI<PdxSdkPlatform>("PdxSdk");
		PlatformManager.instance.onPlatformRegistered += delegate(IPlatformServiceIntegration psi)
		{
			if (psi is PdxSdkPlatform manager)
			{
				m_Manager = manager;
			}
		};
	}
```

- `public virtual SetDefaults() : System.Void`  

```csharp
public override void SetDefaults()
	{
		autoSave = false;
		autoSaveInterval = AutoSaveInterval.FiveMinutes;
		autoSaveCount = AutoSaveCount.Three;
		fpsMode = FPSMode.Off;
		assetDatabaseAutoReloadMode = AssetDatabase.AutoReloadMode.None;
		performancePreference = SimulationSystem.PerformancePreference.Balanced;
	}
```

- `private SetTelemetryConsentChoice(System.Boolean allow) : System.Void`  

```csharp
private async void SetTelemetryConsentChoice(bool allow)
	{
		bool flag = await m_Manager.SetTelemetryConsentChoice(allow);
		m_OptionalTelemetryConsentFaulted = !flag;
		if (!flag)
		{
			GameManager.instance.userInterface.appBindings.ShowMessageDialog(new MessageDialog("Paradox.TELEMETRY_CONSENT_ERROR_TITLE", "Paradox.TELEMETRY_CONSENT_ERROR_DESCRIPTION", "Common.OK"), delegate
			{
			});
		}
	}
```

- `private TelemetryConsentFaulted() : System.Boolean`  

```csharp
private bool TelemetryConsentFaulted()
	{
		return m_OptionalTelemetryConsentFaulted;
	}
```


## Nested types

- `Game.Settings.GeneralSettings+FPSMode`  
- `Game.Settings.GeneralSettings+AutoSaveCount`  
- `Game.Settings.GeneralSettings+AutoSaveInterval`  
- `Game.Settings.GeneralSettings+<>c`  
- `Game.Settings.GeneralSettings+<SetTelemetryConsentChoice>d__36`  

