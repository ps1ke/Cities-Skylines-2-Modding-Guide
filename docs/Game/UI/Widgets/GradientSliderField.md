# Game.UI.Widgets.GradientSliderField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.FloatSliderField<System.Single>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`, `Game.UI.Widgets.IIconProvider`  

## Fields

- `private Game.UI.Widgets.ColorGradient <gradient>k__BackingField`  
- `private System.Func<System.String> <iconSrc>k__BackingField`  

## Properties

- `protected System.Single defaultMin { protected get }`  
- `protected System.Single defaultMax { protected get }`  
- `public Game.UI.Widgets.ColorGradient gradient { get; set }`  
- `public System.Func<System.String> iconSrc { get; set }`  

## Constructors

- `public GradientSliderField()`  

## Methods

- `public virtual ToFieldType(Unity.Mathematics.double4 value) : System.Single`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

