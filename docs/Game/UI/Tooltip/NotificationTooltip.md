# Game.UI.Tooltip.NotificationTooltip

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Widget`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Fields

- `private System.String m_Name`  
- `private Game.UI.Tooltip.TooltipColor m_Color`  
- `private System.Boolean m_Verbose`  

## Properties

- `public System.String name { get; set }`  
- `public Game.UI.Tooltip.TooltipColor color { get; set }`  
- `public System.Boolean verbose { get; set }`  

## Constructors

- `public NotificationTooltip()`  

## Methods

- `public static GetColor(Game.Notifications.IconPriority iconPriority) : Game.UI.Tooltip.TooltipColor`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

