# Game.UI.Tooltip.ProgressTooltip

**Assembly:** `Game`  
**Namespace:** `Game.UI.Tooltip`  

**Type:** class public  

**Base:** `Game.UI.Tooltip.LabelIconTooltip`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`  

## Fields

- `private System.Single m_Value`  
- `private System.Single m_Max`  
- `private System.String m_Unit`  
- `private System.Boolean m_OmitMax`  
- `public static const System.Single kCapacityWarningThreshold`  

## Properties

- `public System.Single value { get; set }`  
- `public System.Single max { get; set }`  
- `public System.String unit { get; set }`  
- `public System.Boolean omitMax { get; set }`  

## Constructors

- `public ProgressTooltip()`  

## Methods

- `public static SetCapacityColor(Game.UI.Tooltip.ProgressTooltip tooltip) : System.Void`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

