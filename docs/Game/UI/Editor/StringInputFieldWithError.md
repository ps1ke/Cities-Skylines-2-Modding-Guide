# Game.UI.Editor.StringInputFieldWithError

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.StringInputField`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`, `Game.UI.Widgets.IWarning`  

## Fields

- `private System.Boolean m_Error`  
- `private System.Func<System.Boolean> <error>k__BackingField`  
- `private Game.UI.Localization.LocalizedString <errorMessage>k__BackingField`  

## Properties

- `public System.Func<System.Boolean> error { get; set }`  
- `public Game.UI.Localization.LocalizedString errorMessage { get; set }`  

## Constructors

- `public StringInputFieldWithError()`  

## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

