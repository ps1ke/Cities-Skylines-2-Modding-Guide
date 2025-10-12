# Game.Settings.TextureQualitySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.TextureQualitySettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Fields

- `private System.Int32 <mipbias>k__BackingField`  
- `private UnityEngine.Rendering.VirtualTexturing.FilterMode <filterMode>k__BackingField`  

## Properties

- `public System.Int32 mipbias { get; set }`  
- `public UnityEngine.Rendering.VirtualTexturing.FilterMode filterMode { get; set }`  
- `private static Game.Settings.TextureQualitySettings highQuality { private get }`  
- `private static Game.Settings.TextureQualitySettings mediumQuality { private get }`  
- `private static Game.Settings.TextureQualitySettings lowQuality { private get }`  
- `private static Game.Settings.TextureQualitySettings veryLowQuality { private get }`  

## Constructors

- `public TextureQualitySettings()`  
- `public TextureQualitySettings(Game.Settings.QualitySetting+Level quality)`  

## Methods

- `public virtual Apply() : System.Void`  

