# Game.UI.Widgets.EnumField

**Assembly:** `Game`  
**Namespace:** `Game.UI.Widgets`  

**Type:** class public  

**Base:** `Game.UI.Widgets.Field<System.UInt64>`  
**Implements:** `Game.UI.Widgets.IWidget`, `Colossal.UI.Binding.IJsonWritable`, `Game.UI.Widgets.IVisibleWidget`, `Game.UI.Widgets.IDisableCallback`, `Game.UI.Widgets.INamed`, `Game.UI.Widgets.ITooltipTarget`, `Game.UI.Widgets.IUITagProvider`, `Game.UI.Widgets.ISettable`, `Game.UI.Widgets.IWarning`  

## Fields

- `private System.Int32 m_ItemsVersion`  
- `private System.Boolean m_Warning`  
- `private System.Func<System.Boolean> <warningAction>k__BackingField`  
- `private Game.UI.Widgets.EnumMember[] <enumMembers>k__BackingField`  
- `private System.Func<System.Int32> <itemsVersion>k__BackingField`  
- `private Game.Reflection.ITypedValueAccessor<Game.UI.Widgets.EnumMember[]> <itemsAccessor>k__BackingField`  

## Properties

- `public System.Func<System.Boolean> warningAction { get; set }`  
- `public Game.UI.Widgets.EnumMember[] enumMembers { get; set }`  
- `public System.Func<System.Int32> itemsVersion { get; set }`  
- `public Game.Reflection.ITypedValueAccessor<Game.UI.Widgets.EnumMember[]> itemsAccessor { get; set }`  
- `public System.Boolean warning { get; set }`  

## Constructors

- `public EnumField()`  

## Methods

- `protected virtual Update() : Game.UI.Widgets.WidgetChanges`  
- `protected virtual WriteProperties(Colossal.UI.Binding.IJsonWriter writer) : System.Void`  

