# Game.Settings.VolumetricsQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.VolumetricsQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Fields

- `private System.Boolean <enabled>k__BackingField`  
- `private System.Single <budget>k__BackingField`  
- `private System.Single <resolutionDepthRatio>k__BackingField`  
- `private static UnityEngine.Rendering.HighDefinition.Fog m_FogComponent`  

## Properties

- `public System.Boolean enabled { get; set }`  
- `public System.Single budget { get; set }`  
- `public System.Single resolutionDepthRatio { get; set }`  
- `private static Game.Settings.VolumetricsQualitySettings highQuality { private get }`  
- `private static Game.Settings.VolumetricsQualitySettings mediumQuality { private get }`  
- `private static Game.Settings.VolumetricsQualitySettings lowQuality { private get }`  
- `private static Game.Settings.VolumetricsQualitySettings disabled { private get }`  

## Constructors

- `public VolumetricsQualitySettings()`  
- `public VolumetricsQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

## Methods

- `public virtual Apply() : System.Void`  
- `public virtual IsOptionsDisabled() : System.Boolean`  

