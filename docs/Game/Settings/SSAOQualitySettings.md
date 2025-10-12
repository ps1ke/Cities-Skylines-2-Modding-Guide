# Game.Settings.SSAOQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.SSAOQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Fields

- `private System.Boolean <enabled>k__BackingField`  
- `private System.Int32 <maxPixelRadius>k__BackingField`  
- `private System.Boolean <fullscreen>k__BackingField`  
- `private System.Int32 <stepCount>k__BackingField`  
- `private static UnityEngine.Rendering.HighDefinition.ScreenSpaceAmbientOcclusion m_AOComponent`  

## Properties

- `public System.Boolean enabled { get; set }`  
- `public System.Int32 maxPixelRadius { get; set }`  
- `public System.Boolean fullscreen { get; set }`  
- `public System.Int32 stepCount { get; set }`  
- `private static Game.Settings.SSAOQualitySettings highQuality { private get }`  
- `private static Game.Settings.SSAOQualitySettings mediumQuality { private get }`  
- `private static Game.Settings.SSAOQualitySettings lowQuality { private get }`  
- `private static Game.Settings.SSAOQualitySettings disabled { private get }`  

## Constructors

- `public SSAOQualitySettings()`  
- `public SSAOQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

## Methods

- `public virtual Apply() : System.Void`  
- `public virtual IsOptionsDisabled() : System.Boolean`  

