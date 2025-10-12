# Game.Settings.MotionBlurQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.MotionBlurQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Fields

- `private System.Boolean <enabled>k__BackingField`  
- `private System.Int32 <sampleCount>k__BackingField`  
- `private static UnityEngine.Rendering.HighDefinition.MotionBlur m_MotionBlurComponent`  

## Properties

- `public System.Boolean enabled { get; set }`  
- `public System.Int32 sampleCount { get; set }`  
- `private static Game.Settings.MotionBlurQualitySettings highQuality { private get }`  
- `private static Game.Settings.MotionBlurQualitySettings mediumQuality { private get }`  
- `private static Game.Settings.MotionBlurQualitySettings lowQuality { private get }`  
- `private static Game.Settings.MotionBlurQualitySettings disabled { private get }`  

## Constructors

- `public MotionBlurQualitySettings()`  
- `public MotionBlurQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

## Methods

- `public virtual Apply() : System.Void`  
- `public virtual IsOptionsDisabled() : System.Boolean`  

