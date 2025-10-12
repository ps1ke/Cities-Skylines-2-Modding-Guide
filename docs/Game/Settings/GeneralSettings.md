# Game.Settings.GeneralSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`  

## Fields

- `private Colossal.IO.AssetDatabase.AssetDatabase+AutoReloadMode m_AssetDatabaseAutoReloadMode`  
- `private Game.Simulation.SimulationSystem+PerformancePreference m_PerformancePreference`  
- `private Game.Settings.GeneralSettings+FPSMode <fpsMode>k__BackingField`  
- `private System.Boolean <autoSave>k__BackingField`  
- `private Game.Settings.GeneralSettings+AutoSaveInterval <autoSaveInterval>k__BackingField`  
- `private Game.Settings.GeneralSettings+AutoSaveCount <autoSaveCount>k__BackingField`  
- `private Colossal.PSI.PdxSdk.PdxSdkPlatform m_Manager`  
- `private System.Boolean m_OptionalTelemetryConsentFaulted`  
- `public static const System.String kName`  

## Properties

- `public Colossal.IO.AssetDatabase.AssetDatabase+AutoReloadMode assetDatabaseAutoReloadMode { get; set }`  
- `public Game.Simulation.SimulationSystem+PerformancePreference performancePreference { get; set }`  
- `public Game.Settings.GeneralSettings+FPSMode fpsMode { get; set }`  
- `public System.Boolean autoSave { get; set }`  
- `public Game.Settings.GeneralSettings+AutoSaveInterval autoSaveInterval { get; set }`  
- `public Game.Settings.GeneralSettings+AutoSaveCount autoSaveCount { get; set }`  
- `public System.Boolean autoSaveNow { get; set }`  
- `public System.Boolean allowOptionalTelemetry { get; set }`  
- `public System.Boolean resetSettings { set }`  

## Constructors

- `public GeneralSettings()`  

## Methods

- `private <InitializePlatform>b__39_0(Colossal.PSI.Common.IPlatformServiceIntegration psi) : System.Void`  
- `public static AutoSaveEnabled() : System.Boolean`  
- `public static CanSave() : System.Boolean`  
- `private HideTelemetryConsentChoice() : System.Boolean`  
- `private InitializePlatform() : System.Void`  
- `public virtual SetDefaults() : System.Void`  
- `private SetTelemetryConsentChoice(System.Boolean allow) : System.Void`  
- `private TelemetryConsentFaulted() : System.Boolean`  

## Nested types

- `Game.Settings.GeneralSettings+FPSMode`  
- `Game.Settings.GeneralSettings+AutoSaveCount`  
- `Game.Settings.GeneralSettings+AutoSaveInterval`  
- `Game.Settings.GeneralSettings+<>c`  
- `Game.Settings.GeneralSettings+<SetTelemetryConsentChoice>d__36`  

