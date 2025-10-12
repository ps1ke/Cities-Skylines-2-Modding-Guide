# Game.UI.InGame.PresetDescriptor

**Assembly:** `Game`  
**Namespace:** `Game.UI.InGame`  

**Type:** class public  

**Base:** `System.Object`  

## Fields

- `private System.Collections.Generic.List<System.String> m_OptionsId`  
- `private System.Collections.Generic.Dictionary<Game.Rendering.CinematicCamera.PhotoModeProperty, System.Single[]> m_Values`  

## Properties

- `public System.Collections.Generic.IReadOnlyCollection<System.String> optionsId { get }`  
- `public System.Collections.Generic.IReadOnlyDictionary<Game.Rendering.CinematicCamera.PhotoModeProperty, System.Single[]> values { get }`  

## Constructors

- `public PresetDescriptor()`  

## Methods

- `public AddOption(System.String optionId) : System.Void`  
- `public AddOptions(System.Collections.Generic.IEnumerable<System.String> optionIds) : System.Void`  
- `public AddValues(Game.Rendering.CinematicCamera.PhotoModeProperty targetProperty, System.Single[] values) : System.Void`  
- `public Validate() : System.Boolean`  

