# Game.UI.Widgets.FloatSliderField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.FloatSliderField<System.Double>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`, `Game.UI.Widgets.IWarning`  

## Fields

- `private System.Boolean m_Warning`  
- `private System.Func<System.Boolean> <warningAction>k__BackingField`  

## Properties

- `public System.Func<System.Boolean> warningAction { get; set }`  
- `protected System.Double defaultMin { protected get }`  
- `protected System.Double defaultMax { protected get }`  
- `public System.Boolean warning { get; set }`  

## Constructors

- `public FloatSliderField()`  

## Methods

- `public virtual ToFieldType(Unity.Mathematics.double4 value) : System.Double`  
- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

