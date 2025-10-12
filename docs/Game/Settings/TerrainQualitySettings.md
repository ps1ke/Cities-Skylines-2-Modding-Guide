# Game.Settings.TerrainQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.TerrainQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Fields

- `private System.Int32 <finalTessellation>k__BackingField`  
- `private System.Int32 <targetPatchSize>k__BackingField`  
- `private static UnityEngine.Rendering.HighDefinition.TerrainRendering m_TerrainRenderingComponent`  

## Properties

- `public System.Int32 finalTessellation { get; set }`  
- `public System.Int32 targetPatchSize { get; set }`  
- `private static Game.Settings.TerrainQualitySettings highQuality { private get }`  
- `private static Game.Settings.TerrainQualitySettings mediumQuality { private get }`  
- `private static Game.Settings.TerrainQualitySettings lowQuality { private get }`  

## Constructors

- `public TerrainQualitySettings()`  
- `public TerrainQualitySettings(Game.Settings.QualitySetting+Level quality, UnityEngine.Rendering.VolumeProfile profile)`  

## Methods

- `public virtual Apply() : System.Void`  

