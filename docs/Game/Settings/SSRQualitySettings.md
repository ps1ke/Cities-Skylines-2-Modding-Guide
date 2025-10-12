# Game.Settings.SSRQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.SSRQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Fields

- `private System.Boolean <enabled>k__BackingField`  
- `private System.Boolean <enabledTransparent>k__BackingField`  
- `private System.Int32 <maxRaySteps>k__BackingField`  
- `private static UnityEngine.Rendering.HighDefinition.ScreenSpaceReflection m_SSRComponent`  

## Properties

- `public System.Boolean enabled { get; set }`  
- `public System.Boolean enabledTransparent { get; set }`  
- `public System.Int32 maxRaySteps { get; set }`  
- `private static Game.Settings.SSRQualitySettings highQuality { private get }`  
- `private static Game.Settings.SSRQualitySettings mediumQuality { private get }`  
- `private static Game.Settings.SSRQualitySettings lowQuality { private get }`  
- `private static Game.Settings.SSRQualitySettings disabled { private get }`  

## Constructors

- `public SSRQualitySettings()`  
- `public SSRQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

## Methods

- `public virtual Apply() : System.Void`  
- `public virtual IsOptionsDisabled() : System.Boolean`  

