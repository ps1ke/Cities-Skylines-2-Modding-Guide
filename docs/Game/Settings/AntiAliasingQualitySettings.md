# Game.Settings.AntiAliasingQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.AntiAliasingQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Fields

- `private Game.Settings.AntiAliasingQualitySettings+AntialiasingMethod <antiAliasingMethod>k__BackingField`  
- `private UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData+SMAAQualityLevel <smaaQuality>k__BackingField`  
- `private UnityEngine.Rendering.MSAASamples <outlinesMSAA>k__BackingField`  
- `private static UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData m_GameCamera`  

## Properties

- `public Game.Settings.AntiAliasingQualitySettings+AntialiasingMethod antiAliasingMethod { get; set }`  
- `public UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData+SMAAQualityLevel smaaQuality { get; set }`  
- `public UnityEngine.Rendering.MSAASamples outlinesMSAA { get; set }`  
- `private static Game.Settings.AntiAliasingQualitySettings highQuality { private get }`  
- `private static Game.Settings.AntiAliasingQualitySettings mediumQuality { private get }`  
- `private static Game.Settings.AntiAliasingQualitySettings lowQuality { private get }`  
- `private static Game.Settings.AntiAliasingQualitySettings disabled { private get }`  

## Constructors

- `public AntiAliasingQualitySettings()`  
- `public AntiAliasingQualitySettings(Game.Settings.QualitySetting+Level quality)`  

## Methods

- `public virtual Apply() : System.Void`  
- `public virtual IsOptionFullyDisabled() : System.Boolean`  
- `private static ToAAMode(Game.Settings.AntiAliasingQualitySettings+AntialiasingMethod method) : UnityEngine.Rendering.HighDefinition.HDAdditionalCameraData+AntialiasingMode`  

## Nested types

- `Game.Settings.AntiAliasingQualitySettings+AntialiasingMethod`  

