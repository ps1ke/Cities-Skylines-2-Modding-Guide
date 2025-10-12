# Game.Settings.DepthOfFieldQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.DepthOfFieldQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Fields

- `private System.Boolean <enabled>k__BackingField`  
- `private System.Int32 <nearSampleCount>k__BackingField`  
- `private System.Single <nearMaxRadius>k__BackingField`  
- `private System.Int32 <farSampleCount>k__BackingField`  
- `private System.Single <farMaxRadius>k__BackingField`  
- `private UnityEngine.Rendering.HighDefinition.DepthOfFieldResolution <resolution>k__BackingField`  
- `private System.Boolean <highQualityFiltering>k__BackingField`  
- `private static UnityEngine.Rendering.HighDefinition.DepthOfField m_DOFComponent`  

## Properties

- `public System.Boolean enabled { get; set }`  
- `public System.Int32 nearSampleCount { get; set }`  
- `public System.Single nearMaxRadius { get; set }`  
- `public System.Int32 farSampleCount { get; set }`  
- `public System.Single farMaxRadius { get; set }`  
- `public UnityEngine.Rendering.HighDefinition.DepthOfFieldResolution resolution { get; set }`  
- `public System.Boolean highQualityFiltering { get; set }`  
- `private static Game.Settings.DepthOfFieldQualitySettings highQuality { private get }`  
- `private static Game.Settings.DepthOfFieldQualitySettings mediumQuality { private get }`  
- `private static Game.Settings.DepthOfFieldQualitySettings lowQuality { private get }`  
- `private static Game.Settings.DepthOfFieldQualitySettings disabled { private get }`  

## Constructors

- `public DepthOfFieldQualitySettings()`  
- `public DepthOfFieldQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

## Methods

- `public virtual Apply() : System.Void`  
- `public virtual IsOptionsDisabled() : System.Boolean`  

