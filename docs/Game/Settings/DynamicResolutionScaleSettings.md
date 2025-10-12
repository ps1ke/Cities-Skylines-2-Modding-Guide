# Game.Settings.DynamicResolutionScaleSettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.QualitySetting<Game.Settings.DynamicResolutionScaleSettings>`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `SettingsUIAdvanced`, `SettingsUISection`, `SettingsUIDisableByCondition`  

## Fields

- `private System.Boolean <enabled>k__BackingField`  
- `private System.Boolean <isAdaptive>k__BackingField`  
- `private Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter <upscaleFilter>k__BackingField`  
- `private System.Single <minScale>k__BackingField`  
- `private static UnityEngine.Camera m_Camera`  

## Properties

- `public System.Boolean enabled { get; set }`  
- `public System.Boolean isAdaptive { get; set }`  
- `public Game.Rendering.Utilities.AdaptiveDynamicResolutionScale+DynResUpscaleFilter upscaleFilter { get; set }`  
- `public System.Single minScale { get; set }`  
- `private static Game.Settings.DynamicResolutionScaleSettings constantQuality { private get }`  
- `private static Game.Settings.DynamicResolutionScaleSettings automaticQuality { private get }`  
- `private static Game.Settings.DynamicResolutionScaleSettings disabledQuality { private get }`  

## Constructors

- `public DynamicResolutionScaleSettings()`  
- `public DynamicResolutionScaleSettings(Game.Settings.QualitySetting+Level quality)`  

## Methods

- `public virtual Apply() : System.Void`  
- `public virtual IsOptionFullyDisabled() : System.Boolean`  
- `public virtual IsOptionsDisabled() : System.Boolean`  

