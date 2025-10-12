# Game.Settings.WaterQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.WaterQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Fields

- `private System.Boolean <waterflow>k__BackingField`  
- `private System.Single <maxTessellationFactor>k__BackingField`  
- `private System.Single <tessellationFactorFadeStart>k__BackingField`  
- `private System.Single <tessellationFactorFadeRange>k__BackingField`  
- `private static UnityEngine.Rendering.HighDefinition.WaterRendering m_WaterRenderingComponent`  

## Properties

- `public System.Boolean waterflow { get; set }`  
- `public System.Single maxTessellationFactor { get; set }`  
- `public System.Single tessellationFactorFadeStart { get; set }`  
- `public System.Single tessellationFactorFadeRange { get; set }`  
- `private static Game.Settings.WaterQualitySettings highQuality { private get }`  
- `private static Game.Settings.WaterQualitySettings mediumQuality { private get }`  
- `private static Game.Settings.WaterQualitySettings lowQuality { private get }`  

## Constructors

- `public WaterQualitySettings()`  
- `public WaterQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

## Methods

- `public virtual Apply() : System.Void`  

