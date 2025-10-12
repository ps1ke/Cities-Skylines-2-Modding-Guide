# Game.Settings.GameplaySettings

**Assembly:** `Game`  
**Namespace:** `Game.Settings`  

**Type:** class public  

**Base:** `Game.Settings.Setting`  
**Implements:** `System.IEquatable<Game.Settings.Setting>`  

**Attributes:** `FileLocation`  

## Fields

- `private Game.CameraController m_CameraController`  
- `private System.Boolean <edgeScrolling>k__BackingField`  
- `private System.Single <edgeScrollingSensitivity>k__BackingField`  
- `private System.Boolean <dayNightVisual>k__BackingField`  
- `private System.Boolean <pausedAfterLoading>k__BackingField`  
- `private System.Boolean <showTutorials>k__BackingField`  
- `public static const System.String kName`  

## Properties

- `public System.Boolean edgeScrolling { get; set }`  
- `public System.Single edgeScrollingSensitivity { get; set }`  
- `public System.Boolean dayNightVisual { get; set }`  
- `public System.Boolean pausedAfterLoading { get; set }`  
- `public System.Boolean showTutorials { get; set }`  
- `public System.Boolean resetTutorials { set }`  

## Constructors

- `public GameplaySettings()`  

## Methods

- `public virtual Apply() : System.Void`  
- `public virtual SetDefaults() : System.Void`  

