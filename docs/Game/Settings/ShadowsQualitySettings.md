# Game.Settings.ShadowsQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.ShadowsQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Fields

- `private System.Boolean <enabled>k__BackingField`  
- `private System.Int32 <directionalShadowResolution>k__BackingField`  
- `private System.Boolean <terrainCastShadows>k__BackingField`  
- `private System.Single <shadowCullingThresholdHeight>k__BackingField`  
- `private System.Single <shadowCullingThresholdVolume>k__BackingField`  
- `private static UnityEngine.Rendering.HighDefinition.HDShadowSettings m_CascadeShadows`  
- `private static UnityEngine.Rendering.HighDefinition.HDAdditionalLightData m_SunLightData`  

## Properties

- `public System.Boolean enabled { get; set }`  
- `public System.Int32 directionalShadowResolution { get; set }`  
- `public System.Boolean terrainCastShadows { get; set }`  
- `public System.Single shadowCullingThresholdHeight { get; set }`  
- `public System.Single shadowCullingThresholdVolume { get; set }`  
- `private static Game.Settings.ShadowsQualitySettings highQuality { private get }`  
- `private static Game.Settings.ShadowsQualitySettings mediumQuality { private get }`  
- `private static Game.Settings.ShadowsQualitySettings lowQuality { private get }`  
- `private static Game.Settings.ShadowsQualitySettings disabled { private get }`  

## Constructors

- `public ShadowsQualitySettings()`  
- `public ShadowsQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

## Methods

- `public virtual Apply() : System.Void`  
- `public virtual IsOptionsDisabled() : System.Boolean`  

