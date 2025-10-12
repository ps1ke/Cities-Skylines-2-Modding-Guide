# Game.UI.Editor.PopupSearchField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.ISettable`  

## Fields

- `private System.String m_Value`  
- `private System.Boolean m_ValueIsFavorite`  
- `private System.Collections.Generic.List<Game.UI.Editor.PopupSearchField+Suggestion> m_Suggestions`  
- `private Game.UI.Editor.PopupSearchField+IAdapter <adapter>k__BackingField`  
- `private System.Boolean <hasFavorites>k__BackingField`  

## Properties

- `public Game.UI.Editor.PopupSearchField+IAdapter adapter { get; set }`  
- `public System.Boolean hasFavorites { get; set }`  
- `public System.Boolean shouldTriggerValueChangedEvent { get }`  

## Constructors

- `public PopupSearchField()`  

## Methods

- `public SetValue(Colossal.UI.Binding.IJsonReader reader) : System.Void`  
- `public SetValue(System.String value) : System.Void`  
- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.UI.Editor.PopupSearchField+IAdapter`  
- `Game.UI.Editor.PopupSearchField+Suggestion`  
- `Game.UI.Editor.PopupSearchField+Bindings`  

