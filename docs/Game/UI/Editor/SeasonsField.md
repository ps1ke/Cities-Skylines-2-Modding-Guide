# Game.UI.Editor.SeasonsField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Editor`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Fields

- `private Unity.Entities.Entity m_SelectedSeason`  
- `private System.Collections.Generic.List<Game.Simulation.ClimateSystem+SeasonInfo> m_Seasons`  
- `private Game.UI.Editor.SeasonsField+SeasonCurves m_SeasonCurves`  
- `private Game.UI.Editor.SeasonsField+IAdapter <adapter>k__BackingField`  

## Properties

- `public Game.UI.Editor.SeasonsField+IAdapter adapter { get; set }`  

## Constructors

- `public SeasonsField()`  

## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.UI.Editor.SeasonsField+SeasonCurves`  
- `Game.UI.Editor.SeasonsField+Season`  
- `Game.UI.Editor.SeasonsField+IAdapter`  
- `Game.UI.Editor.SeasonsField+Bindings`  

