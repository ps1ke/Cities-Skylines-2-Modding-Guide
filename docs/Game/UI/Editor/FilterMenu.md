# Game.UI.Editor.FilterMenu

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Fields

- `private System.Boolean m_Dirty`  
- `private Game.UI.Editor.FilterMenu+IAdapter m_Adapter`  

## Properties

- `public Game.UI.Editor.FilterMenu+IAdapter adapter { get; set }`  

## Constructors

- `public FilterMenu()`  

## Methods

- `private OnAvailableFiltersChanged() : System.Void`  
- `private OnClearFilters() : System.Void`  
- `private OnToggleFilter(System.String filter, System.Boolean active) : System.Void`  
- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.UI.Editor.FilterMenu+IAdapter`  
- `Game.UI.Editor.FilterMenu+Bindings`  

