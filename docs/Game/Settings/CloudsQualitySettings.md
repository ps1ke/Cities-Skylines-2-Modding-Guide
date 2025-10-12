# Game.Settings.CloudsQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.CloudsQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Fields

- `private System.Boolean <volumetricCloudsEnabled>k__BackingField`  
- `private System.Boolean <distanceCloudsEnabled>k__BackingField`  
- `private System.Boolean <volumetricCloudsShadows>k__BackingField`  
- `private System.Boolean <distanceCloudsShadows>k__BackingField`  
- `private static UnityEngine.Rendering.HighDefinition.VolumetricClouds m_VolumetricClouds`  
- `private static UnityEngine.Rendering.HighDefinition.VisualEnvironment m_VisualEnvironment`  
- `private static UnityEngine.Rendering.HighDefinition.CloudLayer m_CloudLayer`  

## Properties

- `public System.Boolean volumetricCloudsEnabled { get; set }`  
- `public System.Boolean distanceCloudsEnabled { get; set }`  
- `public System.Boolean volumetricCloudsShadows { get; set }`  
- `public System.Boolean distanceCloudsShadows { get; set }`  
- `private static Game.Settings.CloudsQualitySettings highQuality { private get }`  
- `private static Game.Settings.CloudsQualitySettings mediumQuality { private get }`  
- `private static Game.Settings.CloudsQualitySettings lowQuality { private get }`  
- `private static Game.Settings.CloudsQualitySettings disabled { private get }`  

## Constructors

- `public CloudsQualitySettings()`  
- `public CloudsQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

## Methods

- `public virtual Apply() : System.Void`  

