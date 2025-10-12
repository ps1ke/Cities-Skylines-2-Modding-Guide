# Game.UI.Widgets.StringInputField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Field<System.String>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`, `Game.UI.Widgets.IWarning`  

## Fields

- `private System.Boolean m_Warning`  
- `private System.Func<System.Boolean> <warningAction>k__BackingField`  
- `private System.Int32 m_Multiline`  
- `private System.Int32 m_MaxLength`  
- `public static readonly System.Int32 kDefaultMultilines`  
- `public static readonly System.Int32 kSingleLine`  

## Properties

- `public System.Func<System.Boolean> warningAction { get; set }`  
- `public System.Int32 multiline { get; set }`  
- `public System.Int32 maxLength { get; set }`  
- `public System.Boolean warning { get; set }`  

## Constructors

- `public StringInputField()`  

## Methods

- `public virtual GetValue() : System.String`  
- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

