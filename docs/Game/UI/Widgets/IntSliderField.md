# Game.UI.Widgets.IntSliderField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.IntField<System.Int32>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`, `Game.UI.Widgets.IWarning`  

## Fields

- `private System.Boolean m_Warning`  
- `private System.Func<System.Boolean> <warningAction>k__BackingField`  
- `private System.String <unit>k__BackingField`  
- `private System.Boolean <signed>k__BackingField`  
- `private System.Boolean <separateThousands>k__BackingField`  
- `private System.Boolean <scaleDragVolume>k__BackingField`  
- `private System.Boolean <updateOnDragEnd>k__BackingField`  

## Properties

- `public System.Func<System.Boolean> warningAction { get; set }`  
- `public System.String unit { get; set }`  
- `public System.Boolean signed { get; set }`  
- `public System.Boolean separateThousands { get; set }`  
- `public System.Boolean scaleDragVolume { get; set }`  
- `public System.Boolean updateOnDragEnd { get; set }`  
- `public System.Boolean warning { get; set }`  

## Constructors

- `public IntSliderField()`  

## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

