# Game.UI.Widgets.NamedWidget

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class abstract public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`  

## Fields

- `private Game.UI.Localization.LocalizedString m_displayName`  
- `private Game.UI.Localization.LocalizedString m_description`  
- `private System.Func<Game.UI.Localization.LocalizedString> <displayNameAction>k__BackingField`  
- `private System.Func<Game.UI.Localization.LocalizedString> <descriptionAction>k__BackingField`  

## Properties

- `public System.Func<Game.UI.Localization.LocalizedString> displayNameAction { get; set }`  
- `public System.Func<Game.UI.Localization.LocalizedString> descriptionAction { get; set }`  
- `public Game.UI.Localization.LocalizedString displayName { get; set }`  
- `public Game.UI.Localization.LocalizedString description { get; set }`  

## Constructors

- `protected NamedWidget()`  

## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  
- `public UpdateNameAndDescription(System.Boolean setChanged = True) : Game.UI.Widgets.WidgetChanges`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

