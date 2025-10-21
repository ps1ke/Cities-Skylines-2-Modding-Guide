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
public GeneralSettings();
```


## Methods

- `private <InitializePlatform>b__39_0(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  

```csharp
private System.Void <InitializePlatform>b__39_0(Colossal.PSI.Common.IPlatformServiceIntegration psi);
```

- `public static AutoSaveEnabled() : System.Boolean`  

```csharp
public static System.Boolean AutoSaveEnabled();
```

- `public static CanSave() : System.Boolean`  

```csharp
public static System.Boolean CanSave();
```

- `private HideTelemetryConsentChoice() : System.Boolean`  

```csharp
private System.Boolean HideTelemetryConsentChoice();
```

- `private InitializePlatform() : System.Void`  

```csharp
private System.Void InitializePlatform();
```

- `public virtual SetDefaults() : System.Void`  

```csharp
public virtual System.Void SetDefaults();
```

- `private SetTelemetryConsentChoice(System.Boolean allow) : System.Void`  

```csharp
private System.Void SetTelemetryConsentChoice(System.Boolean allow);
```

- `private TelemetryConsentFaulted() : System.Boolean`  

```csharp
private System.Boolean TelemetryConsentFaulted();
```


## Nested types

- `Game.Settings.GeneralSettings+FPSMode`  
- `Game.Settings.GeneralSettings+AutoSaveCount`  
- `Game.Settings.GeneralSettings+AutoSaveInterval`  
- `Game.Settings.GeneralSettings+<>c`  
- `Game.Settings.GeneralSettings+<SetTelemetryConsentChoice>d__36`  

