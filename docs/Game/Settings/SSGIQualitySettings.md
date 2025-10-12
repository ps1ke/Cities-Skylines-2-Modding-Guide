# Game.Settings.SSGIQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.SSGIQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Fields

- `private System.Boolean <enabled>k__BackingField`  
- `private System.Boolean <fullscreen>k__BackingField`  
- `private System.Int32 <raySteps>k__BackingField`  
- `private System.Single <denoiserRadius>k__BackingField`  
- `private System.Boolean <halfResolutionPass>k__BackingField`  
- `private System.Boolean <secondDenoiserPass>k__BackingField`  
- `private System.Single <depthBufferThickness>k__BackingField`  
- `private static UnityEngine.Rendering.HighDefinition.GlobalIllumination m_SSGIComponent`  

## Properties

- `public System.Boolean enabled { get; set }`  
- `public System.Boolean fullscreen { get; set }`  
- `public System.Int32 raySteps { get; set }`  
- `public System.Single denoiserRadius { get; set }`  
- `public System.Boolean halfResolutionPass { get; set }`  
- `public System.Boolean secondDenoiserPass { get; set }`  
- `public System.Single depthBufferThickness { get; set }`  
- `private static Game.Settings.SSGIQualitySettings highQuality { private get }`  
- `private static Game.Settings.SSGIQualitySettings mediumQuality { private get }`  
- `private static Game.Settings.SSGIQualitySettings lowQuality { private get }`  
- `private static Game.Settings.SSGIQualitySettings disabled { private get }`  

## Constructors

- `public SSGIQualitySettings()`  
- `public SSGIQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

## Methods

- `public virtual Apply() : System.Void`  
- `public virtual IsOptionsDisabled() : System.Boolean`  

