# Game.UI.Widgets.IconButton

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IInvokable`  

## Fields

- `private System.Boolean m_Selected`  
- `private System.String m_Icon`  
- `private System.Action <action>k__BackingField`  
- `private System.Func<System.Boolean> <selected>k__BackingField`  
- `private System.Nullable<Game.UI.Localization.LocalizedString> <tooltip>k__BackingField`  

## Properties

- `public System.String icon { get; set }`  
- `public System.Action action { get; set }`  
- `public System.Func<System.Boolean> selected { get; set }`  
- `public System.Nullable<Game.UI.Localization.LocalizedString> tooltip { get; set }`  

## Constructors

- `public IconButton()`  

## Methods

- `public Invoke() : System.Void`  
- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

