# Game.UI.Tooltip.TooltipGroup

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Fields

- `private Unity.Mathematics.float2 m_Position`  
- `private Game.UI.Tooltip.TooltipGroup+Category m_Category`  
- `private Game.UI.Tooltip.TooltipGroup+Alignment m_HorizontalAlignment`  
- `private Game.UI.Tooltip.TooltipGroup+Alignment m_VerticalAlignment`  
- `private System.Collections.Generic.List<Game.UI.Widgets.IWidget> m_LastChildren`  
- `private System.Collections.Generic.IList<Game.UI.Widgets.IWidget> <children>k__BackingField`  

## Properties

- `public Unity.Mathematics.float2 position { get; set }`  
- `public Game.UI.Tooltip.TooltipGroup+Alignment horizontalAlignment { get; set }`  
- `public Game.UI.Tooltip.TooltipGroup+Alignment verticalAlignment { get; set }`  
- `public Game.UI.Tooltip.TooltipGroup+Category category { get; set }`  
- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> children { get; set }`  
- `public System.Collections.Generic.IList<Game.UI.Widgets.IWidget> visibleChildren { get }`  

## Constructors

- `public TooltipGroup()`  

## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

## Nested types

- `Game.UI.Tooltip.TooltipGroup+Alignment`  
- `Game.UI.Tooltip.TooltipGroup+Category`  

